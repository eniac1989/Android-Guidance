---
layout: post
color: purple
cover: "http://s3-ap-southeast-1.amazonaws.com/monster-machine/images/horssghonr-1436272011-Midas.jpg"
title:  "layouts of android"
date:   2019-06-29 13:50:39
categories: android basic knowledge
---
Layout ساختار واسط کاربری شما را در برنامه تعریف می کند .تمام المان ها در layout با استفاده از سلسله مراتبی از اشیا view و viewGroup ساخته می شوند.View معمولا چیزی را که کاربر بتواند ببیند و با آن تعامل برقرار کند ترسیم می کند .در حالیکه viewGroup مخزن یا ظرفی است که ساختار layout را برای view و دیگر viewGroup ها تعریف می کند.

<div align="center">
 <p><img src="../assets/images/layout.png" alt="android layouts screenshot" /></p>
</div>
اشیا View معمولا ویجت نامیده می شوند و می توانند یکی از خیلی از زیرکلاس هایی همچون Button یا TextView باشند.اشیا ViewGroup معمولا layout خوانده می شوند که می توانند یکی از خیلی از انواع ساختارهای layout باشند همچون LinearLayout یا ConstraintLayout .
<br/>
Layout را به دو شیوه می توان تعریف نمود :
<br/>
•	المان های UI را در XML اعلان کنید :اندروید در فایل XML که ارائه می دهد کاملا مطابق با کلاس های View و زیر کلاس هایی همچون ویجت ها و layout ها می باشد.برای تعریف آن ها می توان از Layout Editor اندروید استودیو نیز استفاده نمود که طراحی layout را با استفاده از drag & drop انجام می دهد.
<br/>
•	مقدار دهی و تعریف المان های layout در زمان اجرا : می توانید View و ViewGroup را در برنامه تعریف کرده و خصوصیات آن را تغییر دهید.
تعریف UI در XML این امکان را می دهد تا بخش نمایشبرنامه را از کد جدا نمایید که در واقع رفتار این بخش نمایشی را کنترل می کند.با استفاده از فایل های XML همچنین ایجاد layout های متفاوت برای سایزهای صفحه نمایش و جهت متفاوت  صفحه بسیار ساده تر می شود.


<h2>

6.1.	نوشتن XML

</h2>
با استفاده از فرهنگ لغات XML در اندروید ، به راحتی و سریعتر می توانید layout های UIو المان های صفحه نمایش را طراحی کنید.هر فایل layout باید شامل دقیقا یک المان root باشد که باید یا View و ViewGroup باشد.هنگامی که المان root را تعریف می کنید، می توانید layout اضافی یا ویجت های دیگی را نیز به عنوان المان فرزند اضافه نمایید و بدین ترتیب سلسله مراتبی از View بتدریج ساخته می شود که layout شما را تعریف می کند. به مثال زیر توجه نماید :

<div dir="ltr" align="left" style=" background-color:rgba(50, 115, 220, 0.3);" >
<?xml version=”1.0” encoding=”utf-8”?>
<LinearLayout xmlns:android=”http://schemas.android.com/apk/res/android” <br/>
              android:layout_width=”match_parent” <br/>
              android:layout_height=”match_parent” <br/>
              android:orientation=”vertical” >
<br/>
    <TextView android:id=”@+id/text” <br/>
              android:layout_width=”wrap_content” <br/>
              android:layout_height=”wrap_content” <br/>
              android:text=”Hello, I am a TextView” />
<br/>			  
    <Button android:id=”@+id/button” <br/>
            android:layout_width=”wrap_content” <br/>
            android:layout_height=”wrap_content” <br/>
            android:text=”Hello, I am a Button” />
<br/>			
</LinearLayout>
</div>
بعد از اینکه layout را در XML تعریف کردید ، فایل را با پسوند .xml در مسیر res/layout پروژه ذخیره سازی کنید و بدین ترتیب به درستی کامپایل خواهد شد. 

<h2>

6.2.	بارگذاری منبع XML

</h2>

