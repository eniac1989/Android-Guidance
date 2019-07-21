---
layout: post
color: purple
cover: "http://s3-ap-southeast-1.amazonaws.com/monster-machine/images/horssghonr-1436272011-Midas.jpg"
title:  "Table Layout"
date:   2019-07-21 13:50:39
categories: android basic knowledge
---
یکی از Layout های ساده جهت طراحی های پیچیده table می باشد که دارای 3 المان زیر می باشد:

1.	Stretch columns
2.	Layout_span
3.	Layout_column

در tableLayout به وسیله ی tag <tableRow> ردیفی ایجاد شده و به ازای هر ویو یا ویجت یک ستون ایجاد می گردد .شماره ستون ها و ردیف ها از صفر آغاز می گردد.در زمانی که تنظیم خاصی مد نظر باشد می بایست به نکات زیر توجه نمود.

** 	stretchColumns :ستون ها ی مشخص شده را تا پر نمودن عرض screen می کشند.(کشش عرضی)
	
<div align="center">
 <p><img src="../assets/images/table1.png" alt="table xml layout screenshot" /></p>
</div>
	
<div align="center">
 <p><img src="../assets/images/table2.png" alt="table view layout screenshot" /></p>
</div>

**	ShrinkColumns :برای کاهش عرض ستون مشخص شده به اندازه محتوای آن بکار می رود.

<div align="center">
 <p><img src="../assets/images/table3.png" alt="table shrink columns layout screenshot" /></p>
</div>

<div align="center">
 <p><img src="../assets/images/table4.png" alt="table shrink columns view layout screenshot" /></p>
</div>

** 	CollapseColumns :برای غیر قابل مشاهده نمودن ستون مشخص شده به کار می رود:

<div align="center">
 <p><img src="../assets/images/table5.png" alt="table collapse columns view layout screenshot" /></p>
</div>

<div align="center">
 <p><img src="../assets/images/table6.png" alt="table collapse columns view layout screenshot" /></p>
</div>

** 	layout_span: هرگاه بخواهیم ستون مجازی ایجاد کنیم که تعداد ستون ها در تمامی ردیف ها یکسان شود از layout_span استفاده می کنیم.

** 	Layout_column : هرگاه بخواهیم یک ویجت را در یک ستون خاص قرار دهیم از layoutColumn استفاده می کنیم.هرگاه column را مشخص نماییم ویجت های بعدی از ستون بعد از ستون مشخص شده پر نمودن را آغاز می کنند.

تذکر :جهت ایجاد یک خط مشخص بین ردیف ها از مورد زیر استفاده می کنیم:
<div dir="ltr" align="left" style=" background-color:rgba(50, 115, 220, 0.3);" >
<View
Android:background=@android:color/dark_gray”
Android:layout_height=”230dp”
/>
</div>

<div align="center">
 <p><img src="../assets/images/table7.png" alt="table collapse columns view layout screenshot" /></p>
</div>
