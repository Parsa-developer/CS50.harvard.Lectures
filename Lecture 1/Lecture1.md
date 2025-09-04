### خوش آمدید!
<div dir="rtl" style="text-align: right;">

- در جلسه‌ی قبلی، درباره‌ی Scratch یاد گرفتیم؛ یک زبان برنامه‌نویسی تصویری.
- در واقع، تمام مفاهیم پایه‌ای برنامه‌نویسی که در Scratch معرفی شدند، در هنگام یادگیری هر زبان برنامه‌نویسی دیگری نیز مورد استفاده قرار می‌گیرند. توابع (functions)، شرط‌ها (conditionals)، حلقه‌ها (loops) و متغیرها (variables) بلوک‌های سازنده‌ی اصلی هستند که در همه زبان‌های برنامه‌نویسی وجود دارند.
- به یاد داشته باشید که ماشین‌ها فقط زبان باینری را می‌فهمند. در حالی که انسان‌ها کد منبع (source code) می‌نویسند (دستوراتی قابل‌خواندن برای انسان)، کامپیوترها فقط چیزی را می‌فهمند که به آن کد ماشین (machine code) می‌گوییم؛ یعنی الگوهایی از صفر و یک که باعث ایجاد رفتار موردنظر می‌شوند.  
- ما می‌توانیم کد منبع را با استفاده از نرم‌افزاری به نام کامپایلر (compiler) به کد ماشین تبدیل کنیم. امروز با کامپایلری آشنا می‌شوید که کد منبع نوشته‌شده به زبان C را به کد ماشین تبدیل می‌کند.  
- امروز علاوه بر یادگیری برنامه‌نویسی، یاد می‌گیریم چگونه کد خوب بنویسیم.  

---

### Visual Studio Code برای CS50

- ویرایشگر متنی که در این دوره استفاده می‌کنیم Visual Studio Code یا همان VS Code است که با نام cs50.dev هم شناخته می‌شود و از طریق همان آدرس قابل دسترسی است.  
- یکی از مهم‌ترین دلایل استفاده از VS Code این است که همه‌ی نرم‌افزارهای لازم برای این دوره، از پیش روی آن نصب شده‌اند. این دوره و دستورالعمل‌های آن بر اساس VS Code طراحی شده‌اند.  
- نصب دستی نرم‌افزارهای مورد نیاز روی کامپیوتر شخصی شما بسیار دشوار است. بنابراین بهترین کار استفاده از VS Code برای انجام تمرین‌های این دوره است.  
- شما می‌توانید VS Code را در cs50.dev باز کنید.
- کامپایلر را می‌توان به چندین بخش تقسیم کرد:

