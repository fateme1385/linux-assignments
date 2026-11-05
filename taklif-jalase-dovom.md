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
#### تکلیف دوم

### هارد لینک و سافت لینک

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

### نتیجه

- **هارد لینک:** محتوا (`Hello`) همچنان نمایش داده می‌شود، چون هارد لینک نام دیگری برای همان inode (`15935`) است و با حذف `info.txt` داده باقی می‌ماند.
- **سافت لینک:** خطای `No such file or directory` می‌دهد، چون فقط مسیر `info.txt` را نگه می‌دارد و با حذف آن شکسته (dangling) می‌شود.

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




