---
layout: post
color: purple
cover: "http://s3-ap-southeast-1.amazonaws.com/monster-machine/images/horssghonr-1436272011-Midas.jpg"
title:  "Frame Layout"
date:   2019-07-21 13:50:39
categories: android basic knowledge
---
از attribute هایی که در frameLyout در آن استفاده می شود به موارد زیر می توان اشاره کرد:

** 	Foreground

Foreground مقادیر قابل ترسیم را برروی محتوا مشخص می کند و می تواند مقدار یک رنگ باشد .رنگ ها با این مقادیر مشخص می شوند :#rgb ، #argb ، #rrggbb و یا #aarrggbb .

در مثال زیر مقدار این attribute با رنگ سبز مقدار دهی شده است بنابراین imageView و دیگر ویوهای فرزند نمایش داده نمی شوند:
	
<div align="center">
 <p><img src="../assets/images/frame1.png" alt="frame xml layout screenshot" /></p>
</div>
	
<div align="center">
 <p><img src="../assets/images/frame2.png" alt="frame view layout screenshot" /></p>
</div>

** 	foregroundGravity

در واقع تعیین کننده gravity است که برروی foreground اعمال می شود.مقدار پیش فرض fill است.

مقادیر را به فرم های “top” ،"center_vertical"، “fill_vertical” ،”center_horizontal” ، "fill_horizontal " ، "center" ، “fill” ، “clip_vertical” ، "clip_horizontal" ،"bottom" ،"left" یا “right” میتوانیم تنظیم کنیم.

همچنین می توانیم چندین مقدار را با استفاده از (علامت pipe) برای این attribute تنظیم کنیم.

** 	Visibility

تعیین کننده این است که ویو visible ، invisible و یا gone باشد.
-	Visible : ویو visible است و نمایش داده می شود.
-	Invisible : ویو وجود دارد اما نمایش داده نمی شود.
-	Gone : ویو نه وجود دارد و نه نمایش داده می شود.

<div align="center">
 <p><img src="../assets/images/frame3.png" alt="frame layout visibility screenshot" /></p>
</div>


** 	measureAllChildren 

در واقع مشخص می کند آیا تمامی ویو های فرزند از جمله آن هایی که در وضعیت gone هستند سنجیده شوند یا تنها دو حالت visible و invisible مد نظر باشد.مقدار پیش فرض برای آن ها false است.مقادیر قابل قبول برای این attribute ، true  یا false است.همچنین مقدار این ttaribute ممکن است ارجاعی به یک منبع باشد به شکل “@[package:]type:name” یا attribute theme به شکل "?[package:][type:]name" .

اگر measureallchildren مقدار true باشد در نتیجه عرض و ارتفاع واقعی framelayout را نمایش خواهد داد حتی اگر visibility ویو ها در وضعیت gone باشد.

** 	مثالی از frameLayout


<div align="center">
 <p><img src="../assets/images/frame4.png" alt="frame layout sample screenshot" /></p>
</div>

<div align="center">
 <p><img src="../assets/images/frame5.png" alt="frame layout screenshot" /></p>
</div>


