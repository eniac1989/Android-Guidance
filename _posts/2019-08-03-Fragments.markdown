---
layout: post
color: purple
cover: "http://s3-ap-southeast-1.amazonaws.com/monster-machine/images/horssghonr-1436272011-Midas.jpg"
title:  "Fragment"
date:   2019-08-03 13:50:39
categories: android basic knowledge
---
Fragment در واقع بخشی از Activity است که به نام Sub-Activity هم شناخته می شود.در یک Activity بیشتر از یک Fragment هم می تواند وجود داشته باشد.چرخه حیات Fragment متاثر از چرخه حیات Activity است چون در activity قرار دارند.اگرچه هر Fragment متدهای چرخه حیات خود را دارد که متاثر از چرخه حیات Activity هستند.

کلاس FragmentManager مسئول ایجاد تعامل بین اشیا fragment است.

<h2>
1. 	چرخه حیات FRAGMENT
</h2>
<div dir="ltr" align="right">
onAttach(Activity). 1
</div>
 زمانی فراخوانی می شود که فرگمنت به یک activity متصل می شود.
<div dir="ltr" align="right">
onCreate(Bundle) .2
</div>
 زمانی که فرگمنت ایجاد می شود این متد فراخوانی می شود.برای مقداردهی مولفه های اصلی فرگمنت که میخواهید حتما آن ها را بعد از زمانی که فرگمنت Pause یا Stop می شود و سپس Resume می شود ابقا کنید و از دست ندهید می بایست از این متد استفاده کنید.
<div dir="ltr" align="right">
onCreateView(LayoutInflater,ViewGroup,Bundle) .3
</div>
سلسله مراتب ویو را ساخته و آن را باز می گرداند.
هنگامی که زمانی ترسیم UI برای اولین بار توسط فرگمنت باشد این متد فراخوانی می شود.برای ترسیم UI برای فرگمنت باید کامپوننت View از این متد که ریشه layout فرگمنت است برگردانده شود.چنانچه فرگمنت UI نداشته باشد می تواند مقدار null برگرداند.

پارامتر container که به متد onCreateView() ارسال می شود ViewGroup والد است (از layout  اکتیویتی) که فرگمنت در آن قرار می گیرد.پارامتر savedInstanceState در واقع یک Bundle است که داده های نمونه قبلی فرگمنت را در حالتی که اگر فرگمنت در حال resume باشد ارائه کرده و برمی گرداند.

متد inflate() 3 آرگومان می گیرد:

-	ID layout که می خواهید آن را نمایش دهید.

-	ViewGroup که قرار است والد layout باشد.

-	مقدار Boolean که مشخص می کند که layout باید به ViewGroup (پارامتر دوم) متصل بشود یا خیر.در مثال زیر مقدار آن false است بعلت اینکه سیستم layout را در container درج کرده سات و چنانچه مقدار آن true باشد باعث ایجاد viewGroup اضافی در layout نهایی می شود.


<div align="center">
 <p><img src="../assets/images/fragment1.png" alt="fragment screenshot" /></p>
</div>

<div dir="ltr" align="right">
onActivityCreated(Bundle). 4
</div>
 بعد از onCreateView() فراخوانی می شود موقعی که Activity میزبان ایجاد می شود.نمونه های Activity و فرگمنت بعلاه سلسله مراتب activity ایجاد شده است.در این نقطه ، view با findViewById() قابل دستیابی است.برای مثال این متد می توان اشیایی که نیاز مند context می باشند را مقدار دهی نمود.

<div dir="ltr" align="right">
onViewStateRestored(Bundle) .5
</div>
 تمام اطلاعاتی که در خصوص وضعیت فرگمنت ذخیره شده بود به فرگمنت باز می گرداند.

<div dir="ltr" align="right">
onStart() .6
</div>
 فرکمنت را قابل مشاهده می نماید.

<div dir="ltr" align="right">
onResume() .7
</div>
فرکمنت در این مرحله تعاملی می شود و با کاربر تعامل پیدا می کند.در واقع زمانی که فرگمنت فعال می شود.

<div dir="ltr" align="right">
onPause() .8
</div>
 زمانی که دیگر قابلیت تعامل با فرگمنت وجود نداشته باشد فراخوانی می شود.
<div dir="ltr" align="right">
onStop() .9
</div>
 زمانیکه فرگمنت دیگر قابل مشاهده نباشد این متد فراخوانی می شود.

<div dir="ltr" align="right">
onDestroyView() .10
</div>
 این امکان را می دهد که فرگمنت منابع را پاکسازی کند و در صورتی که به منبعی نیازی نبود آن را آزاد کند.

<div dir="ltr" align="right">
onDestroy() .11
</div>
 به فرکمنت امکان پاکسازی نهایی وضعیت فرگمنت را می دهد.

<div dir="ltr" align="right">
onDetach() .12
</div>
 بلافاصله قبل از اینکه فرگمنت دیگر با activity ارتباط نداشته باشد و ارتبازش با فرگمنت قطع شده باشد فراخوانی می شود.

<div align="center">
 <p><img src="../assets/images/fragment2.png" alt="fragment screenshot" /></p>
</div>
