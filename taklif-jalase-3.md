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
