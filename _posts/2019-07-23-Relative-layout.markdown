---
layout: post
color: purple
cover: "http://s3-ap-southeast-1.amazonaws.com/monster-machine/images/horssghonr-1436272011-Midas.jpg"
title:  "Relative Layout"
date:   2019-07-21 13:50:39
categories: android basic knowledge
---
در RelativeLayout هدف ایجاد layout است که ویجت ها به صورت نسبی چیده می شوند.در این layout نسبت ها به یکی از دو صورت زیر و یا ترکیبی از آن ها ایجاد می شود:

1.	نسبت ویجت با parent
2.	نسبت ویجت با ویجت دیگری

هرگاه بخواهیم از نسبت های parent استفاده کنیم ، در تنظیمات از layout های دارای parent استفاده می کنیم و در حالت دوم از layoutهای فاقد parent استفاده می کنیم.

1.Layout_alignParentLeft=”true” ->  Anchor را به سمت چپ screen متصل می کنیم.

2.Layout_alignBaseLine=”@+id/txt_url” ->   خط مرکز با خط مرکز فونتی ویجت مشخص شده یکی می کنیم.


3.Layout_alignParentTop=”true”  ->      اتصال به خط افقی بالای screen

4.Layout_toRightOf=”@+id/label”	->	سمت راست ویجت مشخص شده قرار می گیرد.


5.layout_below=”@+id/txt_url”  ->   قرار گرفتن در پایین ویجت مشخص شده

6.layout_alignRight=”@+id/txt_url”  ->  خط عمودی سمت راست با خط عمودی سمت راست ویجت مشخص شده یکی می شود.



7.layout_toLeftOf=”@+id/btn_ok”  ->  در سمت چپ ویجت مشخص شده قرار می گیرد.

8.layout_alignTop=”@+id/btn_ok” ->  خط افقی بالای دو ویجت یکسان می شود.

- باید دقت شود در RelativeLayout همواره از ایجاد deadlock جلوگیری شود.
- به دلیل آنکه این layout نسبی می باشد تمامی ویجت ها می بایست دارای یک id باشد.
از مهمترین Attribute های RelativeLayout به موارد زیر می توان اشاره نمود :

<table>
  <tr>
    <th>ردیف</th>
    <th>Attribute ها و توضیحات</th>
    
  </tr>
  <tr>
    <td>1</td>
    <td>android:gravity
	<br/>		
	نحوه جایگذاری محتویات را در دومحور x و y مشخص می کند :
	
	مقادیر ممکن برای این attribute : top  ، bottom ، left ، right ، center ، center_vertical ، center_horizontal
	</td>
    
  </tr>
  <tr>
    <td>2</td>
    <td>android:ignoreGravity
	<br/>
	تعیین کننده این است که چه ویوهایی نباید gravity بررویشان تاثیری بگذارد
	</td>    
  </tr>
   
</table>
