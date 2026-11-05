## تکلیف اول

### ۱. ساخت پوشه‌های تو در تو با یک دستور

هدف: ساخت یک پوشه که داخلش پوشه دیگری باشد و داخل آن سه پوشه هم‌سطح قرار بگیرد.

دستور زیر با گزینه `-p` پوشه‌های والد را هم می‌سازد و با `{css,pages,py}` سه پوشه را یکجا ایجاد می‌کند:

```bash
mkdir -p project/assets/{css,pages,py}
```

برای بررسی نتیجه:

```bash
ls -R project
```

خروجی:

```
project:
assets

project/assets:
css  pages  py

project/assets/css:

project/assets/pages:

project/assets/py:
```

ساختار ساخته‌شده:

```
project
└── assets
    ├── css
    ├── pages
    └── py

```
## تکلیف دوم

### هارد لینک و سافت لینک

هدف: ساخت فایل `info.txt`، ساخت یک هارد لینک و یک سافت لینک برای آن، حذف فایل اصلی با `rm` و بررسی محتوای دو لینک با `cat`.

### اجرای کامل دستورها در ترمینال

```
ubuntu@ubuntu:~$ echo "Hello" >info.txt
ubuntu@ubuntu:~$ cat info.txt
Hello
ubuntu@ubuntu:~$ ln info.txt hardlink.txt
ubuntu@ubuntu:~$ ln -s info.txt softlink.txt
ubuntu@ubuntu:~$ ls -li info.txt hardlink.txt softlink.txt
15935 -rw-rw-r-- 2 ubuntu ubuntu 6 Nov  1 12:17 hardlink.txt
15935 -rw-rw-r-- 2 ubuntu ubuntu 6 Nov  1 12:17 info.txt
15951 lrwxrwxrwx 1 ubuntu ubuntu 8 Nov  1 12:19 softlink.txt -> info.txt
ubuntu@ubuntu:~$ rm info.txt
ubuntu@ubuntu:~$ cat hardlink.txt
Hello
ubuntu@ubuntu:~$ cat softlink.txt
cat: softlink.txt: No such file or directory
ubuntu@ubuntu:~$ ls -li hardlink.txt softlink.txt
15935 -rw-rw-r-- 1 ubuntu ubuntu 6 Nov  1 12:17 hardlink.txt
15951 lrwxrwxrwx 1 ubuntu ubuntu 8 Nov  1 12:19 softlink.txt -> info.txt
```

### توضیح مراحل

| مرحله | دستور | توضیح |
|---|---|---|
| ساخت فایل | `echo "Hello" >info.txt` | فایل `info.txt` با محتوای `Hello` ساخته می‌شود. |
| هارد لینک | `ln info.txt hardlink.txt` | یک نام دوم برای همان داده (همان inode) ساخته می‌شود. |
| سافت لینک | `ln -s info.txt softlink.txt` | یک میان‌بر (فایل جدا) ساخته می‌شود که فقط مسیر `info.txt` را نگه می‌دارد. |
| بررسی inode | `ls -li` | شماره inode در ستون اول و تعداد لینک‌ها در ستون سوم دیده می‌شود. |
| حذف فایل اصلی | `rm info.txt` | فقط نام `info.txt` حذف می‌شود. |
| بررسی لینک‌ها | `cat hardlink.txt` و `cat softlink.txt` | محتوای هر لینک خوانده می‌شود. |

### قبل از حذف فایل اصلی چه می‌بینیم؟

- `info.txt` و `hardlink.txt` شماره inode یکسان دارند (`15935`) و تعداد لینک هر دو `2` است. یعنی هر دو نام به یک داده روی دیسک اشاره می‌کنند.
- `softlink.txt` شماره inode متفاوتی دارد (`15951`)، نوعش لینک است (حرف `l` در ابتدای `lrwxrwxrwx`) و با `->` به `info.txt` اشاره می‌کند.

### بعد از حذف فایل اصلی چه می‌بینیم و چرا؟

**۱. هارد لینک:** دستور `cat hardlink.txt` همچنان `Hello` را نشان می‌دهد.

دلیل: هارد لینک یک نام دیگر برای همان inode (همان داده) است. دستور `rm info.txt` فقط یکی از نام‌ها را حذف کرد و تعداد لینک‌ها از `2` به `1` رسید. تا وقتی حداقل یک نام به inode اشاره کند، داده از بین نمی‌رود.

**۲. سافت لینک:** دستور `cat softlink.txt` خطای `No such file or directory` می‌دهد.

دلیل: سافت لینک خودش داده ندارد و فقط مسیر (نام) `info.txt` را ذخیره کرده است. وقتی `info.txt` حذف شد، لینک به جایی اشاره می‌کند که دیگر وجود ندارد. به این حالت لینک شکسته (dangling link) می‌گویند.

### جمع‌بندی

| | هارد لینک | سافت لینک |
|---|---|---|
| به چه اشاره می‌کند؟ | به خود داده (inode) | به نام/مسیر فایل |
| inode | همان inode فایل اصلی | inode جدا |
| بعد از حذف فایل اصلی | سالم می‌ماند و محتوا نمایش داده می‌شود | شکسته می‌شود و خطا می‌دهد |





## تکلیف شماره ۳

### سویچ حذف اجباری و بدون تأیید در `rm`

```bash
man rm
```

سویچ پیدا شده:

```
-f, --force
       ignore nonexistent files and arguments, never prompt
```

سویچ **`-f`** فایل را اجباری و بدون پرسیدن تأیید حذف می‌کند.

مثال:

```bash
rm -f file1.txt
```

**هشدار:** `rm` سطل بازیافت ندارد و فایل حذف‌شده برنمی‌گردد. ترکیب `-f` با `-r` (یعنی `rm -rf`) بسیار خطرناک است و باید با احتیاط استفاده شود.