هنگامی که برنامه خود را کامپایل می کنید ، هر فایل XML layout به منبع  View کامپایل می شود.شما باید layout را از کد برنامه خود و در پیاده سازی callback Activity.onCreate() بارگذاری کنید.این کار را با فراخوانی setContentView() و با ارسال مرجعی  به منبع layout خود به فرم R.layout.Layout_File_Name انجام می دهید.برای مثال ، اگر layout به شکل main_layout.xml ذخیره می شود ، شما آن را به شکل زیر بارگذاری می کنید:
<div dir="ltr" align="left" style=" background-color:rgba(50, 115, 220, 0.3);" >
public void onCreate(Bundle savedInstanceState) {
<br/>			
    super.onCreate(savedInstanceState);
	<br/>			
    setContentView(R.layout.main_layout);
	<br/>			
}
</div>
متد callback onCreate() در اکتیویتی توسط فریم ورک اندروید زمانی که Acivity راه اندازی  می گردد ، فراخوانی می شود.

<h2>

6.3.	ATTRIBUTES

</h2>
هر View و ViewGroup ، attribute های متعدد XML خود را پشتیبانی می کندبرخی از این attribute ها مختص یک شی View هستند (مثال : TextView ، attribute textSize را پشتیبانی می کند) اما این attribute ها همچنین توسط هر شی View دیگری که ممکن است از آن کلاس ارث بری کند هم به ارث برده می شود.برخی از آن ها بین تمام اشیا View مشترک هستند چون از یک کلاس ریشه ای View ارث بری کرده اند ، مانند attribute id.
<br/>
دیگر attribute ها بعنوان layout parameters در نظر گرفته می شوند که attribute هایی هستند که جهت layout مشخص شی View شرح می دهد مانند آنچه توسط شی والد ViewGroup شی تعریف می شود.


<h2>
6.4.	ID
</h2>
هر شی View ممکن است یک integer ID داشته باشد که مرتبط با آن است ، تا بدین ترتیب در درخت View شناخته شود.هنگامی که app کامپایل می شود ، به این ID بعنوان یک integer ارجاع می شود اما ID که در فایل CML منتسب می شود به شکل یک رشته در attribute id است.id attribute مشترک در بین تمامی اشیا View است که توسط کلاس View تعریف می شود و اغلب از آن نیز استفاده می شود.سینتکس آن به شکل زیر است:
<div dir="ltr" align="left" style=" background-color:rgba(50, 115, 220, 0.3);" >
android:id="@+id/my_button"
</div>
سمبل @ در ابتدای رشته تعیین کننده این است که پارسر XML باید ادامه رشته ID را پارس کند و تعمیم دهد و آن را بعنوان یک منبع ID بشناسد.سمبل (+) یعنی اینکه این یک نام منبع جدید است که باید ایجاد شده و به منابع ما در فایل R.java اضافه گردد.هنگامی که به یک منبع ID اشاره می کنید نیازی به استفاده از سمبل + نیست اما باید namasepace پکیج اندروید را اضافه کنید مانند زیر:
<div dir="ltr" align="left" style=" background-color:rgba(50, 115, 220, 0.3);" >
android:id="@android:id/empty"
</div>
هنگامی که از namespace پکیج اندروید استفاده می کنیم به ID از کلاس منبع android.R  به جای کلاس منبع محلی اشاره می کنیم.در واقع در android.R نام ها تعریف شده وجود دارند .
 <br/>
به منظور ایجاد View ها و اشاره و ارجاع به آن ها از app پترن مشترک به شکل زیر است:

1.	یک view/widget را در فایل layout تعریف کنید و به آن یک ID یکتا منتسب کنید.
<div dir="ltr" align="left" style=" background-color:rgba(50, 115, 220, 0.3);" >
<Button android:id="@+id/my_button"
<br/>
        android:layout_width="wrap_content"
		<br/>
        android:layout_height="wrap_content"
		<br/>
        android:text="@string/my_button_text"/>
		<br/>
</div>

2.	سپس نمونه ای از شی View را ساخته و از layout آن را پیدا کنید (به طور معمول در متد onCreate() اتفاق می افتد).
<div dir="ltr" align="left" style=" background-color:rgba(50, 115, 220, 0.3);" >
Button myButton = (Button) findViewById(R.id.my_button);
</div>
تعریف ID ها زمانی که RelativeLayout ایجاد میکنید مهمتر می شود.در RelativeLayout ، view های مجاور میتوانند layout های خود را نسبت به view مجاور دیگر تعریف کند که توسط یک ID یکتا بدان ارجاع می شود.یک ID نیازی نیست تا در کل درخت یکتا باشد اما بهتر است در بخشی از درخت که در آن جستجو می کنید یکتا باشد ، که ممکن است اغلب کل درخت باشد بنابراین بهتر است کاملا یکتا باشد.


