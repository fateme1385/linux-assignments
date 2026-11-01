# linux-assignment

## تکلیف اول

### ۱. نمایش مسیر فعلی

```bash
pwd
```

خروجی:

```
/home/ubuntu
```

### ۲. رفتن به دایرکتوری etc و بررسی مسیر

```bash
cd /etc
pwd
```

خروجی:

```
/etc
```

### ۳. نمایش لیست کامل فایل‌ها (شامل فایل‌های مخفی)

```bash
ls -la
```

بخشی از خروجی:

```
total 404
drwxr-xr-x  1 root                 root                   680 Nov  1 11:00 .
drwxr-xr-x  1 root                 root                   260 Nov  1 10:45 ..
...
```

### ۴. بازگشت به دایرکتوری home

```bash
cd ~
pwd
```

خروجی:

```
/home/ubuntu
```






SORT(1)                     General Commands Manual                     SORT(1)

NAME
       sort  -  Display  sorted  concatenation of all FILE(s). With no FILE, or
       when FILE is -, read standard input.

SYNOPSIS
       sort    [--help]    [--version]    [--sort]    [-h|--human-numeric-sort]
       [-M|--month-sort]     [-n|--numeric-sort]    [-g|--general-numeric-sort]
       [-V|--version-sort] [-R|--random-sort]  [--random-source]  [-d|--dictio‐
       nary-order]   [-m|--merge]  [-c|--check]  [-C|--check-silent]  [-f|--ig‐
       nore-case]    [-i|--ignore-nonprinting]     [-b|--ignore-leading-blanks]
       [-o|--output]   [-r|--reverse]  [-s|--stable]  [-u|--unique]  [-k|--key]
       [-t|--field-separator]        [-z|--zero-terminated]        [--parallel]
       [-S|--buffer-size]    [-T|--temporary-directory]    [--compress-program]
       [--batch-size] [--files0-from] [--debug] [files]

DESCRIPTION
       Display sorted concatenation of all FILE(s). With no FILE, or when  FILE
       is -, read standard input.

OPTIONS
       --help Print help information.
 Manual page sort(1) line 1 (press h for help or q to quit)

