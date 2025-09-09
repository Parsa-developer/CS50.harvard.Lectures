## خوش آمدید

<div dir="rtl" style="text-align: right;"> در هفته‌های گذشته با پایتون آشنا شدیم؛ زبانی سطح‌بالا که از همان اجزای سازنده‌ای استفاده می‌کرد که در زبان C یاد گرفته بودیم. امروز این مفاهیم را در دنیای <b>HTML</b>، <b>CSS</b> و <b>JavaScript</b> گسترش خواهیم داد.

### The Internet
اینترنت فناوری‌ای است که همه‌ی ما از آن استفاده می‌کنیم. با مهارت‌هایی که تا اینجا یاد گرفته‌ایم، می‌توانیم صفحات وب و برنامه‌های خود را بسازیم.
اینترنت در ابتدا با پروژه‌ای به نام <b>ARPANET</b> شروع شد که اولین نقاط را به هم متصل کرد.
نقاط اتصال را می‌توان مانند <b>Router</b> در نظر گرفت.

### Routers
برای ارسال داده از نقطه A به نقطه B، باید تصمیمات مسیریابی گرفته شود. داده می‌تواند مسیرهای مختلفی را طی کند. اگر یک روتر شلوغ باشد، داده از مسیر دیگری عبور می‌کند. داده‌ها در قالب <b>Packets</b> (بسته‌ها) از روتر به روتر و از یک کامپیوتر به کامپیوتر دیگر منتقل می‌شوند.

<b>TCP/IP</b>: دو پروتکل اصلی برای انتقال داده در اینترنت.

<b>IP (Internet Protocol)</b>: هر کامپیوتر در اینترنت یک آدرس منحصربه‌فرد دارد.

### IP Addresses
```
#.#.#.#
```

اعداد از 0 تا 255 متغیرند.
آدرس‌های IP نسخه 4، 32 بیتی هستند (حدود ۴ میلیارد آدرس).
نسخه‌های جدیدتر (IPv6) با 128 بیت، تعداد بسیار بیشتری آدرس را پشتیبانی می‌کنند.
Packets
هر بسته اطلاعاتی شامل نسخه، آدرس مبدأ، آدرس مقصد، طول، پروتکل، و دیگر داده‌های ساختاری است. به این ترتیب استانداردسازی تضمین می‌کند که همه دستگاه‌ها بتوانند داده‌ها را درک و پردازش کنند.
TCP
برای ردیابی ترتیب بسته‌ها استفاده می‌شود.
برای شناسایی سرویس‌های وب از <b>Port Numbers</b> استفاده می‌کند: ۸۰ برای HTTP و ۴۴۳ برای HTTPS.
فایل‌های بزرگ (مثل یک عکس) به بسته‌های کوچک تقسیم می‌شوند و در صورت گم‌شدن بخشی از داده، مجدد درخواست می‌شوند.
TCP اطمینان حاصل می‌کند که همه داده‌ها به مقصد برسند.

### DNS
به خاطر سپردن آدرس‌های IP کار دشواری است. پروتکل <b>DNS</b> (Domain Name System) این مشکل را حل می‌کند.
DNS یک پایگاه داده است که نام دامنه‌ها (مثل harvard.edu) را به آدرس‌های IP ترجمه می‌کند.

### DHCP
<b>DHCP</b> پروتکلی است که وظیفه اختصاص خودکار آدرس IP به دستگاه شما را بر عهده دارد.
همچنین Gateway پیش‌فرض و Nameserverهای دستگاه شما را مشخص می‌کند.

### HTTPS
<b>HTTP</b> یا <b>Hypertext Transfer Protocol</b> یک پروتکل در سطح برنامه (Application-Level Protocol) است که توسعه‌دهندگان از آن برای انتقال داده و ساختن سرویس‌ها و اپلیکیشن‌های کاربردی استفاده می‌کنند. نسخه‌ی امن آن، <b>HTTPS</b>، امنیت بیشتری در تبادل داده‌ها فراهم می‌کند.