<h2>
6.5.	پارامترهای LAYOUT
</h2>
Attribute های layout XML ،که مثلا layout_something نامیده می شود پارامترهای layout رابرای View تعریف می کند که این View مناسب ViewGroup ای هست که در آن قرار گرفته است.هر کلاس ViewGroup یک کلاس تو در تو   را پیاده سازی می کند که ViewGroup.LayoutParams را ارث بری می کند.این زیر کلاس شامل انواع خصوصیت  است که سایز و جایگاه مناسب هر کدام از view های فرزند را برای ViewGroup تعریف می کند.
<div align="center">
 <p><img src="../assets/images/parameterLayout.png" alt="android parameter layouts screenshot" /></p>
 Figure 2. Visualization of a view hierarchy with layout parameters associated with each view
</div>
توجه داشته باشید که هر زیر کلاس LayoutParams سینتکس خودش رابرای ست کردن مقادیر دارد.هر المان فرزند باید LayoutParams خود را تعریف کند که مناسب والد خودش باشد.اگرچه ممکن است LayoutParams متفاوتی را برای فرزندش تعریف کند.
 <br/>
 تمام ViewGroup ها شامل width و height هستند (layout_width و layout_height) و هر view ملزم به تعریف آن هاست.بسیاری از LayoutParams ها شامل مارجین و border های اختیاری هم هستند.شما می توانید طول و عرض را با مقدار دقیق مشخص کنید که اغلب اگر این کار را نکنید بهتر است.در اغلب اوقات یکی از مقادیر زیر را برا ی طول و عرض ست می کنید:

•	Wrap_content : view را به اندازه ای که نیازمند نمایش محتوایش هست بزرگ می کند.

•	Match_parent : اندازه view به اندازه بزرگی view group والدش می شود.

در کل ، تعیین طول و عرض layout با استفاده از واحدهای مطلق و قطعی مانند pixel توصیه نمی شود.در عوض استفاده از اندازه های نسبی مانند واحدهای مستقل از پیکسل (dp) ، wrap_content و یا match_parent شیوه ای بهتر است.چون با این روش می توانید مطمئن باشید که برنامه شما در دستگاه های مختلف با اندازه های مخنلف صفحه نمایش به صورتی مناسب نمایش داده می شود.

<h2>
6.6.	LAYOUT POSITION
</h2>
هندسه view مستطیل است.view مکان دارد که با مختصات چپ و بالا بیان می شود و دو بعد دارد که با طول و عرض بیان می شود.واحد مکان و بعد آن پیکسل است.بازیابی مکان view با استفاده از getLeft() و getTop() امکان پذیر است.اولی مختصات چپ یا X مستطیلی که نماینده view هست برمی گرداند و دومی مختصات top یا Y مستطیل view رابرمیگرداند.این متدها هر دو مکان view را به نسبت والدشان برمیگردانند.برای نمونه زمانی که getLeft() ، 20 را برمیگرداند بدین معنی است که view نسبت به لبه چپ والد مستقیمش 20 پیکسل در راست قراردارد .بعلاوه اینکه ، بسیاری از متدهای دیگر هم هستند که برای جلوگیری از محاسبات غیر ضروری پیشنهاد شده اند مانند getRight() و getBottom() .این متدها مختصات لبه های راست و پایین مستطیلی را که نماینده view هست برمی گرداند.برای مثال ، فراخوانی getRight() مشابه محاسبه getLeft()+getWidth() است.
<h2>
6.7.	SIZE,PADDING و MARGIN
</h2>
سایز یک view بیان کننده طول و عرض آن است. یک view مطمئنا شامل دو جفت از مقادیر طول و عرض می باشد.اولین جفت به عنوان عرض اندازه گیری شده  و ارتفاع اندازه گیری شده  شناخته می شود. این ابعاد در واقع تعیین کننده و مشخص کننده میزان بزرگی view  در والدش است.این ابعاد می توانند با فراخوانی دو متد getMeasuredWidth() و getMeasuredHeight() بدست آورده شوند.دومین جفت به نام عرض و ارتفاع یا گاهی هم به نام عرض ترسیمی  و یا ارتفاع ترسیمی   شناخته می شود.این ابعاد اندازه واقعی view را برروی صفحه نمایش در زمان ترسیم تعریف می کنداین مقادیر ممکن است متفاوت از measured width و measured height باشد البته اجبار نیست.این عرض و ارتفاع با فراخوانی متدهای getWidth() و gteHeight() بدست می آیند.برای اندازه گیری ابعاد ، view ، padding را نیز به حساب می آورد.padding برای چپ ، بالا ، راست و پایین بخش view و به پیکسل بیان می شود.padding می تواند برای افست محتوا از view با تعداد پیکسل مشخص استفاده شود.برا ی نمونه left padding=2 محتوای view را به اندازه 2 پیکسل به سمت راست لبه سمت چپ view هل می دهد.padding را با استفاده از setPadding(int, int,int,int) می توان تنظیم کرد و با فراخوانی getPaddingLeft() ، getPaddingTop() ، getPaddingRight() و getPaddingBottom() می توان مقادیرش را بدست آورد.اگرچه view می تواند یک padding را تعریف کند ، نمی تواند هیچگونه پشتیبانی برا مارجین ها ارائه دهد.اما View Group ها چنین پشتیبانی را دارند.

