---
layout: post
color: purple
cover: "http://s3-ap-southeast-1.amazonaws.com/monster-machine/images/horssghonr-1436272011-Midas.jpg"
title:  "Coordinator Layout"
date:   2019-07-28 13:50:39
categories: android basic knowledge
---
Coordinator Layout در واقع Frame Layout قدرتمند است.Coordinator Layout همه منظوره بوده و این امکان را می دهد که ویو های فرزند که دارای رفتارهای تعاملی هستند بتوان به درستی چیدمان کرد.

<div align="center">
 <p><img src="../assets/images/coord1.png" alt="coordinator layout screenshot" /></p>
</div>

دو کاربرد عمده که توسط Coordinator Layout پشتیبانی می شوند :
-	به عنوان layout والد در نظر گرفته می شوند در واقع root ویو ها در Activity و یا Fragmenr در نظر گرفته می شوند. 
-	بعنوان ظرفی برای تعاملات خاص با یک یا چند ویو فرزند در نظر گرفته می شوند.
با تعیین Behaviors برای ویو های فرزند در CoordinatorLayout می توان تعاملات متفاوتی را در یک والد و حتی بین ویو های آن والد داشت. 



<h2>
1. مهمترین Attribute ها در XML Coordinator Layout
</h2>

-	Android:layout_gravity :

gravity فرزند نسبت به والد در آن تعیین می شود .اگر Anchor با استفاده از app:layout_ancor در آن مشخص شود ، attribute layout_gravity در نظر گرفته نخواهد شد.و در عوض می بایست از app:layout_anchorGravity استفاده نمود.توجه کنید از هردو این attribute ها همزمان استفاده نکنید که منجر به نتایج غیر منتظره می شود.

<div align="center">
 <p><img src="../assets/images/coord2.png" alt="coordinator layout screenshot" /></p>
 استفاده از Fab بدون attribute Layout_gravity
</div>


<div align="center">
 <p><img src="../assets/images/coord3.png" alt="coordinator layout screenshot" /></p>
 Fab با attribute Layout_gravity="bottom|end"
</div>

-	App:layout_anchor : 

این attribute برروی فرزندان CoordinatorLayout اعمال می شود تا با استفده از آن ، آن ها را به ویو دیگر الصاق کنند.
<div dir="rtl">
 مقدار این attribute ، id ویویی است که نسبت به آن باید مکان یابی شود. 
</div>

<div align="center">
 <p><img src="../assets/images/coord4.png" alt="coordinator layout screenshot" /></p>
 FAB با  app:layout_ancor="@id/appbar"  و بدون app:layout_anchorGravity
</div>

-	App:layout_anchorGravity : تعیین می کند که یک شی چگونه نسبت به یک ویو anchor هم در محور X ها و هم در محور y ها در محدوده والد خود قرار بگیرد.

<div align="center">
 <p><img src="../assets/images/coord5.png" alt="coordinator layout screenshot" /></p>
 Fab با app:layout_anchorGravity="bottom|end"
</div>

-	App:layout_insetEdge : نحوه نمایش این ویو را در Coordinator Layout مشخص می کند و اینکه دیگر ویو ها چگونه در آن تعامل و حرکت می کنند.فرزند فضایی از صفحه نمایش را اشغال می کند که دیگر فرزنداان نباید در آن فضا قرار بگیرند.Bottom مقدار پیش فرض insetEdge ، SnackBar است.

-	App:layout_dodgeInsetEdges : مشخص می کند کدام لبه های فرزند باید توسط حرکت ها و تعاملات تنظیم شوند.Bottom مقدار پیش فرض برای dodgeInsetEdges دکمه Fab است.

<div align="center">
 <p><img src="../assets/images/coord6.png" alt="coordinator layout screenshot" /></p>
 دکمه dodgeInsetEdge را ندارد اما FAB دارد
</div>

-	App:layout_behaviour : این attribute تعیین کننده نحوه رفتار ویو فرزند در زمان اجراست.AppBarLayout و دکمه FAB رفتار پیش فرض که به آن ها الصاق شده دارند.





