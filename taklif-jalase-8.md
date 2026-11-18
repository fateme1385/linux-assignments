# تمرین: کامپایل و لینک خودکار دو فایل C با استفاده از Makefile

## ۱. ابزارهای موردنیاز

برای انجام این پروژه ابزارهای زیر را دریافت و نصب کردم:

- **GCC:** برای کامپایل فایل‌های زبان C
- **GNU Make:** برای خودکارسازی فرایند کامپایل و لینک
- **libc6-dev:** برای دسترسی به فایل‌های Header استاندارد C مانند `stdio.h`

## ۲. کد فایل‌های C

ابتدا دو فایل C در نظر گرفتم که هرکدام بخشی از برنامه را تشکیل می‌دهند.

### فایل اول: main.c

در این فایل تابع اصلی `main` را نوشتم و تابع `say_hello` را که در فایل دوم تعریف شده است، فراخوانی کردم.

```c
#include <stdio.h>

void say_hello();

int main() {
    say_hello();
    printf("This is the main file.\n");
    return 0;
}
```

### فایل دوم: message.c

در این فایل تابع `say_hello` را تعریف کردم که یک پیام را چاپ می‌کند.

```c
#include <stdio.h>

void say_hello() {
    printf("Hello from the second file!\n");
}
```

## ۳. نوشتن Makefile

برای خودکارسازی مراحل کامپایل و لینک، فایل `Makefile` را با دستورات زیر نوشتم:

```makefile
all: program

main.o: main.c
	gcc -c main.c -o main.o

message.o: message.c
	gcc -c message.c -o message.o

program: main.o message.o
	gcc main.o message.o -o program

clean:
	rm -f *.o program
```

### توضیح بخش‌های Makefile

- `all`: هدف اصلی اجرای Make است و باعث شروع فرایند ساخت برنامه می‌شود.
- `main.o`: فایل `main.c` را کامپایل کرده و فایل Object آن را تولید می‌کند.
- `message.o`: فایل `message.c` را کامپایل کرده و فایل Object آن را تولید می‌کند.
- `program`: دو فایل Object را به یکدیگر لینک کرده و فایل اجرایی نهایی را ایجاد می‌کند.
- `clean`: فایل‌های Object و فایل اجرایی را حذف می‌کند.

نکته: قبل از دستورات اجرایی در Makefile از کلید Tab استفاده کردم.

## ۴. اجرای Makefile و رفع خطای اولیه

برای اجرای مراحل کامپایل و لینک، دستور زیر را اجرا کردم:

```bash
make
```

در اجرای اولیه با خطای زیر مواجه شدم:

```text
gcc -c main.c -o main.o
main.c:1:10: fatal error: stdio.h: No such file or directory
    1 | #include <stdio.h>
      |          ^~~~~~~~~
compilation terminated.
make: *** [Makefile:4: main.o] Error 1
```

علت خطا، نصب نبودن فایل Header مربوط به کتابخانه استاندارد ورودی و خروجی C یعنی `stdio.h` بود.

برای رفع این مشکل، بسته `libc6-dev` را نصب کردم و مجدداً دستور `make` را اجرا کردم.

## ۵. کامپایل و لینک موفقیت‌آمیز

پس از رفع خطا، دستور زیر را دوباره اجرا کردم:

```bash
make
```

خروجی:

```text
gcc -c main.c -o main.o
gcc -c message.c -o message.o
gcc main.o message.o -o program
```

در این مرحله Make به‌صورت خودکار:

1. فایل `main.c` را به `main.o` تبدیل کرد.
2. فایل `message.c` را به `message.o` تبدیل کرد.
3. دو فایل Object را به یکدیگر لینک کرد و فایل اجرایی `program` را ساخت.

## ۶. بررسی فایل‌های خروجی

برای بررسی فایل‌های ایجادشده، دستور زیر را اجرا کردم:

```bash
ls -l
```

خروجی:

```text
total 36
-rw-r--r-- 1 hp hp   194 Nov 18 10:03 Makefile
-rw-r--r-- 1 hp hp   125 Nov 18 10:01 main.c
-rw-r--r-- 1 hp hp  1568 Nov 18 10:06 main.o
-rw-r--r-- 1 hp hp    86 Nov 18 10:02 message.c
-rw-r--r-- 1 hp hp  1512 Nov 18 10:06 message.o
-rwxr-xr-x 1 hp hp 16016 Nov 18 10:06 program
```

همان‌طور که در خروجی مشاهده می‌شود، فایل‌های Object و فایل اجرایی با موفقیت ایجاد شدند.

## ۷. اجرای برنامه نهایی

در آخر، برای اجرای فایل اجرایی تولیدشده، دستور زیر را وارد کردم:

```bash
./program
```

خروجی:

```text
Hello from the second file!
This is the main file.
```

## نتیجه‌گیری

در این تمرین با استفاده از Makefile، فرایند کامپایل دو فایل C و لینک کردن آن‌ها را خودکار کردم.

ابتدا هرکدام از فایل‌های C را به یک فایل Object تبدیل کردم و سپس با لینک کردن این دو فایل، فایل اجرایی نهایی را ساختم.

در نتیجه، توانستم با اجرای تنها یک دستور `make` تمام مراحل کامپایل و لینک را به‌صورت خودکار انجام دهم.
