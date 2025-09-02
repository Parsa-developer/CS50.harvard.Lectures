## خوش آمدید
<div dir="rtl" style="text-align: right;"> در هفته‌ی صفر، ایده‌ی یک <b>الگوریتم</b> را معرفی کردیم: یک جعبه‌سیاه که می‌تواند ورودی بگیرد و خروجی تولید کند. این هفته قرار است درکمان از الگوریتم‌ها را از طریق <b>pseudocode (شبه کد )</b> و سپس وارد <b>کد واقعی</b> گسترش دهیم. همچنین، به <b>کارایی الگوریتم‌ها</b> نیز توجه خواهیم کرد. در واقع، بر پایه‌ی مفاهیمی که هفته‌ی قبل گفتیم، یاد می‌گیریم چگونه الگوریتم‌ها را بسازیم و تحلیل کنیم. </div>

![chart 1](https://cs50.harvard.edu/x/notes/3/cs50Week3Slide010.png)

<div dir="rtl" style="text-align: right;"> وقتی وارد این هفته می‌شویم باید در نظر بگیریم که <b>روش کار یک الگوریتم با یک مسئله</b> تعیین می‌کند که حل آن چه‌قدر زمان می‌برد! الگوریتم‌ها می‌توانند به شکل بهینه‌تری طراحی شوند. امروز روی <b>طراحی الگوریتم‌ها</b> و <b>اندازه‌گیری کارایی آن‌ها</b> تمرکز می‌کنیم. </div>

## Linear Search
<div dir="rtl" style="text-align: right;"> هفته‌ی قبل، با ایده‌ی <b>array</b> آشنا شدید: بلوک‌هایی از حافظه که پشت سر هم قرار گرفته‌اند. می‌توانید آرایه را مثل هفت کمد قرمز کنار هم تصور کنید: </div>

![chart 2](https://cs50.harvard.edu/x/notes/3/cs50Week3Slide018.png)

<div dir="rtl" style="text-align: right;"> سمت چپ‌ترین کمد، <b>مکان 0</b> یا ابتدای آرایه است. سمت راست‌ترین کمد، <b>مکان 7</b> یا انتهای آرایه است. حالا فرض کنید می‌خواهیم بدانیم: «آیا عدد 50 داخل آرایه هست؟» کامپیوتر باید تک‌تک کمدها را نگاه کند تا ببیند 50 داخل است یا نه. به این فرایند <b>searching</b> می‌گوییم. </div>

![chart 3](https://cs50.harvard.edu/x/notes/3/cs50Week3Slide022.png)

<div dir="rtl" style="text-align: right;"> ما می‌توانیم دستورالعمل‌های مختلفی را تصور کنیم که به الگوریتم خود بدهیم تا این کار را انجام دهد، به شکل زیر: </div>

```python
    for each door from left to right
        if 50 is behind door
            return true
    return false

```

<div dir="rtl" style="text-align: right;"> توجه کنید که دستورالعمل‌های بالا <b>pseudocode</b> نامیده می‌شوند: نسخه‌ای قابل‌خواندن برای انسان از دستوراتی که می‌توانیم به کامپیوتر بدهیم. </div> <div dir="rtl" style="text-align: right;"> یک دانشمند کامپیوتر می‌تواند این pseudocode را به شکل زیر ترجمه کند: </div>

```python
    for i from 0 to n-1
        if 50 is behind doors[i]
            return true
    return false
```

<div dir="rtl" style="text-align: right;"> توجه کنید که این هنوز کد واقعی نیست، اما تقریب بسیار نزدیکی از چیزی است که کد نهایی ممکن است شبیه آن باشد. </div>

## Binary Search
<div dir="rtl" style="text-align: right;"> <b>Binary search</b> یک الگوریتم جستجوی دیگر است که می‌تواند در کار ما برای پیدا کردن عدد 50 استفاده شود. فرض کنید مقادیر داخل کمدها از کوچک به بزرگ مرتب شده‌اند. pseudocode برای Binary Search به این شکل خواهد بود: </div>

```sql
If no doors left
    Return false
If 50 is behind middle door
    Return true
Else if 50 < middle door
    Search left half
Else if 50 > middle door
    Search right half
```

<div dir="rtl" style="text-align: right;"> با استفاده از زبان کدنویسی، می‌توانیم الگوریتم را به این صورت دقیق‌تر بازنویسی کنیم: </div>

```sql
If no doors left
    Return false
If 50 is behind doors[middle]
    Return true
Else if 50 < doors[middle]
    Search doors[0] through doors[middle - 1]
Else if 50 > doors[middle]
    Search doors[middle + 1] through doors[n - 1]
```

<div dir="rtl" style="text-align: right;"> توجه کنید که با نگاه کردن به این تقریبی از کد، تقریباً می‌توانید تصور کنید کد واقعی چه شکلی خواهد داشت. </div>

## Running Time
<div dir="rtl" style="text-align: right;"> می‌توان در نظر گرفت که یک الگوریتم چه مقدار زمان برای حل یک مسئله نیاز دارد. تحلیل زمان اجرا با استفاده از <b>big O notation</b> انجام می‌شود. </div>

![chart 4](https://cs50.harvard.edu/x/notes/3/cs50Week3Slide042.png)

<div dir="rtl" style="text-align: right;"> به جای اینکه خیلی دقیق درباره‌ی کارایی ریاضی الگوریتم صحبت کنیم، دانشمندان کامپیوتر کارایی را از نظر <b>مرتبه‌ی زمانی اجرا</b> بررسی می‌کنند. در نمودار بالا:

- الگوریتم اول از مرتبه‌ی <code>O(n)</code> است. 
- دومی هم از مرتبه‌ی <code>O(n)</code> است. 
- سومی از مرتبه‌ی <code>O(log n)</code> است. </div>
<div dir="rtl" style="text-align: right;"> شکل منحنی است که نشان می‌دهد یک الگوریتم چقدر کارآمد است. برخی زمان‌های رایج اجرای الگوریتم: </div>

- O(n^2)
- O(n log n)
- O(n)
- O(log n)
- O(1)

<div dir="rtl" style="text-align: right;"> از میان این زمان‌ها: <br><code>O(n^2)</code> کندترین است. <br><code>O(1)</code> سریع‌ترین است.

جستجوی خطی از مرتبه‌ی <code>O(n)</code> است چون در بدترین حالت نیاز به n گام دارد.<br>
جستجوی دودویی از مرتبه‌ی <code>O(log n)</code> است چون حتی در بدترین حالت هم تعداد گام‌ها کمتر و کمتر می‌شود.

برنامه‌نویسان هم به <b>بدترین حالت (upper bound)</b> و هم به <b>بهترین حالت (lower bound)</b> علاقه‌مندند.

نماد <code>Ω</code> بهترین حالت یک الگوریتم را نشان می‌دهد، مثل <code>Ω(log n)</code>.

نماد <code>Θ</code> حالتی را نشان می‌دهد که بهترین و بدترین حالت یکسان باشند.

<b>Asymptotic notation</b> معیاری است برای اینکه ببینیم الگوریتم‌ها وقتی ورودی بزرگ‌تر و بزرگ‌تر می‌شود چه‌طور عملمی‌کنند.

با ادامه‌ی یادگیری در علوم کامپیوتر، در آینده این موضوعات را با جزئیات بیشتری بررسی خواهید کرد.
</div>

## search.c
<div dir="rtl" style="text-align: right;"> می‌توانید <b>Linear Search</b> را با نوشتن فایل <code>search.c</code> در ترمینال خود پیاده‌سازی کنید و کد زیر را بنویسید: </div>

```c
// Implements linear search for integers

#include <cs50.h>
#include <stdio.h>

int main(void)
{
    // An array of integers
    int numbers[] = {20, 500, 10, 5, 100, 1, 50};

    // Search for number
    int n = get_int("Number: ");
    for (int i = 0; i < 7; i++)
    {
        if (numbers[i] == n)
        {
            printf("Found\n");
            return 0;
        }
    }
    printf("Not found\n");
    return 1;
}
```

<div dir="rtl" style="text-align: right;"> توجه کنید که خطی که با <code>int numbers[]</code> شروع می‌شود، به ما اجازه می‌دهد مقادیر هر عنصر آرایه را هنگام ایجاد آن تعریف کنیم. سپس، در حلقه‌ی <code>for</code>، یک پیاده‌سازی از جستجوی خطی داریم. - <code>return 0</code> برای اعلام موفقیت و خروج از برنامه استفاده می‌شود. - <code>return 1</code> برای خروج از برنامه با خطا (شکست) استفاده می‌شود. </div> <div dir="rtl" style="text-align: right;"> ما اکنون جستجوی خطی را خودمان در C پیاده‌سازی کرده‌ایم! اما اگر بخواهیم در یک آرایه به دنبال یک رشته بگردیم چه؟ کافی است کد خود را به این صورت تغییر دهید: </div>

```c
// Implements linear search for strings

#include <cs50.h>
#include <stdio.h>
#include <string.h>

int main(void)
{
    // An array of strings
    string strings[] = {"battleship", "boot", "cannon", "iron", "thimble", "top hat"};

    // Search for string
    string s = get_string("String: ");
    for (int i = 0; i < 6; i++)
    {
        if (strcmp(strings[i], s) == 0)
        {
            printf("Found\n");
            return 0;
        }
    }
    printf("Not found\n");
    return 1;
}
```

<div dir="rtl" style="text-align: right;"> نکات مهم: - نمی‌توانیم مانند نسخه‌ی قبلی از <code>==</code> استفاده کنیم. در عوض باید از <code>strcmp</code> که از کتابخانه‌ی <code>string.h</code> می‌آید استفاده کنیم. - <code>strcmp</code> اگر دو رشته یکسان باشند، مقدار <code>0</code> برمی‌گرداند. - همچنین توجه کنید که طول آرایه به صورت hard-coded یعنی <code>6</code> نوشته شده است، که از نظر برنامه‌نویسی روش مناسبی نیست.

اجرای این کد به ما امکان می‌دهد روی این آرایه از رشته‌ها پیمایش کنیم و ببینیم آیا یک رشته‌ی خاص در آن وجود دارد یا خیر.

اما اگر با خطای <b>segmentation fault</b> مواجه شدید (زمانی که برنامه‌ی شما به بخشی از حافظه که نباید دسترسی داشته باشد دسترسی پیدا می‌کند)، مطمئن شوید که در شرط حلقه از <code>i < 6</code> استفاده کرده‌اید، نه <code>i < 7</code>.

می‌توانید درباره‌ی <code>strcmp</code> بیشتر در <b>CS50 Manual Pages</b> یاد بگیرید.
</div>

## phonebook.c
<div dir="rtl" style="text-align: right;"> می‌توانیم ایده‌های جستجو در آرایه‌های عددی و متنی را در یک برنامه ترکیب کنیم. کافی است فایل <code>phonebook.c</code> را ایجاد کرده و کد زیر را بنویسید: </div>

```c
// Implements a phone book without structs

#include <cs50.h>
#include <stdio.h>
#include <string.h>

int main(void)
{
    // Arrays of strings
    string names[] = {"Yuliia", "David", "John"};
    string numbers[] = {"+1-617-495-1000", "+1-617-495-1000", "+1-949-468-2750"};

    // Search for name
    string name = get_string("Name: ");
    for (int i = 0; i < 3; i++)
    {
        if (strcmp(names[i], name) == 0)
        {
            printf("Found %s\n", numbers[i]);
            return 0;
        }
    }
    printf("Not found\n");
    return 1;
}
```
<div dir="rtl" style="text-align: right;"> در این کد: - شماره‌ی یولیا با <code>+1-617</code> شروع می‌شود. - شماره‌ی دیوید هم با <code>+1-617</code> شروع می‌شود. - شماره‌ی جان با <code>+1-949</code> شروع می‌شود.

به همین دلیل <code>names[0]</code> برابر با <code>Yuliia</code> است و <code>numbers[0]</code> شماره‌ی یولیا است.
این کد به ما اجازه می‌دهد دفترچه تلفن را جستجو کنیم و شماره‌ی فرد خاصی را پیدا کنیم.

</div> <div dir="rtl" style="text-align: right;"> اگرچه این کد کار می‌کند، اما چندین ناکارآمدی دارد: - این احتمال وجود دارد که بین آرایه‌ی <code>names</code> و آرایه‌ی <code>numbers</code> هماهنگی وجود نداشته باشد. - نگهداری و توسعه‌ی چنین ساختاری سخت و پرخطا خواهد شد.

<b>بهتر نیست اگر بتوانیم نوع داده‌ی مخصوص خودمان را بسازیم</b> که در آن بتوانیم یک شخص را مستقیماً به شماره‌اش مرتبط کنیم؟ این دقیقاً جایی است که <code>structs</code> در زبان C به کمک ما می‌آیند.
</div>

## Structs
<div dir="rtl" style="text-align: right;"> در زبان C می‌توانیم با استفاده از <code>struct</code> نوع داده‌ی دلخواه خود را بسازیم. به عنوان مثال، اگر بخواهیم نوع داده‌ای به نام <b>person</b> داشته باشیم که شامل یک <code>name</code> و یک <code>number</code> باشد، می‌توانیم بنویسیم: </div>

```c
typedef struct
{
    string name;
    string number;
} person;
```

<div dir="rtl" style="text-align: right;"> در اینجا، یک نوع داده‌ی جدید به نام <b>person</b> تعریف کرده‌ایم که شامل دو رشته است: یکی برای نام و دیگری برای شماره. </div>
<div dir="rtl" style="text-align: right;"> حالا می‌توانیم کد دفترچه تلفن قبلی را بهبود دهیم و به شکل زیر بازنویسی کنیم: </div>

```c
// Implements a phone book with structs

#include <cs50.h>
#include <stdio.h>
#include <string.h>

typedef struct
{
    string name;
    string number;
} person;

int main(void)
{
    person people[3];

    people[0].name = "Yuliia";
    people[0].number = "+1-617-495-1000";

    people[1].name = "David";
    people[1].number = "+1-617-495-1000";

    people[2].name = "John";
    people[2].number = "+1-949-468-2750";

    // Search for name
    string name = get_string("Name: ");
    for (int i = 0; i < 3; i++)
    {
        if (strcmp(people[i].name, name) == 0)
        {
            printf("Found %s\n", people[i].number);
            return 0;
        }
    }
    printf("Not found\n");
    return 1;
}
```

<div dir="rtl" style="text-align: right;"> در این کد: - ابتدا با <code>typedef struct</code> یک نوع داده‌ی جدید به نام <b>person</b> ساخته‌ایم. - هر <code>person</code> شامل یک رشته <code>name</code> و یک رشته <code>number</code> است. - در تابع <code>main</code> آرایه‌ای از نوع <code>person</code> به نام <code>people</code> و به اندازه‌ی ۳ تعریف کرده‌ایم. - سپس با استفاده از <b>dot notation</b> (مثل <code>people[0].name</code>) نام و شماره‌ی هر شخص را مقداردهی کرده‌ایم. - در نهایت، با استفاده از <code>strcmp</code> در آرایه جستجو می‌کنیم تا ببینیم آیا نام وارد شده وجود دارد یا نه. </div>

## Sorting
<div dir="rtl" style="text-align: right;"> مرتب‌سازی (<b>Sorting</b>) به معنای گرفتن یک لیست نامرتب و تبدیل آن به یک لیست مرتب است. وقتی یک لیست مرتب باشد، جستجو در آن بسیار سریع‌تر خواهد بود. به یاد بیاور که الگوریتم <b>binary search</b> تنها روی یک لیست مرتب کار می‌کند، نه روی یک لیست نامرتب. </div>
<div dir="rtl" style="text-align: right;"> الگوریتم‌های زیادی برای مرتب‌سازی وجود دارد. یکی از آن‌ها <b>Selection Sort</b> است. فرض کن یک آرایه از مقادیر داریم (مثل ۷ کمد در کنار هم که آخرین کمد شماره‌ی <code>n-1</code> دارد). </div>

### الگوریتم Selection Sort (شبه‌کد)
```
For i from 0 to n – 1
    Find smallest number between numbers[i] and numbers[n - 1]
    Swap smallest number with numbers[i]
```

<div dir="rtl" style="text-align: right;">

 به زبان ساده: 
- در هر مرحله کوچک‌ترین عدد باقی‌مانده در آرایه را پیدا می‌کنیم.
- آن عدد را با عدد در موقعیت فعلی (index i) جابه‌جا می‌کنیم.
- این کار را تا رسیدن به انتهای لیست ادامه می‌دهیم. </div>
![chart5](https://cs50.harvard.edu/x/notes/3/cs50Week3Slide104.png)

### تحلیل زمانی
<div dir="rtl" style="text-align: right;"> بار اول که از ابتدای لیست شروع می‌کنیم، باید <code>n - 1</code> مقایسه انجام دهیم. بار دوم، <code>n - 2</code> مقایسه. و همین‌طور ادامه پیدا می‌کند تا آخر.

پس تعداد کل مقایسه‌ها برابر خواهد بود با:

(
𝑛
−
1
)
+
(
𝑛
−
2
)
+
(
𝑛
−
3
)
+
.
.
.
+
1
(n−1)+(n−2)+(n−3)+...+1

این جمع برابر است با:

𝑛
(
𝑛
−
1
)
2
2
n(n−1)
	​


که در ساده‌ترین حالت می‌شود: O(n²)

</div>

## Bubble Sort
<div dir="rtl" style="text-align: right;"> <b>Bubble Sort</b> یک الگوریتم مرتب‌سازی دیگر است که با جابه‌جایی مکرر عناصر کار می‌کند تا مقادیر بزرگ‌تر به سمت انتهای آرایه "حباب" کنند. </div>

الگوریتم Bubble Sort (شبه‌کد):
```
Repeat n - 1 times
    For i from 0 to n - 2
        If numbers[i] and numbers[i+1] out of order
            Swap them
    If no swaps
        Quit
```

<div dir="rtl" style="text-align: right;">

- آرایه را بارها مرور می‌کنیم.
- اگر دو عنصر پشت سر هم به ترتیب درست نباشند، جای آن‌ها را عوض می‌کنیم. 
- این کار باعث می‌شود عناصر بزرگ‌تر به انتهای لیست حرکت کنند. 
- اگر در یک مرحله هیچ جابه‌جایی انجام نشود، یعنی لیست مرتب شده و الگوریتم می‌تواند متوقف شود. </div>
تحلیل زمانی
<div dir="rtl" style="text-align: right;"> تعداد مراحل به صورت زیر خواهد بود:
(
𝑛
−
1
)
×
(
𝑛
−
1
)
=
𝑛
2
−
2
𝑛
+
1
(n−1)×(n−1)=n
2
−2n+1

که در ساده‌ترین حالت می‌شود: O(n²)

بدترین حالت (Upper Bound): الگوریتم باید کل لیست را مرور کند → 𝑂(n²)

بهترین حالت (Lower Bound): اگر لیست از قبل مرتب باشد، فقط یک بار مرور می‌کند → Ω(n)
</div>

## Recursion
<div dir="rtl" style="text-align: right;"> چگونه می‌توانیم کارایی مرتب‌سازی را بهبود دهیم؟ <b>Recursion</b> یا بازگشت، مفهومی در برنامه‌نویسی است که در آن یک تابع خودش را فراخوانی می‌کند. </div>

```
If no doors left
    Return false
If number behind middle door
    Return true
Else if number < middle door
    Search left half
Else if number > middle door
    Search right half
```

<div dir="rtl" style="text-align: right;"> در این مثال، تابع جستجو روی بخش‌های کوچکتر و کوچکتر آرایه یا مسئله خودش را فراخوانی می‌کند. </div>
مثال از Week 0 – دفترچه تلفن
<div dir="rtl" style="text-align: right;"> پیش از بازنویسی برای بازگشتی بودن: </div>

```
Pick up phone book
Open to middle of phone book
Look at page
If person is on page
Call person
Else if person is earlier in book
Open to middle of left half of book
Go back to line 3
Else if person is later in book
Open to middle of right half of book
Go back to line 3
Else
Quit
```

<div dir="rtl" style="text-align: right;"> نسخه‌ی بازگشتی ساده‌تر: </div>

```
Pick up phone book
Open to middle of phone book
Look at page
If person is on page
    Call person
Else if person is earlier in book
    Search left half of book
Else if person is later in book
    Search right half of book
Else
    Quit
```

مثال در Week 1 – هرم
<div dir="rtl" style="text-align: right;"> می‌خواستیم یک هرم با شکل زیر بسازیم: </div>

```shell
  #
  ##
  ###
  ####
```

پیاده‌سازی با حلقه (iteration):

```c
// Draws a pyramid using iteration

#include <cs50.h>
#include <stdio.h>

void draw(int n);

int main(void)
{
    // Get height of pyramid
    int height = get_int("Height: ");

    // Draw pyramid
    draw(height);
}

void draw(int n)
{
    // Draw pyramid of height n
    for (int i = 0; i < n; i++)
    {
        for (int j = 0; j < i + 1; j++)
        {
            printf("#");
        }
        printf("\n");
    }
}
```

<div dir="rtl" style="text-align: right;"> در این کد، هرم با استفاده از حلقه ساخته می‌شود. </div>

پیاده‌سازی بازگشتی (recursion):

```c
// Draws a pyramid using recursion

#include <cs50.h>
#include <stdio.h>

void draw(int n);

int main(void)
{
    // Get height of pyramid
    int height = get_int("Height: ");

    // Draw pyramid
    draw(height);
}

void draw(int n)
{
    // If nothing to draw
    if (n <= 0)
    {
        return;
    }

    // Draw pyramid of height n - 1
    draw(n - 1);

    // Draw one more row of width n
    for (int i = 0; i < n; i++)
    {
        printf("#");
    }
    printf("\n");
}
```

<div dir="rtl" style="text-align: right;"> نکات مهم: - <b>Base case</b> یا حالت پایه: خط <code>if (n <= 0)</code> تضمین می‌کند که بازگشت بی‌نهایت اجرا نشود و برنامه خاتمه یابد. - هر بار که تابع <code>draw</code> خودش را فراخوانی می‌کند، <code>n-1</code> ارسال می‌شود. - زمانی که <code>n-1 = 0</code> شود، تابع باز می‌گردد و برنامه به پایان می‌رسد. </div>

## Merge Sort
<div dir="rtl" style="text-align: right;"> اکنون می‌توانیم از <b>recursion</b> برای ایجاد یک الگوریتم مرتب‌سازی کارآمدتر استفاده کنیم و <b>Merge Sort</b> را پیاده‌سازی کنیم. Merge Sort یکی از الگوریتم‌های بسیار کارآمد مرتب‌سازی است. </div>
شبه‌کد Merge Sort:

```sql
If only one number
    Quit
Else
    Sort left half of number
    Sort right half of number
    Merge sorted halves
```

<div dir="rtl" style="text-align: right;"> به زبان ساده: - اگر فقط یک عنصر باقی مانده باشد، نیازی به مرتب‌سازی نیست. - در غیر این صورت، لیست را به دو نیمه تقسیم کرده و هر نیمه را مرتب می‌کنیم. - در نهایت دو نیمه‌ی مرتب شده را با هم ترکیب (merge) می‌کنیم. </div>
مثال مرحله به مرحله
<div dir="rtl" style="text-align: right;"> فرض کنید لیستی از اعداد داریم: </div>

```
6341
```
1. Merge Sort ابتدا می‌پرسد: "آیا این یک عدد است؟" → جواب: نه، پس ادامه می‌دهد.
```
6341
```
2. لیست را به دو نیمه تقسیم می‌کند:
```
63 | 41
```

3. نیمه‌ی چپ را بررسی می‌کند: "آیا این یک عدد است؟" → نه، پس دوباره تقسیم می‌کند:
```
6 | 3
```

4. اکنون نیمه‌ی چپ یک عدد است، بنابراین باز می‌گردد:
```
63 | 41
```

5. نیمه‌ی چپ مرتب می‌شود:
```
36 | 41
```

6. حالا روی نیمه‌ی راست همان مراحل تکرار می‌شود:
```
36 | 14
```

7. هر دو نیمه مرتب شده‌اند. اکنون دو نیمه با هم ترکیب می‌شوند:

- اولین عدد هر نیمه را مقایسه کرده، کوچک‌تر را انتخاب می‌کنیم.

- این کار برای تمام عناصر تکرار می‌شود و لیست نهایی به دست می‌آید:

```
1346
```

تحلیل زمانی
<div dir="rtl" style="text-align: right;"> - Merge Sort بسیار کارآمد است و <b>Worst-case</b> آن 𝑂(n log n) است. - حتی در بهترین حالت، الگوریتم باید همه عناصر را بررسی کند → Ω(n log n) - بنابراین Merge Sort نیز Θ(n log n) است، زیرا بهترین و بدترین حالت برابرند. </div>

## جمعبندی
<div dir="rtl" style="text-align: right;"> در این درس، با مفاهیم زیر آشنا شدیم و مهارت‌هایی کسب کردیم: 

- الگوریتم‌ها (<b>Algorithms</b>)
- نشانه‌گذاری پیچیدگی زمانی با <b>Big O notation</b>
- جستجوی دودویی (<b>Binary Search</b>) و جستجوی خطی (<b>Linear Search</b>)
- الگوریتم‌های مرتب‌سازی مختلف، شامل <b>Bubble Sort</b>، - <b>Selection Sort</b> و <b>Merge Sort</b>
- بازگشت یا <b>Recursion</b>
 تا جلسه‌ی بعد! </div>