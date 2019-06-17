---
layout: post
color: purple
cover: "http://s3-ap-southeast-1.amazonaws.com/monster-machine/images/horssghonr-1436272011-Midas.jpg"
title:  "Dalvik virtual Machine!"
date:   2019-06-17 13:50:39
categories: android basic knowledge
---
<h1 dir="rtl" align="right">
 2. معماری ماشین مجازی Dalvik
</h1>
<div dir="rtl" align="right">
جاوا همیشه با این عنوان که "یکجا بنویس ، و همه جا اجرا کن" شناخته شده و چنین قابلیتی با پلت فرم جاوا که بنیان و اساس آن Java Virtual Machin یا JVM هست امکان پذیر شده است.
اگرچه این هدف برای پلت فرم جاوا در محیط دسکتاپ (JSE)و سرور (J2EE) اجرایی شده اما اکوسیستم موبایل جاوا (JME)  با پیکربندی ها ، پروفایل ها و بسته های مختلف و متنوعی قطعه قطعه شده و یکپارچه نیست که این اتفاق در نهایت منجر به تغییرات مهمی در برنامه میشود تا برای دستگاه های مختلف قابل استفاده  و پشتیبانی باشد.
زمانی که گوگل جاوا را به عنوان زبانی برای توسعه برنامه های اندرویدی انتخاب کرد ، JME   و JVM را رها کرده و آن را با ماشین مجازی Dalvik جایگزین کرد.گوگل حتی برای یکسری از کتابخانه های استاندارد جاوا پیاده سازی هایی محدود و جایگزین نیز ارائه کرد که هردو این ها (هم کتابخانه و هم ماشین مجازی) جاوا غیر استاندارد بوده و در واقع انشعابی از جاوا می باشند.
در این بخش به دلایل فنی که منجر به ایجاد ماشین مجازی غیر استاندارد Dalvik و استفاده آن توسط گوگل شد و همینطور معماری Dalvik خواهیم پرداخت.

</div>
<h2>
<div dir="rtl" align="right">
2.1.	محدودیت های طراحی تحمیل شده توسط پلت فرم های هدف
</div>
</h2>

<div dir="rtl" align="right">
پلت فرم اندروید برای دستگاههای با قدرت پردازش ، حافظه و فضای ذخیره سازی محدود طراحی شده است.حداقل نیازمندی برای یک دستگاه اندروید به شرح ذیل است :
</div>
<table>
  <tr>
    <th>ویژگی</th>
    <th>حداقل نیازمندی</th>
    
  </tr>
  <tr>
    <td>تراشه</td>
    <td>ARM-Based</td>
    
  </tr>
  <tr>
    <td>حافظه</td>
    <td>128 MB RAM,256 MB Flash External</td>    
  </tr>
   <tr>
    <td>فضای ذخیره سازی</td>
    <td>Mini or Micro SD</td>    
  </tr>
   <tr>
    <td>صفحه نمایش اولیه</td>
    <td>QVGA TFT LCD or Larger , 16 bit  color  or better</td>    
  </tr>
   <tr>
    <td>کلید های هدایت </td>
    <td>5-way navigation with 5 application keys ,power, camera and volume controls</td>    
  </tr>
   <tr>
    <td>دوربین </td>
    <td>2MP CMOS</td>    
  </tr>
   <tr>
    <td>USB</td>
    <td>Standard Mini-B USB interface</td>    
  </tr>
    <tr>
    <td>Blutooth</td>
    <td>1.2 یا 2.0</td>    
  </tr>
</table>

<br/>
<div dir="rtl" align="right">
اگرچه گوشی های هوشمند با امکاناتی فراتر از آنچه بالا گفته شد در حال حاضر وجود دارند و به سرعت در حال رشد هستند اما آنچه در جدول بالا میبینیم گویای این است که پلت فرم در واقع باید تعداد وسیعی از دستگاههای با محدودیت منابع را پوشش داده و مورد هدف خود قرار دهد.
با توجه به چنین بازه وسیعی از محیط های هدف ، لازم است تا پلت فرمی که برنامه های کاربردی قرار است برروی آن اجرا شوند از سخت افزار و سیستم عامل به صورت انتزاعی جدا شود.
چنین نیازمندی را با این شرح میتوان بیان و خلاصه نمود که Andoid runtime باید موارد زیر را پشتیبانی نماید:
<br/>
-	Limited processor speed
<br/>
-	Limited RAM
<br/>
-	No swap Space
<br/>
-	Battery powered
<br/>
-	Diverse set of devices
<br/>
-	Sandboxed application runtime

</div>