SDK اندروید شامل layout های زیر است که ممکن است در طراحی واسط کاربری مورد استفاده قرار می گیرد:

•	ConstraintLayout

این layout در اندروید 7 معرفی شد ، استفاده از این layout manager برای بسیاری از نیازمندی های layout توصیه شده است.ConstraintLayout این امکان را فراهم می آورد تارفتار و مکان  view ها را در layout با تنظیمات ساده و محدود بتوان تعریف نمود. انعطاف پذیری این layout باعث می شود تا layout های پیچیده بدون نیاز به استفاده از layout ها ی تو در تو به سادگی و سریعتر ایجاد نمود که در نهایت منجر به بهبود کارایی layout می شود.

•	LinearLayout

در این layout View ها در یک ردیف یا یک ستون بسته به جهت انتخاب شده قرار داده می شوند.مقدار weight یا وزن برروی هر کدام از فرزند ها می تواند انتخاب شود که بدین شکل میزان فضایی که آن فرزند از layout نسبت به دیگر فرزندان میگیرد مشخص می شود.

•	TableLayout

View های فرزند را به فرمت جدولی از سطر و ستون سازماندهی می کند.هر سطر در جدول توسط شی فرزند TableRow نمایش داده می شود .

•	FrameLayout

هدف FrameLayout تخصیص بخشی از صفحه نمایش عمدتا برای نمایش یک View است.اگر چند فرزند به آن اضافه شود به صورت پیش فرض ، هر کدام بالای دیگری در بخش بالا ،سمت چپ فضای layout قرار می گیرد.راه دیگر برای قراردادن این view های فرزند استفاده از تنظیم مقدار gravity برروی هر فرزند است.

•	RelativeLayout

RelativeLayout این امکان را فراهم می کند تا view های فرزند هم نسبت به یکدیگر و هم نسبت به layout والد قرار بگیرند.

•	AbsoluteLayout

در AbsoluteLayout هر view فرزند در مختصات مشخص X و Y از layout قرار می گیرد.استفاده از این layout توصیه نمی شود چون از انعطاف پذیری لازم در تغییرات سایز و جهت صفحه نمایش برخوردار نیست.

•	GridLayout

هر نمونه از GridLayout توسط خطوط نامرئی تقسیم بندی می شود که جدولی از سطرها و ستون ها تشکیل می دهد.View های فرزند در سلول ها قرار می گیرد و ممکن است به شکلی تنظیم شود که چندین سلول را هم به طور افقی و هم به طور عمودی پوشش دهد و بدین ترتیب این امکان را فراهم می آورد که بازه وسیعی از گزینه های layout به سادگی و سریع یاده سازی شود.فاصله بین کامپوننت ها در GridLayout ممکن است با قرار دادن نوع خاصی از view به نام Space View در سلول های مجاور یا با تنظیم پارامترهای مارجین پیاده سازی شوند.

