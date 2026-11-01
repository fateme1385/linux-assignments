## تکلیف سوم

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
