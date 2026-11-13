## تکلیف شماره ۱

### سویچ جایگزین `grep | wc -l` در `grep`

دستور `wc -l` تعداد خطوط را می‌شمارد. پس داخل `man grep` به دنبال کلمه‌ای مربوط به «شمردن» گشتم:

```bash
man grep
```

داخل صفحه راهنما کلید `/` را زدم، کلمه `count` را نوشتم و Enter زدم. خط زیر پیدا شد:

```
-c, --count
       Suppress normal output; instead print a count of matching lines
       for each input file.
```

چون سویچ **`-c`** به‌جای نمایش خطوط، تعداد خطوطِ منطبق را چاپ می‌کند، همان کار `grep | wc -l` را انجام می‌دهد.

```bash
grep -c root /etc/passwd
```

که معادل است با:

```bash
grep root /etc/passwd | wc -l
```
## تکلیف شماره 2
### جست‌وجوی فایل‌های `.conf` در `/etc` با `find`

```bash
find /etc -name "*.conf"
```

بخشی از خروجی:

```
/etc/NetworkManager/NetworkManager.conf
/etc/NetworkManager/conf.d/default-wifi-powersave-on.conf
/etc/PackageKit/PackageKit.conf
/etc/PackageKit/Vendor.conf
/etc/UPower/UPower.conf
/etc/adduser.conf
/etc/alsa/conf.d/50-pipewire.conf
/etc/alsa/conf.d/99-pipewire-default.conf
/etc/apparmor/parser.conf
/etc/apport/crashdb.conf
...
```

`find` به‌صورت پیش‌فرض بازگشتی است و زیرشاخه‌های `/etc` را هم می‌گردد. سویچ `-name "*.conf"` فقط فایل‌هایی را که نامشان به `.conf` ختم می‌شود انتخاب می‌کند. پیام‌های `Permission denied` مربوط به پوشه‌هایی است که کاربر عادی اجازه خواندنشان را ندارد.



## تکلیف شماره 3
## سوال: چاپ خطوط ۱۰۰۰ تا ۱۰۱۰ فایل data.csv

**هدف:** با ترکیب `head` و `tail` و پایپ (`|`)، فقط خطوط ۱۰۰۰ تا ۱۰۱۰ فایل چاپ شود.

### جستجوی فایل

ابتدا سعی کردم فایل `data.csv` را در پوشه‌های Downloads، Desktop و Documents پیدا کنم. فایل در این پوشه‌ها وجود نداشت و دستور روی آن با خطا مواجه شد:

```bash
head -n 1010 data.csv | tail -n 11
```

```text
head: cannot open 'data.csv' for reading: No such file or directory
```

### ساخت فایل نمونه

چون فایل اصلی در دسترس نبود، برای تست یک فایل نمونه با ۵۰۰۰ خط ساختم. دستور `seq` اعداد ۱ تا ۵۰۰۰ را هر کدام در یک خط می‌نویسد، پس شماره هر خط با مقدار آن برابر است و درستی خروجی راحت بررسی می‌شود:

```bash
cd ~/projects
seq 1 5000 > data.csv
```

### راه‌حل

```bash
head -n 1010 data.csv | tail -n 11
```

**توضیح:**
- `head -n 1010` ۱۰۱۰ خط اول فایل را جدا می‌کند.
- `|` خروجی `head` را به‌عنوان ورودی به `tail` می‌دهد.
- `tail -n 11` از آن ۱۰۱۰ خط، فقط ۱۱ خط آخر را نگه می‌دارد. تعداد خطوط از ۱۰۰۰ تا ۱۰۱۰ برابر ۱۱ است (۱۰۱۰ − ۱۰۰۰ + ۱).

**خروجی:**

```text
1000
1001
1002
1003
1004
1005
1006
1007
1008
1009
1010
```

### بررسی تعداد خطوط

برای اطمینان از اینکه دقیقاً ۱۱ خط چاپ شده، خروجی را به `wc -l` دادم:

```bash
head -n 1010 data.csv | tail -n 11 | wc -l
```

```text
11
```

**نتیجه:** فقط خطوط ۱۰۰۰ تا ۱۰۱۰ چاپ شد و تعداد آن‌ها ۱۱ است، که با خواسته سوال مطابقت دارد.