•	CoordinatorLayout 

این layout در واقع بعنوان بخشی از کتابخانه Android Design Support در اندروید 5 معرفی شد.CoordinatorLayout به صورت خاص برای هماهنگی ظاهر و رفتار appbar در بالای صفحه نمایش برنامه با دیگر المان های view طراحی شده است.در هنگام ایجاد یک activity جدید در قالب Activity Basic ، view والد در layout اصلی با استفاده از CoordinatorLayout پیاده سازی می شود.


<div style=" background-color:rgba(50, 115, 220, 0.3);" >
 	نکته:
	
LinearLayout های تو در تو با وجود layout_weight و همینطور relativeLayout های تودرتو هزینه layout را به صورت نمایی افزایش می دهند . در این جا بود که constraintLayout برای نجات ظهور پیدا کرد!
</div>
<h2>
6.8.	CONSTRAINTLAYOUT
</h2>


https://developer.android.com/training/constraint-layout

https://codelabs.developers.google.com/codelabs/constraint-layout/index.html#11

https://medium.com/exploring-android/exploring-the-new-android-constraintlayout-eed37fe8d8f1

https://www.journaldev.com/13590/android-constraintlayout

<h2>
6.9.	LINEARLAYOUT
</h2>
برای کارایی هر چه بهتر و پشتیبانی ابزار ، بهتر است از ConstraintLayout استفاده نمایید.

Android Layout  گروهی از view هاست که به صورت عمودی و یا افقی تراز و ردیف می شوند.

<p><img src="../assets/images/linearLayout1.png" alt="android linear layouts vertical screenshot" /></p>

<p><img src="../assets/images/linearLayoutHorizontal.png" alt="android linear layouts horizontal screenshot" /></p>

•	Attribute ها در LinearLayout

<table>
  <tr>
    <th>ردیف</th>
    <th>Attribute ها و توضیحات</th>
    
  </tr>
  <tr>
    <td>1</td>
    <td>Android:id
	<br/>
	ID است که view با آن شناسایی می شود.
	</td>
    
  </tr>
  <tr>
    <td>2</td>
    <td>android:baselineAligned
	<br/>
	مقدار آن true و یا false می باشد که از ترازشدن baseline ویوهای فرزند جلوگیری می کند.
	</td>    
  </tr>
   <tr>
    <td>3</td>
    <td>android:baselineAlignedChildIndex
	<br/>
	هنگامی که linearLayout بخشی از LAYOUT دیگری باشد که baseline آنها با یکدیگر تراز است می تواند بدین ترتیب مشخص نماید کدامیک از فرزندانش با baseline تراز باشد.
	</td>    
  </tr>
   <tr>
    <td>4</td>
    <td>android:divider
	<br/>
	در واقع خط ترسیمی به صورت عمودی بین دکمه هاست .برای آن مقدار رنگی را که مدنظر دارید انتخاب میکنید که به این شکل می باشد: #rgb,#argb,#rrggbb,و یا #aarrggbb
	</td>    
  </tr>
   <tr>
    <td>5 </td>
    <td>android:gravity
	<br/>
	در واقع تعیین کننده آن است که شی چگونه محتوایش را در دو محور X و Y نمایش می دهد .مقادیر ممکن برای آن top، bottom ، left ، right ،center ،center_vertical ، center_horizontal می باشد.
	</td>    
  </tr>
   <tr>
    <td>6 </td>
    <td>android:orientation
	<br/>
	جهت چیدمان را تعیین می کند که برای ردیف horizontal و برای ستون vertical است.مقدار پیش فرض horizontal است.
	</td>    
  </tr>
   <tr>
    <td>7</td>
    <td>android:weightSum
	<br/>
	مجموع وزن ویوهای فرزند است.
	</td>    
  </tr>
  
</table>

در این layout می بایست کنترل مناسبی برروی width و height درزمان طراحی داشته باشیم.
<div dir="ltr" align ="left">

1. Layout_width:”fill_parent”
<br/>
2. Layout_width:”match_parent”
<br/>
3. Layout_width:”wrap_content”
</div>

1.  براساس عرض صفحه نمایش عرض را تعیین می کند.

2. براساس عرض ویو والد عرض را تعیین می کند.

3.  براساس عرض محتوا عرض را تعیین می کند.