### ساختار آدرس‌ها
وقتی وارد یک وبسایت می‌شوید (مثلاً: <b>https://www.example.com</b>) در واقع به طور ضمنی مسیر را با یک اسلش <b>/</b> در انتهای آن درخواست می‌کنید.
آنچه بعد از اسلش قرار می‌گیرد، <b>path</b> یا مسیر نامیده می‌شود. برای مثال: <b>https://www.example.com/folder/file.html</b> → وارد فولدر folder می‌شود و فایل <i>file.html</i> را درخواست می‌کند.
بخش <b>.com</b> یک <b>Top-Level Domain (TLD)</b> است که نوع یا موقعیت سازمان را مشخص می‌کند.
پیشوند <b>https</b> پروتکل استفاده‌شده را تعیین می‌کند.

### درخواست‌ها و پاسخ‌ها (Requests & Responses)
HTTP عمدتاً از <b>GET</b> و <b>POST</b> برای تبادل داده استفاده می‌کند.
مثال یک درخواست GET:</div>

```
GET / HTTP/2
Host: www.harvard.edu
```
<div dir="rtl" style="text-align: right;">مثال یک پاسخ موفقیت‌آمیز از سمت سرور:</div>

```
HTTP/2 200
Content-Type: text/html
```
### آزمایش با curl
<div dir="rtl" style="text-align: right;"> می‌توانیم درخواست‌ها و پاسخ‌های HTTP را به کمک ابزار <b>curl</b> مشاهده کنیم: </div>

```
curl -I https://www.harvard.edu/
```
<div dir="rtl" style="text-align: right;">هدرهای پاسخ سرور را نمایش می‌دهد.</div>

```
curl -I https://harvard.edu
```
<div dir="rtl" style="text-align: right;">پاسخ 301 (ریدایرکت دائم) را برمی‌گرداند.</div>

```
curl -I http://www.harvard.edu/
```
<div dir="rtl" style="text-align: right;">به دلیل نبودن s در https، باز هم پاسخی با کد 301 بازمی‌گردد.

### کدهای متداول وضعیت HTTP

1. 200 OK → موفقیت

2. 301 Moved Permanently → انتقال دائم

3. 302 Found → انتقال موقت

4. 304 Not Modified → بدون تغییر

5. 307 Temporary Redirect → ریدایرکت موقت

6. 401 Unauthorized → نیاز به احراز هویت

7. 403 Forbidden → دسترسی غیرمجاز

8. 404 Not Found → صفحه پیدا نشد

9. 418 I'm a Teapot → خطای طنزآمیز

10. 500 Internal Server Error → خطای داخلی سرور (اشتباه برنامه‌نویس)

11. 503 Service Unavailable → سرویس در دسترس نیست

نکته‌ی مهم: خطاهای <b>500</b> همیشه به کد یا برنامه‌ی شما مربوط می‌شوند و نشان‌دهنده‌ی مشکل سمت سرور هستند. این موضوع برای تمرین‌های هفته‌ی آینده و پروژه‌ی نهایی بسیار مهم خواهد بود!

## HTML
<div dir="rtl" style="text-align: right;"> <b>HTML</b> یا <b>HyperText Markup Language</b> زبانی است متشکل از تگ‌ها (tags) که می‌توانند دارای ویژگی‌هایی (attributes) باشند. این تگ‌ها ساختار یک صفحه‌ی وب را تعریف می‌کنند. </div>

### مثال اولیه
```html
<!DOCTYPE html>

<!-- Demonstrates HTML -->

<html lang="en">
    <head>
        <title>hello, title</title>
    </head>
    <body>
        hello, body
    </body>
</html>
```

<div dir="rtl" style="text-align: right;">

در این کد:
- تگ `<html>` آغاز و پایان سند HTML را مشخص می‌کند. 
- ویژگی `lang="en"` زبان سند را تعیین می‌کند. 
- بخش `<head>` شامل اطلاعات متادیتا مثل عنوان (title) است. 
- بخش `<body>` محتوای قابل مشاهده در مرورگر را در بر می‌گیرد. 

![html structure](https://cs50.harvard.edu/x/notes/8/cs50Week8Slide065.png)

### پاراگراف‌ها
فاصله‌ها و تورفتگی‌ها در HTML نادیده گرفته می‌شوند. برای نوشتن متن منظم باید از تگ `<p>` استفاده کنیم: </div>

```html
<p>
    این یک پاراگراف است.
</p>
<p>
    این هم یک پاراگراف دیگر است.
</p>
```

### تیترها
<div dir="rtl" style="text-align: right;"> 

HTML شش سطح تیتر دارد: از `<h1>` (بزرگ‌ترین و مهم‌ترین) تا `<h6>` (کوچک‌ترین). </div>
```html
<h1>عنوان اصلی</h1>
<h2>زیرعنوان</h2>
<h3>زیرزیرعنوان</h3>
```

### لیست‌ها
لیست نامرتب (Unordered List)
```html
<ul>
    <li>سیب</li>
    <li>موز</li>
    <li>پرتقال</li>
</ul>
```

لیست مرتب (Ordered List)
```html
<ol>
    <li>مرحله اول</li>
    <li>مرحله دوم</li>
    <li>مرحله سوم</li>
</ol>
```

### جدول‌ها (Tables)
```html
<!DOCTYPE html>

<!-- Demonstrates table -->

<html lang="en">
    <head>
        <title>table</title>
    </head>
    <body>
        <table border="1">
            <tr>
                <td>1</td>
                <td>2</td>
                <td>3</td>
            </tr>
            <tr>
                <td>4</td>
                <td>5</td>
                <td>6</td>
            </tr>
            <tr>
                <td>7</td>
                <td>8</td>
                <td>9</td>
            </tr>
            <tr>
                <td>*</td>
                <td>0</td>
                <td>#</td>
            </tr>
        </table>
    </body>
</html>
```

<div dir="rtl" style="text-align: right;">

در جدول بالا: 
- تگ `<table>` جدول را می‌سازد. 
- تگ `<tr>` یک ردیف جدید ایجاد می‌کند. 
- تگ `<td>` یک سلول داده در جدول است. </div>

### تصاویر (Images)
```html
<!DOCTYPE html>

<!-- Demonstrates image -->

<html lang="en">
    <head>
        <title>image</title>
    </head>
    <body>
        <img alt="photo of bridge" src="bridge.png">
    </body>
</html>
```

<div dir="rtl" style="text-align: right;">

- ویژگی `src="bridge.png"` مسیر فایل تصویر را مشخص می‌کند. 
- ویژگی `alt` توضیحی برای تصویر فراهم می‌کند (برای سئو و دسترس‌پذیری).

### ویدئوها (Videos)
```html
<!DOCTYPE html>

<!-- Demonstrates video -->

<html lang="en">
    <head>
        <title>video</title>
    </head>
    <body>
        <video controls muted>
            <source src="video.mp4" type="video/mp4">
        </video>
    </body>
</html>
```

<div dir="rtl" style="text-align: right;">

- ویژگی `controls` دکمه‌های کنترل (پخش، توقف و غیره) اضافه می‌کند. 
- ویژگی `muted` ویدئو را بی‌صدا اجرا می‌کند. 
- تگ `<source>` مسیر فایل و نوع آن (مثلاً `video/mp4`) را مشخص می‌کند.

### لینک‌ها (Links)
```html
<!DOCTYPE html>

<!-- Demonstrates link -->

<html lang="en">
    <head>
        <title>link</title>
    </head>
    <body>
       Visit <a href="https://www.harvard.edu">Harvard</a>.
    </body>
</html>
```

<div dir="rtl" style="text-align: right;">

تگ `<a>` یا *anchor* برای ایجاد لینک استفاده می‌شود. ویژگی `href` مسیر لینک را مشخص می‌کند. در این مثال، کلمه‌ی *Harvard* قابل کلیک است.

### فرم‌ها (Forms)
فرم ساده
```html
<!DOCTYPE html>

<!-- Demonstrates form -->

<html lang="en">
    <head>
        <title>search</title>
    </head>
    <body>
        <form action="https://www.google.com/search" method="get">
            <input name="q" type="search">
            <input type="submit" value="Google Search">
        </form>
    </body>
</html>
```

<div dir="rtl" style="text-align: right;">

- تگ `<form>` مشخص می‌کند که داده‌ها کجا ارسال شوند (`action`). 
- ویژگی `method="get"` روش ارسال داده را تعیین می‌کند. 
- تگ `<input>` برای ورودی‌های مختلف کاربر استفاده می‌شود.
فرم پیشرفته‌تر
```html
<!DOCTYPE html>

<!-- Demonstrates additional form attributes -->

<html lang="en">
    <head>
        <title>search</title>
    </head>
    <body>
        <form action="https://www.google.com/search" method="get">
            <input autocomplete="off" autofocus name="q" placeholder="Query" type="search">
            <button>Google Search</button>
        </form>
    </body>
</html>
```

<div dir="rtl" style="text-align: right;">

- ویژگی `autocomplete="off"` تکمیل خودکار مرورگر را غیرفعال می‌کند. 
- ویژگی `autofocus` باعث می‌شود فرم هنگام باز شدن صفحه به‌طور خودکار انتخاب شود. 
- ویژگی `placeholder="Query"` متن راهنما داخل ورودی نمایش می‌دهد.

### Regular Expressions & CSS
Regular Expressions (Regex)
```html
<!DOCTYPE html>

<!-- Demonstrates type="email" -->

<html lang="en">
    <head>
        <title>register</title>
    </head>
    <body>
        <form>
            <input autocomplete="off" autofocus name="email" placeholder="Email" type="email">
            <button>Register</button>
        </form>
    </body>
</html>
```

<div dir="rtl" style="text-align: right;"> 

در این مثال، ویژگی `type="email"` باعث می‌شود مرورگر بررسی کند که مقدار واردشده یک ایمیل معتبر باشد.

اما می‌توانیم یک گام جلوتر برویم و با استفاده از regex، قالب خاصی را برای ایمیل تعریف کنیم:
</div>

```html
<!DOCTYPE html>

<!-- Demonstrates pattern attribute -->

<html lang="en">
    <head>
        <title>register</title>
    </head>
    <body>
        <form>
            <input autocomplete="off" autofocus name="email" 
                   pattern=".+@.+\.edu" 
                   placeholder="Email" type="email">
            <button>Register</button>
        </form>
    </body>
</html>
```

<div dir="rtl" style="text-align: right;"> 

اینجا: 
- ویژگی `pattern=".+@.+\.edu"` می‌گوید که ورودی باید یک **آدرس ایمیل دانشگاهی با پسوند `.edu`** باشد. 
- علامت `.` یعنی هر کاراکتری. 
- علامت `+` یعنی یک یا بیشتر. 
- `\.` یعنی نقطه واقعی. </div>

### CSS (Cascading Style Sheets)

1. CSS خطی (Inline CSS)
```html
<!DOCTYPE html>

<!-- Demonstrates inline CSS with P tags -->

<html lang="en">
    <head>
        <title>css</title>
    </head>
    <body>
        <p style="font-size: large; text-align: center;">
            John Harvard
        </p>
        <p style="font-size: medium; text-align: center;">
            Welcome to my home page!
        </p>
        <p style="font-size: small; text-align: center;">
            Copyright &#169; John Harvard
        </p>
    </body>
</html>
```

<div dir="rtl" style="text-align: right;">

در این روش، ویژگی `style` مستقیماً روی هر تگ اعمال می‌شود. این روش سریع است ولی تکراری و غیر بهینه. </div>

2. استفاده از `<div>` و وراثت (Cascading)
```html
<!DOCTYPE html>

<!-- Removes outer DIV -->

<html lang="en">
    <head>
        <title>css</title>
    </head>
    <body style="text-align: center">
        <div style="font-size: large">
            John Harvard
        </div>
        <div style="font-size: medium">
            Welcome to my home page!
        </div>
        <div style="font-size: small">
            Copyright &#169; John Harvard
        </div>
    </body>
</html>
```

<div dir="rtl" style="text-align: right;">

ویژگی `text-align: center` روی `<body>` اعمال شده و به تمام فرزندان آن ارث می‌رسد. این همان مفهوم **Cascading** است. </div>

3. استفاده از تگ‌های معنایی (Semantic Tags)
```html
<!DOCTYPE html>

<!-- Uses semantic tags instead of DIVs -->

<html lang="en">
    <head>
        <title>css</title>
    </head>
    <body style="text-align: center">
        <header style="font-size: large">
            John Harvard
        </header>
        <main style="font-size: medium">
            Welcome to my home page!
        </main>
        <footer style="font-size: small">
            Copyright &#169; John Harvard
        </footer>
    </body>
</html>
```

<div dir="rtl" style="text-align: right;">

اینجا به جای `<div>` از **تگ‌های معنایی** استفاده شده: 
- `<header>` برای سربرگ 
- `<main>` برای محتوای اصلی 
- `<footer>` برای پاورقی </div>

4. استفاده از Class Selector
```html
<!DOCTYPE html>

<!-- Demonstrates class selectors -->

<html lang="en">
    <head>
        <style>
            .centered {
                text-align: center;
            }
            .large {
                font-size: large;
            }
            .medium {
                font-size: medium;
            }
            .small {
                font-size: small;
            }
        </style>
        <title>css</title>
    </head>
    <body class="centered">
        <header class="large">
            John Harvard
        </header>
        <main class="medium">
            Welcome to my home page!
        </main>
        <footer class="small">
            Copyright &#169; John Harvard
        </footer>
    </body>
</html>
```

<div dir="rtl" style="text-align: right;">

در این روش: 
- کلاس‌ها با `.` تعریف می‌شوند. 
- هر تگ می‌تواند یک یا چند کلاس داشته باشد. </div>

5. استفاده از فایل خارجی CSS

style.css
```css
.centered {
    text-align: center;
}

.large {
    font-size: large;
}

.medium {
    font-size: medium;
}

.small {
    font-size: small;
}
```

home.html
```html
<!DOCTYPE html>

<!-- Demonstrates external stylesheets -->

<html lang="en">
    <head>
        <link href="style.css" rel="stylesheet">
        <title>css</title>
    </head>
    <body class="centered">
        <header class="large">
            John Harvard
        </header>
        <main class="medium">
            Welcome to my home page!
        </main>
        <footer class="small">
            Copyright &#169; John Harvard
        </footer>
    </body>
</html>
```

<div dir="rtl" style="text-align: right;">

اینجا فایل `style.css` جداگانه تعریف شده و با `<link>` به HTML وصل شده است. این بهترین روش برای پروژه‌های واقعی است.

## Frameworks
<div dir="rtl" style="text-align: right;">

همانطور که در پایتون می‌توانیم از **کتابخانه‌های جانبی (third-party libraries)** استفاده کنیم، در طراحی وب هم می‌توانیم از **فریمورک‌ها** استفاده کنیم.

یکی از پرکاربردترین فریمورک‌ها برای طراحی صفحات وب، Bootstrap است. این فریمورک مجموعه‌ای از CSS + JavaScript آماده دارد که به ما کمک می‌کند صفحات زیباتر و واکنش‌گرا (responsive) بسازیم.

برای استفاده از Bootstrap کافی است لینک آن را در <head> قرار دهیم:
</div>

```html
<head>
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css" rel="stylesheet">
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/js/bootstrap.bundle.min.js"></script>
    <title>bootstrap</title>
</head>
```

1. جدول ساده بدون Bootstrap
```html
<!DOCTYPE html>

<!-- Demonstrates table -->

<html lang="en">
    <head>
        <title>phonebook</title>
    </head>
    <body>
        <table>
            <thead>
                <tr>
                    <th>Name</th>
                    <th>Number</th>
                </tr>
            </thead>
            <tbody>
                <tr>
                    <td>Carter</td>
                    <td>+1-617-495-1000</td>
                </tr>
                <tr>
                    <td>David</td>
                    <td>+1-617-495-1000</td>
                </tr>
                <tr>
                    <td>John</td>
                    <td>+1-949-468-2750</td>
                </tr>
            </tbody>
        </table>
    </body>
</html>
```

<div dir="rtl" style="text-align: right;"> این جدول کار می‌کند، اما ظاهر آن ساده و ابتدایی است.

2. جدول با Bootstrap
```html
<!DOCTYPE html>

<!-- Demonstrates table with Bootstrap -->

<html lang="en">
    <head>
        <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css" rel="stylesheet">
        <title>phonebook</title>
    </head>
    <body>
        <table class="table">
            <thead>
                <tr>
                    <th scope="col">Name</th>
                    <th scope="col">Number</th>
                </tr>
            </thead>
            <tbody>
                <tr>
                    <td>Carter</td>
                    <td>+1-617-495-1000</td>
                </tr>
                <tr>
                    <td>David</td>
                    <td>+1-949-468-2750</td>
                </tr>
            </tbody>
        </table>
    </body>
</html>
```

<div dir="rtl" style="text-align: right;"> کافیست کلاس `class="table"` را اضافه کنیم تا جدول زیبا و مرتب شود.

3. صفحه جستجو با Bootstrap
```html
<!DOCTYPE html>

<!-- Demonstrates layout with Bootstrap -->

<html lang="en">
    <head>
        <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css" rel="stylesheet">
        <title>search</title>
    </head>
    <body>

        <div class="container-fluid">

            <!-- Navigation bar -->
            <ul class="m-3 nav">
                <li class="nav-item">
                    <a class="nav-link text-dark" href="https://about.google/">About</a>
                </li>
                <li class="nav-item">
                    <a class="nav-link text-dark" href="https://store.google.com/">Store</a>
                </li>
                <li class="nav-item ms-auto">
                    <a class="nav-link text-dark" href="https://www.google.com/gmail/">Gmail</a>
                </li>
                <li class="nav-item">
                    <a class="nav-link text-dark" href="https://www.google.com/imghp">Images</a>
                </li>
                <li class="nav-item">
                    <a class="btn btn-primary" href="https://accounts.google.com/ServiceLogin" role="button">Sign in</a>
                </li>
            </ul>

            <!-- Centered content -->
            <div class="text-center">

                <img alt="Happy Cat" class="img-fluid w-25" src="cat.gif">

                <form action="https://www.google.com/search" class="mt-4" method="get">
                    <input autocomplete="off" autofocus 
                           class="form-control form-control-lg mb-4 mx-auto w-50" 
                           name="q" placeholder="Query" type="search">
                    <button class="btn btn-light">Google Search</button>
                    <button class="btn btn-light" name="btnI">I'm Feeling Lucky</button>
                </form>
            </div>
        </div>
    </body>
</html>
```

<div dir="rtl" style="text-align: right;">

اینجا: 
- `container-fluid` برای یک صفحه تمام‌عرض استفاده شده. 
- `nav` و `nav-item` یک نوار منو ساخته‌اند. 
- `btn btn-primary` دکمه‌های زیبا و استاندارد تولید کرده. 
- `form-control` و `form-control-lg` جعبه جستجو را بزرگ و مرتب کرده‌اند.

در نتیجه ظاهر صفحه بسیار حرفه‌ای‌تر می‌شود، بدون اینکه ما خودمان CSS زیادی بنویسیم.

</div>

🔗 برای مطالعه بیشتر: [Bootstrap Documentation](https://getbootstrap.com/docs/)

## JavaScript
<div dir="rtl" style="text-align: right;">

جاوااسکریپت (**JavaScript**) یک زبان برنامه‌نویسی است که به صفحات وب **تعامل (interactivity)** می‌بخشد. با جاوااسکریپت می‌توانیم رفتار صفحه را پس از بارگذاری تغییر دهیم، بدون اینکه نیاز به رفرش شدن داشته باشد.

بیایید چند نمونه ببینیم:
</div>

1. فرم ساده با onsubmit
```html
<!DOCTYPE html>
<html lang="en">
    <head>
        <script>
            function greet()
            {
                alert('hello, ' + document.querySelector('#name').value);
            }
        </script>
        <title>hello</title>
    </head>
    <body>
        <form onsubmit="greet(); return false;">
            <input autocomplete="off" autofocus id="name" placeholder="Name" type="text">
            <input type="submit">
        </form>
    </body>
</html>
```

<div dir="rtl" style="text-align: right;">

- وقتی فرم ارسال (submit) شود، تابع `greet()` اجرا می‌شود.
- مقدار ورودی با `document.querySelector('#name').value` گرفته می‌شود. 
- سپس با `alert` نمایش داده می‌شود.

2. روش بهتر با addEventListener
```html
<!DOCTYPE html>
<html lang="en">
    <head>
        <script>
            document.addEventListener('DOMContentLoaded', function() {
                document.querySelector('form').addEventListener('submit', function(e) {
                    alert('hello, ' + document.querySelector('#name').value);
                    e.preventDefault();
                });
            });
        </script>
        <title>hello</title>
    </head>
    <body>
        <form>
            <input autocomplete="off" autofocus id="name" placeholder="Name" type="text">
            <input type="submit">
        </form>
    </body>
</html>
```

<div dir="rtl" style="text-align: right;">

اینجا: 
- از **DOMContentLoaded** استفاده شده تا مطمئن شویم کل صفحه بارگذاری شده. 
- به جای `onsubmit` در HTML، با `addEventListener` مدیریت رویداد انجام می‌شود (که **بهتر و تمیزتر** است). </div>

3. نمایش لحظه‌ای متن با keyup
```html
<!DOCTYPE html>
<html lang="en">
    <head>
        <script>
            document.addEventListener('DOMContentLoaded', function() {
                let input = document.querySelector('input');
                input.addEventListener('keyup', function(event) {
                    let name = document.querySelector('p');
                    if (input.value) {
                        name.innerHTML = `hello, ${input.value}`;
                    }
                    else {
                        name.innerHTML = 'hello, whoever you are';
                    }
                });
            });
        </script>
        <title>hello</title>
    </head>
    <body>
        <form>
            <input autocomplete="off" autofocus placeholder="Name" type="text">
        </form>
        <p></p>
    </body>
</html>
```

<div dir="rtl" style="text-align: right;">

- در هر بار تایپ (`keyup`) مقدار ورودی گرفته می‌شود. 
- متن `<p>` به‌طور پویا تغییر می‌کند. 
- اگر چیزی نوشته نشود، متن پیش‌فرض نمایش داده می‌شود. </div>

4. تغییر رنگ پس‌زمینه با دکمه‌ها
```html
<!DOCTYPE html>
<html lang="en">
    <head>
        <title>background</title>
    </head>
    <body>
        <button id="red">R</button>
        <button id="green">G</button>
        <button id="blue">B</button>
        <script>
            let body = document.querySelector('body');
            document.querySelector('#red').addEventListener('click', function() {
                body.style.backgroundColor = 'red';
            });
            document.querySelector('#green').addEventListener('click', function() {
                body.style.backgroundColor = 'green';
            });
            document.querySelector('#blue').addEventListener('click', function() {
                body.style.backgroundColor = 'blue';
            });
        </script>
    </body>
</html>
```

<div dir="rtl" style="text-align: right;"> اینجا با کلیک روی هر دکمه، رنگ پس‌زمینه تغییر می‌کند.

5. چشمک‌زن (Blink)
```html
<!DOCTYPE html>
<html lang="en">
    <head>
        <script>
            function blink()
            {
                let body = document.querySelector('body');
                if (body.style.visibility == 'hidden')
                {
                    body.style.visibility = 'visible';
                }
                else
                {
                    body.style.visibility = 'hidden';
                }
            }
            window.setInterval(blink, 500);
        </script>
        <title>blink</title>
    </head>
    <body>
        hello, world
    </body>
</html>
```

<div dir="rtl" style="text-align: right;">

- با `setInterval` هر ۵۰۰ میلی‌ثانیه متن نمایش داده یا پنهان می‌شود. 
- نتیجه: متن شروع به چشمک زدن می‌کند.

6. تکمیل خودکار (Autocomplete)
```html
<!DOCTYPE html>
<html lang="en">
    <head>
        <title>autocomplete</title>
    </head>
    <body>
        <input autocomplete="off" autofocus placeholder="Query" type="text">
        <ul></ul>
        <script src="large.js"></script>
        <script>
            let input = document.querySelector('input');
            input.addEventListener('keyup', function(event) {
                let html = '';
                if (input.value) {
                    for (word of WORDS) {
                        if (word.startsWith(input.value)) {
                            html += `<li>${word}</li>`;
                        }
                    }
                }
                document.querySelector('ul').innerHTML = html;
            });
        </script>
    </body>
</html>
```

<div dir="rtl" style="text-align: right;">

- فایل `large.js` شامل یک آرایه بزرگ از کلمات است. 
- وقتی کاربر شروع به تایپ می‌کند، کلماتی که با متن تایپ‌شده شروع می‌شوند در یک لیست `<ul>` ظاهر می‌شوند. </div>

## 📝 جمع‌بندی
<div dir="rtl" style="text-align: right;"> در این درس یاد گرفتیم:

- TCP/IP
- DNS
- HTML و تگ‌های پرکاربرد
- Regular Expressions برای اعتبارسنجی داده‌ها
- CSS برای استایل‌دهی
- Frameworks مثل Bootstrap برای طراحی سریع‌تر
- JavaScript برای ایجاد تعاملات پویا در صفحات وب
- جاوااسکریپت ابزار اصلی برای زنده کردن صفحات وب است. 🚀

تا جلسه‌ی بعد!
</div>