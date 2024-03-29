---
layout: post
color: purple
cover: "http://s3-ap-southeast-1.amazonaws.com/monster-machine/images/horssghonr-1436272011-Midas.jpg"
title:  "معماری پلت فرم اندروید"
date:   2019-06-21 13:50:39
categories: android basic knowledge
---

<div dir="rtl" align="right">
اندروید درواقع سیستم عاملی مبتنی بر لینوکس و Open source می باشدکه با توجه به توضیحاتی که داده شد برای بازه وسیعی از دستگاهها طراحی شده است و قابلیت پشتیبانی آن ها را دارد.تصویر زیر کامپوننت های اصلی پلت فرم اندروید را نمایش می دهد.
</div>
<div align="center">
 <p><img src="../assets/images/android-platform-arch.png" alt="android platform architecture screenshot" /></p>
</div>

<h2>
<div dir="rtl" align="right">
4.1.	کرنل لینوکس
</div>
</h2>
<div dir="rtl" align="right">
بنیان و اساس پلت فرم اندروید کرنل لینوکس است.برای مثال ART (Android Runtime) برای یکسری از وظیفه مندی ها مثل threading و مدیریت سطوح پایین حافظه بر کرنل لینوکس متکی است. استفاده از لینوکس کرنل امکان استفاده از ویژگی های امنیتی کلیدی را فراهم می کند و به تولید کنندگان دستگاه ها امکان می دهد تا درایورهای سخت افزاری را برای کرنلی شناخته شده توسعه دهند.
</div>
<h2>
<div dir="rtl" align="right">
4.2.	لایه انتزاعی سخت افزار (HAL)
</div>
</h2>
<div dir="rtl" align="right">
Hardware abstraction layer (HAL) در واقع فراهم کننده اینترفیس های استاندارد برای قابلیت های سخت افزاری دستگاه و ارائه آن ها به فریم ورک جاواست. HAL شامل چندیدن ماژول کتابخانه ای است که هرکدام یک اینترفیس از نوع خاصی از کامپوننت سخت افزار ی را پیاده سازی می کند، مانند ماژول دوربین و یا Bluetooth.وقتی API فریم ورک برای دسترسی به سخت افزار دستگاه ،فراخوانی را انجام می دهد ، سیستم اندروید ماژول کتابخانه ای آن کامپوننت سخت افزاری را بارگذاری می کند.
</div>
<h2>
<div dir="rtl" align="right">
4.3.	Android Runtime
</div>
</h2>
<div dir="rtl" align="right">
برای دستگاههایی که اندروید 5 به بالا دارند هر برنامه ای برروی پردازش و نمونه خود از ART اجرا می شود.
</div>
<h2>
<div dir="rtl" align="right">
4.4.	کتابخانه های Native C/C++
</div>
</h2>
<div dir="rtl" align="right">
بسیاری از کامپوننت ها و سرویسهای هسته ای و اصلی سیستم اندروید مثل ART و HAL برپایه ی کد native ساخته شده اند که نیازمند کتابخانه های native می باشد که به زبان c و c++ نوشته شده اند.پلت فرم اندروید API های فریم ورک جاوا را به منظور امکان استفاده از وظیفه مندی های برخی از این کتابخانه های native در app ها فراهم می کند.برای مثال می توانید به OpenGL ES از طریق Java OpenGl API فریم ورک اندروید دسترسی داشته باشید که بدین طری گرافیک های دو بعدی و سه بعدی در برنامه قابل پشتیبانی خواهد بود.اگر در حال توسعه یک برنامه هستید که نیازمند کد C یا C++ هست ، می توانید از NDK اندروید برای دسترسی به برخی از این کتابخانه های پلت فرم native به صورت مستقیم از کد native خود استفاده کنید.
</div>
<h2>
<div dir="rtl" align="right">
4.5.	JAVA API Framework
</div>
</h2>
<div dir="rtl" align="right">
همانطور که میدانید به کل مجموعه ویژگی های سیستم عامل اندروید از طریق API هایی که به زبان جاوا نوشته شده است می توان دسترسی پیدا کرد.
این API ها بلوک هایی که شما برای ساختن برنامه اندرویدی خود بدان احتیاج دارید را تشکیل می دهد که این بلوک ها  با ساده سازی استفاده مجدد از هسته ، سرویس ها و کامپوننت های سیستمی ماژولار (که شامل موارد زیر می شود) شکل می گیرند.
<br/>
-	View System : برای ساختن UI برنامه های اندروید (شامل لیست ها ، گریدها، text box ها ، دکمه ها و حتی browser وب که قابل تعبیه شدن در برنامه است.)
<br/>
-	مدیر منابع : دسترسی به منابع غیر کد مثل string ها ، گرافیک ها و فایل های layout را فراهم می کند.
<br/>
-	مدیر notification :امکان نمایش پیام های سفارشی سازی شده را در status bar امکان پذیر می کند.
<br/>
-	مدیر Activity : چرخه حیات برنامه ها را مدیریت می کند و استکی جهت بازگشت به عقب برای برنامه ها فراهم می کند.
<br/>
-	Content Provider ها : به برنامه ها امکان دسترسی به داده های دیگر برنامه ها مانند برنامه Contacts یا به اشتراک گذاری داده های خودشان را فراهم می کند.
<br/>
توسعه دهندگان دسترسی کامل به همان API های فریم ورک را دارند که برنامه های سیستمی اندروید از آن استفاده می کنند.
</div>
<h2>
<div dir="rtl" align="right">
4.6.	System Apps
</div>
</h2>
<div dir="rtl" align="right">
اندروید شامل مجموعه ای از برنامه های اصلی برای ایمیل ، SMS ، تقویم ها ، اینترنت ، تماس ها و ... می باشند.برنامه هایی که در خود پلت فرم وجود دارند و وضعیت خاصی در بین برنامه هایی که کاربر برای نصب انتخاب می کند ندارند.
بنابراین برنامه های third-party میتوانند browser پیش فرض کاربر ، SMS messenger یا حتی صفحه کلید پیش فرض وی باشد(که این به استثنای برنامه های تنظیمات سیستمی است).
برنامه های سیستمی هم به عنوان برنامه هایی برای کاربران و هم بعنوان قابلیت های کلیدی برای توسعه دهنده ها که در برنامه های خودشان بدان ها بتوانند دسترسی پیدا کنند مطرح هستند.برای مثال اگر در برنامه خود بخواهید پیام SMS را ارسال کنید نیازی به این نیست که خودتان این وظیفه مندی را ایجاد کنید می توانید از برنامه SMS که برروی گوشی نصب شده است برای ارسال پیام استفاده کنید
</div>
