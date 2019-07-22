---
layout: post
color: purple
cover: "http://s3-ap-southeast-1.amazonaws.com/monster-machine/images/horssghonr-1436272011-Midas.jpg"
title:  "Grid Layout"
date:   2019-07-22 13:50:39
categories: android basic knowledge
---
GridLayout در ApI 14 معرفی شد و برای حفظ compatibility توسط Support Library پشتیبانی می شود.هدف اصلی آن رفع مشکل کارایی و تراز بودن در باقی layout هایی مثل linearLayout بود.

GridLayout عمدتا به منظور تراز کردن ویوهای فرزند در سلول ها که به صورت عمودی یا افقی هستند استفاده می شود.هر ویو در یک سلول قرار دارد و سلول ها با ایندکس های افقی و عموی شماره گذاری شده اند.در کل API ، خطوط grid با ایندکس های grid ارجاع می شوند.گرید با n ستون N+1 ایندکس دارد که از 0 تا N شماره گذاری می شود.صرف نظر از اینکه Grid Layout به چه ترتیبی پیکربندی می شود، ایندکس grid صفر برای لبه ی اول و ایندکس N برای لبه انتهایی در نظر گرفته می شود.

<div align="center">
 <p><img src="../assets/images/grid1.png" alt="grid layout screenshot" /></p>
</div>

تعداد سطرها و ستون ها در grid با استفاده از android:rowCount و android:columnCount مشخص می شود.به صورت کلی اگر تعداد ستون ها مشخص شده باشد ، تعداد سطرها بسته به اینکه چه تعداد سلول در صفحه اشغال می شوند تعیین می شود و استفاده از rowCount الزامی نیست. به صورت مشابه ، جهت GridLayout به صورت اختیاری با استفاده از android:orientation مشخص می شود.

<h2>
6.1.	اضافه نمودن ویو های فرزند به GridLayout
</h2>

ویو های فرزند می توانند به GridLayout در ساختار تگ <GridLayout> اضافه شوند .اگر هیچ سطر و یا ستونی در آن مشخص نشده باشد ، ویو های فرزند به صورت خودکار توسط کلاس GridLayout بسته به پیکربندی layout و مکان ویو در فایل XML جایگذاری می شوند.

به مثال زیر توجه کنید:

<div align="center">
 <p><img src="../assets/images/grid2.png" alt="grid layout screenshot" /></p>
</div>
<div align="center">
 <p><img src="../assets/images/grid3.png" alt="grid layout screenshot" /></p>
</div>

در عین حال یک ویو می تواند با مشخص نمودن شماره سطر و ستون سلول مورد نظر ، در آن سلول قرار بگیرد.به مثال زیر توجه کنید:

دکمه در سطر شماره 1 ، ستون 2 قرار گرفته است. 

<div align="center">
 <p><img src="../assets/images/grid4.png" alt="grid layout screenshot" /></p>
</div>