![vscode for cs50](https://cs50.harvard.edu/x/notes/1/cs50Week1Slide017.png)

---

### اجزای محیط IDE

در سمت چپ محیط، یک File Explorer می‌بینید که فایل‌های شما در آن نمایش داده می‌شوند. در وسط، بخشی به نام Text Editor وجود دارد که می‌توانید کدهای خود را در آن ویرایش کنید. در پایین نیز یک Command Line Interface (CLI) یا Terminal دارید که می‌توانید از آن برای اجرای دستورها استفاده کنید.

- در پنجره ترمینال، برخی از آرگومان‌های command-line رایج که ممکن است استفاده کنیم عبارتند از:
    - cd # تغییر پوشه جاری
    - cp # کپی کردن فایل یا پوشه
    - ls # نمایش لیست فایل‌ها
    - mkdir # ساخت پوشه جدید
    - mv # جابه‌جا یا تغییر نام
    - rm # حذف فایل
    - rmdir # حذف پوشه

- رایج‌ترین دستور مورد استفاده ls است که تمام فایل‌های موجود در دایرکتوری فعلی را فهرست می‌کند. در پنجره ترمینال ls را تایپ کنید و Enter را بزنید. تمام فایل‌های موجود در پوشه فعلی را مشاهده خواهید کرد.
- از آنجا که این IDE با تمام نرم‌افزارهای لازم از پیش پیکربندی شده است، باید از آن برای تکمیل تمام تکالیف این دوره استفاده کنید.

---

### Hello World

برای نوشتن، کامپایل و اجرای اولین برنامه از سه دستور استفاده می‌کنیم:  
</div>

```
code hello.c
make hello
./hello
```

<div dir="rtl" style="text-align: right;">

- دستور اول فایل `hello.c` را ایجاد کرده و امکان نوشتن کد در آن را فراهم می‌کند.  
- دستور دوم فایل را کامپایل کرده و یک فایل اجرایی به نام `hello` می‌سازد.  
- دستور سوم برنامه‌ی `hello` را اجرا می‌کند.

---

### نوشتن اولین برنامه

ما می‌توانیم اولین برنامه شما را به زبان C با تایپ کد hello.c در پنجره ترمینال بسازیم. توجه داشته باشید که ما عمداً کل نام فایل را با حروف کوچک نوشته‌ایم و پسوند c. را نیز گنجانده‌ایم.
سپس، در ویرایشگر متنی که ظاهر می‌شود، کد را به صورت زیر بنویسید: 
</div>

```c
// A program that says hello to the world

#include <stdio.h>

int main(void)
{
    printf("hello, world\n");
}
```
<div dir="rtl" style="text-align: right;">

هر کاراکتر این کد اهمیت دارد. اگر اشتباه تایپ کنید، برنامه اجرا نخواهد شد. تابع `printf` یک خط متن چاپ می‌کند. `\n` هم خط جدید ایجاد می‌کند.
با دستور زیر برنامه کامپایل می‌شود:

make hello<br>
سپس با دستور زیر اجرا می‌شود:
./hello<br>

### از Scratch به C 

- در Scratch از بلوک `say` برای نمایش متن استفاده می‌کردیم. در C از تابع `printf` استفاده می‌کنیم. 

</div>

```
printf("hello, world\n");
```
<div dir="rtl" style="text-align: right;">

اگر `n\` را حذف کنیم: </div>

```
printf("hello, world");
```

### اجرای برنامه و کاراکترهای escape
<div dir="rtl" style="text-align: right;">

در پنجره‌ی ترمینال خود، دستور `make hello` را اجرا کنید. سپس با تایپ `./hello` در پنجره‌ی ترمینال، چه تغییری در برنامه‌ی شما ایجاد شد؟  

این کاراکتر `\` یک کاراکتر escape نامیده می‌شود که به کامپایلر می‌گوید `n\` یک دستور ویژه برای ایجاد خط جدید است.  

کاراکترهای escape دیگری هم وجود دارند که می‌توانید استفاده کنید:
</div>

```
\n ایجاد خط جدید
\r برگشت به اول خط
\" چاپ double quote
\' چاپ single quote
\\ چاپ بک اسلش
```

<div dir="rtl" style="text-align: right;">
 برنامه‌ی خود را به حالت زیر بازگردانید: </div>
 
```c 
// A program that says hello to the world

#include <stdio.h>

int main(void)
{
    printf("hello, world\n");
}
```
<div dir="rtl" style="text-align: right;">

دقت کنید که نقطه‌ویرگول (semicolon) و `n\` دوباره در کد قرار گرفته‌اند.

---
 ### Header Files و راهنمای CS50

دستور `#include <stdio.h>` در ابتدای کد یک دستور بسیار ویژه است که به کامپایلر می‌گوید می‌خواهید از قابلیت‌های کتابخانه‌ای به نام `stdio.h` استفاده کنید که یک header file است. این کار به شما اجازه می‌دهد (در کنار بسیاری امکانات دیگر) از تابع `printf` استفاده کنید. کتابخانه در واقع مجموعه‌ای از کدی است که توسط شخص دیگری نوشته شده است. کتابخانه‌ها مجموعه‌ای از کدها و توابع آماده هستند که دیگران قبلاً نوشته‌اند و ما می‌توانیم در برنامه‌ی خودمان از آن‌ها استفاده کنیم. شما می‌توانید تمام قابلیت‌های این کتابخانه را در Manual Pages بخوانید. Manual Pages راهی برای درک بهتر دستورات مختلف و عملکرد آن‌ها هستند. جالب است بدانید که CS50 کتابخانه‌ی مخصوص به خودش را دارد به نام `cs50.h`. در این کتابخانه توابع زیادی وجود دارند که مثل «چرخ کمکی» به شما کمک می‌کنند وقتی تازه کار با C را شروع کرده‌اید: </div>

```
get_char
get_double
get_float
get_int
get_long
get_string
``` 
<div dir="rtl" style="text-align: right;"> بیایید از این کتابخانه در برنامه‌ی خود استفاده کنیم. </div>

### Hello, You

```c
#include <cs50.h>
#include <stdio.h>

int main(void)
{
    string answer = get_string("What's your name? ");
    printf("hello, %s\n", answer);
}
```
<div dir="rtl" style="text-align: right;">

در اینجا `s%` یک placeholder است که مقدار رشته‌ای answer را در خود قرار می‌دهد.
انواع داده (Types)

برخی از format code های مهم:
- `s%` برای string
- `i%` برای int
- `f%` برای float
- `c%` برای char
- `li%` برای long

و انواع داده‌ای که استفاده می‌کنیم:

- bool
- char
- float
- int
- long
- string

### شرط‌ها (Conditionals)

- یکی دیگر از بلوک‌های سازنده‌ای که در اسکرچ استفاده کردید، شرط‌ها بودند. برای مثال، ممکن است بخواهید اگر x از y بزرگتر باشد، یک کار انجام دهید. علاوه بر این، اگر آن شرط برقرار نباشد، ممکن است بخواهید کار دیگری انجام دهید.
- به چند مثال از اسکرچ نگاهی می‌اندازیم.
- در زبان C، می‌توانید دو مقدار را به صورت زیر مقایسه کنید:

```c
if (x < y)
{
    printf("x is less than y\n");
}
else
{
    printf("x is not less than y\n");
}
```
```c
if (x < y)
{ ... }
else if (x > y)
{ ... }
else
{ ... }
```
عملگرها (Operators)
<div dir="rtl" style="text-align: right;">

- `+` جمع
- `-` تفریق
- `*` ضرب
- `/` تقسیم
- `%` باقیمانده تقسیم

### متغیرها (Variables)
در زبان C می‌توانید یک مقدار را به یک متغیر از نوع `int` یا همان عدد صحیح اختصاص دهید به این صورت:
</div>

```c
int counter = 0;
```
<div dir="rtl" style="text-align: right;">

دقت کنید که یک متغیر به نام `counter` از نوع `int` مقدار 0 گرفته است.
همچنین می‌توان برنامه‌ریزی کرد که یک واحد به counter اضافه شود:

</div>

```c
counter = counter + 1;
```
<div dir="rtl" style="text-align: right;">

در اینجا مقدار 1 به متغیر `counter` اضافه شده است.
این دستور می‌تواند به شکل زیر هم نوشته شود:

</div>

```c
counter += 1;
```
<div dir="rtl" style="text-align: right;"> و باز هم می‌توان ساده‌ترش کرد: </div>

```c
counter++;
```
<div dir="rtl" style="text-align: right;">

اینجا از `++` برای اضافه کردن 1 استفاده شده است.
همچنین می‌توانید یک واحد از counter کم کنید:

</div>

```c
counter--;
```
<div dir="rtl" style="text-align: right;">

در این حالت مقدار 1 از متغیر `counter` کم می‌شود. </div>

```
compare.c
```
<div dir="rtl" style="text-align: right;"> با استفاده از این دانش تازه درباره‌ی انتساب مقادیر به متغیرها، می‌توانید اولین دستور شرطی خود را بنویسید.
در پنجره‌ی ترمینال، تایپ کنید code compare.c و کدی مثل زیر بنویسید:

</div>

```c
// Conditional, Boolean expression, relational operator

#include <cs50.h>
#include <stdio.h>

int main(void)
{
    // Prompt user for integers
    int x = get_int("What's x? ");
    int y = get_int("What's y? ");

    // Compare integers
    if (x < y)
    {
        printf("x is less than y\n");
    }
}
```
<div dir="rtl" style="text-align: right;">

دقت کنید که دو متغیر ساخته‌ایم: یک عدد صحیح به نام `x` و دیگری `y`. این مقادیر توسط تابع `get_int` گرفته می‌شوند.
برای اجرای برنامه کافی است در ترمینال دستور make compare و سپس ./compare را اجرا کنید. اگر پیغام خطا دیدید، کدتان را بررسی کنید.

نمودارهای جریان (Flow charts) راهی برای بررسی عملکرد یک برنامه‌ی کامپیوتری هستند و می‌توانند برای بررسی کارایی کد ما استفاده شوند.

اگر به نمودار جریان این کد نگاه کنید، متوجه برخی کاستی‌ها خواهید شد. می‌توانیم برنامه را بهبود بدهیم:

</div>

```c
// Conditionals

#include <cs50.h>
#include <stdio.h>

int main(void)
{
    // Prompt user for integers
    int x = get_int("What's x? ");
    int y = get_int("What's y? ");

    // Compare integers
    if (x < y)
    {
        printf("x is less than y\n");
    }
    else if (x > y)
    {
        printf("x is greater than y\n");
    }
    else
    {
        printf("x is equal to y\n");
    }
}
```
<div dir="rtl" style="text-align: right;"> اکنون تمام حالت‌های ممکن پوشش داده شده‌اند.
می‌توانید دوباره برنامه را کامپایل (make) و اجرا کنید و آن را آزمایش کنید.

با بررسی این برنامه روی یک نمودار جریان، می‌توانید کارایی تصمیمات طراحی کدتان را بهتر ببینید.

agree.c

با در نظر گرفتن نوع داده‌ای به نام `char` می‌توانیم برنامه‌ی جدیدی آغاز کنیم. در ترمینال تایپ کنید `code agree.c`.
در حالی که string مجموعه‌ای از کاراکترهاست، char فقط یک کاراکتر منفرد است.

کدی مثل زیر بنویسید:

</div>

```c
// Comparing against lowercase char

#include <cs50.h>
#include <stdio.h>

int main(void)
{
    // Prompt user to agree
    char c = get_char("Do you agree? ");

    // Check whether agreed
    if (c == 'y')
    {
        printf("Agreed.\n");
    }
    else if (c == 'n')
    {
        printf("Not agreed.\n");
    }
}
```
<div dir="rtl" style="text-align: right;">

توجه کنید که برای کاراکترها از علامت نقل قول تکی (') استفاده می‌کنیم. همچنین `==` برای بررسی برابری است، در حالی که یک علامت مساوی تنها (=) کاربرد کاملاً متفاوتی در C دارد.
می‌توانید برنامه را با دستور make agree و سپس ./agree آزمایش کنید.

حالا اجازه دهیم ورودی هم حروف کوچک و هم بزرگ را قبول کند:

</div>

```c
// Comparing against lowercase and uppercase char

#include <cs50.h>
#include <stdio.h>

int main(void)
{
    // Prompt user to agree
    char c = get_char("Do you agree? ");

    // Check whether agreed
    if (c == 'y')
    {
        printf("Agreed.\n");
    }
    else if (c == 'Y')
    {
        printf("Agreed.\n");
    }
    else if (c == 'n')
    {
        printf("Not agreed.\n");
    }
    else if (c == 'N')
    {
        printf("Not agreed.\n");
    }
}
```
<div dir="rtl" style="text-align: right;"> می‌بینید که گزینه‌های بیشتری اضافه کردیم. اما این کد چندان بهینه نیست.
می‌توانیم آن را بهتر کنیم:

</div>

```c
// Logical operators

#include <cs50.h>
#include <stdio.h>

int main(void)
{
    // Prompt user to agree
    char c = get_char("Do you agree? ");

    // Check whether agreed
    if (c == 'Y' || c == 'y')
    {
        printf("Agreed.\n");
    }
    else if (c == 'N' || c == 'n')
    {
        printf("Not agreed.\n");
    }
}
```
<div dir="rtl" style="text-align: right;">

در اینجا عملگر `||` به معنای «یا» است.

### حلقه‌ها و meow.c
ما می‌توانیم از بلوک ساخت حلقه در Scratch در برنامه‌های C خود نیز استفاده کنیم.  

در ترمینال تایپ کنید `code meow.c` و کدی مثل زیر بنویسید:
</div>

```c
// Opportunity for better design

#include <stdio.h>

int main(void)
{
    printf("meow\n");
    printf("meow\n");
    printf("meow\n");
}
```

<div dir="rtl" style="text-align: right;"> این کد کار موردنظر را انجام می‌دهد اما طراحی بهتری می‌تواند داشته باشد چون کد بارها تکرار شده است.
می‌توانیم برنامه را اینطور بهبود بدهیم:

</div>

```c
// Better design

#include <stdio.h>

int main(void)
{
    int i = 3;
    while (i > 0)
    {
        printf("meow\n");
        i--;
    }
}
```

<div dir="rtl" style="text-align: right;">

اینجا یک عدد صحیح به نام `i` تعریف کردیم و مقدار 3 به آن دادیم. سپس یک حلقه‌ی `while` ساختیم که تا وقتی `i > 0` باشد اجرا می‌شود. هر بار مقدار `i--` یک واحد از `i` کم می‌کند.
همچنین می‌توانیم شمارش رو به بالا هم داشته باشیم:

</div>

```c
// Print values of i

#include <stdio.h>

int main(void)
{
    int i = 1;
    while (i <= 3)
    {
        printf("meow\n");
        i++;
    }
}
```
<div dir="rtl" style="text-align: right;">

در این حالت شمارنده از 1 شروع می‌شود. در هر بار اجرای حلقه، مقدار `i` یک واحد زیاد می‌شود و وقتی از 3 بیشتر شد، حلقه متوقف می‌شود.
به طور کلی در علوم کامپیوتر شمارش از صفر شروع می‌شود. بهتر است کد را اینطور بازنویسی کنیم:

</div>

```c
// Better design

#include <stdio.h>

int main(void)
{
    int i = 0;
    while (i < 3)
    {
        printf("meow\n");
        i++;
    }
}
```
<div dir="rtl" style="text-align: right;"> اکنون شمارش از صفر شروع می‌شود.
استفاده از for loop

ابزار دیگری که برای حلقه‌ها داریم، `for loop` است. می‌توانیم طراحی `meow.c` را با آن بهتر کنیم: </div>

```c
// Better design

#include <stdio.h>

int main(void)
{
    for (int i = 0; i < 3; i++)
    {
        printf("meow\n");
    }
}
```
<div dir="rtl" style="text-align: right;">

حلقه‌ی `for` شامل سه بخش است: 1. مقداردهی اولیه شمارنده: `int i = 0` 2. شرط بررسی: `i < 3` 3. افزایش شمارنده: `i++`
حلقه‌ی بی‌نهایت
</div>

```c
// Infinite loop

#include <cs50.h>
#include <stdio.h>

int main(void)
{
    while (true)
    {
        printf("meow\n");
    }
}
```
<div dir="rtl" style="text-align: right;">

در اینجا `true` همیشه برقرار است. بنابراین برنامه بی‌پایان اجرا می‌شود. در این حالت کنترل ترمینال را از دست خواهید داد. برای شکستن حلقه‌ی بی‌نهایت می‌توانید کلیدهای <kbd>Ctrl</kbd> + <kbd>C</kbd> را بزنید.
توابع (Functions)
می‌توانیم توابع خودمان را در C تعریف کنیم. مثال: </div>

```c
void meow(void)
{
    printf("meow\n");
}
```
<div dir="rtl" style="text-align: right;">

کلمه‌ی `void` در ابتدا یعنی این تابع مقدار برنمی‌گرداند. و `(void)` یعنی این تابع هیچ ورودی نمی‌گیرد.
می‌توانیم در تابع main از آن استفاده کنیم:

</div>

```c
// Abstraction

#include <stdio.h>

void meow(void);

int main(void)
{
    for (int i = 0; i < 3; i++)
    {
        meow();
    }
}

// Meow once
void meow(void)
{
    printf("meow\n");
}
```
<div dir="rtl" style="text-align: right;">

اینجا تابع `meow()` صدا زده می‌شود. این امکان وجود دارد چون نمونه‌ی اولیه (prototype) آن در بالای کد تعریف شده است.
پارامتر در توابع
</div>

```c
// Abstraction with parameterization

#include <stdio.h>

void meow(int n);

int main(void)
{
    meow(3);
}

// Meow some number of times
void meow(int n)
{
    for (int i = 0; i < n; i++)
    {
        printf("meow\n");
    }
}
```
<div dir="rtl" style="text-align: right;">

اینجا نمونه‌ی اولیه تابع تغییر کرده به `void meow(int n)` تا نشان دهد ورودی از نوع `int` می‌گیرد. </div>
گرفتن ورودی از کاربر
```c
// User input

#include <cs50.h>
#include <stdio.h>

void meow(int n);

int main(void)
{
    int n;
    do
    {
        n = get_int("Number: ");
    }
    while (n < 1);
    meow(n);
}

// Meow some number of times
void meow(int n)
{
    for (int i = 0; i < n; i++)
    {
        printf("meow\n");
    }
}
```
<div dir="rtl" style="text-align: right;">

اینجا با استفاده از `get_int` از کاربر ورودی گرفته می‌شود. مقدار ورودی `n` به تابع `meow` داده می‌شود. </div>
تابع با مقدار بازگشتی
```c
// Return value

#include <cs50.h>
#include <stdio.h>

int get_positive_int(void);
void meow(int n);

int main(void)
{
    int n = get_positive_int();
    meow(n);
}

// Get number of meows
int get_positive_int(void)
{
    int n;
    do
    {
        n = get_int("Number: ");
    }
    while (n < 1);
    return n;
}

// Meow some number of times
void meow(int n)
{
    for (int i = 0; i < n; i++)
    {
        printf("meow\n");
    }
}
```
<div dir="rtl" style="text-align: right;">

اینجا یک تابع جدید به نام `get_positive_int` داریم که از کاربر یک عدد صحیح می‌خواهد و تا وقتی مقدار مثبت نباشد دوباره سؤال می‌پرسد. وقتی ورودی درست گرفت، مقدار `n` را به تابع `main` بازمی‌گرداند.

# Correctness, Design, Style

کد را می‌توان بر اساس سه محور ارزیابی کرد.  
اول، **درستی (correctness)** به این معناست که «آیا کد همان‌طور که در نظر گرفته شده اجرا می‌شود؟» می‌توانید درستی کد خود را با `check50` بررسی کنید.  
دوم، **طراحی (design)** به این معناست که «کد چقدر خوب طراحی شده است؟» می‌توانید طراحی کد خود را با `design50` ارزیابی کنید.  
در نهایت، **سبک (style)** به این معناست که «کد از نظر زیبایی و یکنواختی چقدر قابل قبول است؟» می‌توانید سبک کد خود را با `style50` بررسی کنید.  

---

# Mario

هرآنچه تاکنون آموختیم به بلوک‌های سازنده‌ی کار شما به عنوان یک دانشمند علوم کامپیوتر نوظهور مربوط می‌شود.  
حال پرسش این است: چگونه باید به یک مسئله‌ی مرتبط با علوم کامپیوتر نزدیک شویم؟  
تصور کنید می‌خواهیم نمایی از بازی **Super Mario Bros** را شبیه‌سازی کنیم. به‌ویژه چهار بلاک علامت سؤال را. چگونه می‌توانیم کدی بنویسیم که این چهار بلاک افقی را نمایش دهد؟  
</div>

![mario first](https://cs50.harvard.edu/x/notes/1/cs50Week1Slide123.png)

```c
// Prints a row of 4 question marks with a loop

#include <stdio.h>

int main(void)
{
    for (int i = 0; i < 4; i++)
    {
        printf("?");
    }
    printf("\n");
}
```
<div dir="rtl" style="text-align: right;">
در اینجا چهار علامت سؤال با استفاده از یک حلقه چاپ می‌شود. </div>

![mario second](https://cs50.harvard.edu/x/notes/1/cs50Week1Slide125.png)

Vertical Blocks
```c
// Prints a column of 3 bricks with a loop

#include <stdio.h>

int main(void)
{
    for (int i = 0; i < 3; i++)
    {
        printf("#\n");
    }
}
```
<div dir="rtl" style="text-align: right;"> در این مثال، سه آجر عمودی چاپ می‌شود. </div>

![mario third](https://cs50.harvard.edu/x/notes/1/cs50Week1Slide127.png)

Nested Loops (3x3 Grid)
```c
// Prints a 3-by-3 grid of bricks with nested loops

#include <stdio.h>

int main(void)
{
    for (int i = 0; i < 3; i++)
    {
        for (int j = 0; j < 3; j++)
        {
            printf("#");
        }
        printf("\n");
    }
}
```
<div dir="rtl" style="text-align: right;">

این کد با استفاده از **حلقه‌های تو در تو**، یک شبکه‌ی سه در سه از آجرها چاپ می‌کند. </div>
Constants
```c
// Prints a 3-by-3 grid of bricks with nested loops using a constant

#include <stdio.h>

int main(void)
{
    const int n = 3;
    for (int i = 0; i < n; i++)
    {
        for (int j = 0; j < n; j++)
        {
            printf("#");
        }
        printf("\n");
    }
}
```
<div dir="rtl" style="text-align: right;">

این بار از یک مقدار ثابت `const int n = 3;` استفاده شده است. </div>
Helper Function
```c
// Helper function

#include <stdio.h>

void print_row(int width);
  
int main(void)
{
    const int n = 3;
    for (int i = 0; i < n; i++)
    {
        print_row(n);
    }
}

void print_row(int width)
{
    for (int i = 0; i < width; i++)
    {
        printf("#");
    }
    printf("\n");
}
```
<div dir="rtl" style="text-align: right;">

این کد وظیفه چاپ یک ردیف را به تابع `print_row` واگذار کرده است. </div>
Comments
```c
// Helper function

#include <stdio.h>

void print_row(int width);
  
int main(void)
{
    const int n = 3;

    // Print n rows
    for (int i = 0; i < n; i++)
    {
        print_row(n);
    }
}

void print_row(int width)
{
    for (int i = 0; i < width; i++)
    {
        printf("#");
    }
    printf("\n");
}
```
<div dir="rtl" style="text-align: right;">

نظرات (comments) با `//` شروع می‌شوند و توضیحاتی درباره عملکرد بخش‌های مختلف کد ارائه می‌دهند. </div>
More About Operators
Addition
```c
// Addition with int

#include <cs50.h>
#include <stdio.h>

int main(void)
{
    // Prompt user for x
    int x = get_int("x: ");

    // Prompt user for y
    int y = get_int("y: ");

    // Add numbers
    int z = x + y;

    // Perform addition
    printf("%i\n", z);
}
```
Doubling a Number
```c
// int

#include <cs50.h>
#include <stdio.h>

int main(void)
{
    int dollars = 1;
    while (true)
    {
        char c = get_char("Here's $%i. Double it and give to next person? ", dollars);
        if (c == 'y')
        {
            dollars *= 2;
        }
        else
        {
            break;
        }
    }
    printf("Here's $%i.\n", dollars);
}
```
Using long
```c
// long

#include <cs50.h>
#include <stdio.h>

int main(void)
{
    long dollars = 1;
    while (true)
    {
        char c = get_char("Here's $%li. Double it and give to next person? ", dollars);
        if (c == 'y')
        {
            dollars *= 2;
        }
        else
        {
            break;
        }
    }
    printf("Here's $%li.\n", dollars);
}
```
Data Types
<div dir="rtl" style="text-align: right;">

برخی از انواع داده‌ای در C: - **bool** → مقادیر `true` یا `false` - **char** → یک کاراکتر واحد مانند `a` یا `2` - **double** → عدد اعشاری با دقت بالا - **float** → عدد اعشاری (ممکن است با خطای دقت همراه باشد) - **int** → اعداد صحیح تا محدوده خاصی - **long** → اعداد صحیح بزرگتر از int - **string** → رشته‌ای از کاراکترها </div>
Truncation
```c
// Division with ints, demonstrating truncation

#include <cs50.h>
#include <stdio.h>

int main(void)
{
    int x = get_int("x: ");
    int y = get_int("y: ");
    printf("%i\n", x / y);
}
```
<div dir="rtl" style="text-align: right;">

تقسیم دو عدد صحیح همیشه یک عدد صحیح می‌دهد (اعداد اعشاری حذف می‌شوند). </div>
Floats
```c
// Floats

#include <cs50.h>
#include <stdio.h>

int main(void)
{
    float x = get_float("x: ");
    float y = get_float("y: ");
    printf("%.50f\n", x / y);
}
```
<div dir="rtl" style="text-align: right;">

استفاده از `float` باعث می‌شود بخش اعشاری حفظ شود، اما باز هم می‌تواند با خطای دقت همراه باشد.

### جمعبندی

در این درس آموختید:
- چگونه اولین برنامه خود را در C بنویسید.
- چگونه  از خط فرمان استفاده کنید.
- درباره توابع از پیش تعریف‌شده در C. 
- نحوه استفاده از متغیرها، شرط‌ها و حلقه‌ها. 
- چگونه توابع خودتان را بسازید تا کدتان ساده‌تر و بهتر شود. 
- چگونه کد را از نظر درستی، طراحی و سبک ارزیابی کنید. 
- اهمیت اضافه کردن نظرات به کد. 
- چگونگی استفاده از انواع 
- داده و عملگرها و پیامدهای انتخاب آن‌ها.

تا چلسه بعدی خدا نگهدار!

</div>