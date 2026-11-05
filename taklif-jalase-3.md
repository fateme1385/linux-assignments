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
