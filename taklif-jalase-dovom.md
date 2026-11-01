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
ubuntu@ubuntu:~$ 
