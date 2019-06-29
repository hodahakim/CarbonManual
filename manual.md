
 ‫CARBON یک توزیع آماده ‫گنو/لینوکسی است که در چندین نسخه، از بسته‌های نرم‌افزاری مختلف در زمینه‌ی علم مواد پشتیبانی می‌کند.‬    
 ‫هدف از تولید CARBON این بوده است که شما بدون نیاز به طی کردن فرآیند پیچیده‌ی نصب و آماده‌سازی نرم‌افزارهای محاسباتی، بتوانید روی رایانه خود به طور آماده با آن‌ها کار کرده و تمام تمرکز خود را روی شبیه‌سازی و محاسباتتان بگذارید.‬     
    
 کاری که تیم توسعه‌ی ‫نرم‌افزارهای محاسباتی در NRTC انجام داده این بوده که یک توزیع گنو/لینوکسی ساخته که پکیج محاسباتی مورد نظر به صورت بهینه روی آن نصب شده است. این توزیع محاسباتی قابلیت این را دارد که به روی سیستم‌عامل شما (چه با GNU/Linux کار کنید و چه کاربر Windows باشید) به صورت یک ماشین مجازی اجرا شود، بدون اینکه با سیستم اصلی شما تداخل داشته باشد.‬        


‫در این راهنما به طور کامل با راه‌اندازی CARBON  روی رایانه خود آشنا می‌شوید.

------------------

### **‫راهنمای کاربران GNU/Linux‬**

‫‫برای استفاده از CARBON شما باید دو برنامه‌ی virtualbox و vagrant را دریافت کنید تا بتوانید بواسطه آن‌ها توزیع محاسباتی CARBON را به طور مجازی روی سیستم خود اجرا و مدیریت کنید.‬        
‫دقت کنید که هردوی این سایت‌ها تحریم هستند و  شما برای دانلود برنامه‌ها نیاز به vpn دارید.‬

‫ابتدا آخرین نسخه virtualbox  را مطابق با سیستم عامل خود از آدرس زیر دریافت کنید:‫

https://www.virtualbox.org/wiki/Downloads

![lin1.vbdownload](./images/lin1.vbdownload.png)

![lin2.vblinux](./images/lin2.vblinux.png)

![lin3.vbdebian](./images/lin3.vbdebian.png)

‫فایل virtualbox-6.0_6.0.8-130520_Debian_stretch_amd64.deb  دانلود شده و در مسیر پیشفرض Download  قرار می‌گیرد.‬

‫با دستورات زیر در مسیر جاری برنامه قرار گرفته و برنامه  را نصب می‌کنیم:‬
‍‍‍
```
$ cd Download
```

![lin4.cd](./images/lin4.cd.png)

‫دقت کنید که برای نصب، نیاز به دسترسی کابر ریشه (root) دارید:‬

```
# sudo dpkg -i virtualbox-6.0_6.0.8-130520~Debian~stretch_amd64.deb
```
![lin5.sudovb](./images/lin5.sudovb.png)

و یا

![lin6.suvb](./images/lin6.suvb.png)


‫همچنین vagrant را نیز مطابق با سیستم عامل خود از آدرس زیر دریافت و نصب کنید:‬

https://www.vagrantup.com/downloads.html

![lin7.vagrantdownload](./images/lin7.vagrantdownload.png)

![lin8.vagrantdebian](./images/lin8.vagrantdebian.png)


```
$ cd /Download
$ dpkg -i vagrant_2.2.4_x86_64.deb
```
![lin4.cd](./images/lin4.cd.png)

![lin9.suvagrant](./images/lin9.suvagrant.png)
و یا   

![lin10.suvagrant](./images/lin10.suvagrant.png)

‫حال به پوشه‌ای که دیتاهای محاسباتی شما در آن است بروید و دستور زیر را وارد کنید:‬

```
$ vagrant init nrtc/carbon-qe-intel --box-version  0.2

$ vagrant up
```
![lin11.data](./images/lin11.data.png)

![lin12.vagrantinit](./images/lin12.vagrantinit.png)
  
![lin13.vagrantupstart](./images/lin13.vagrantupstart.png)

‫در این مرحله باید اندکی صبر کنید تا باکس کربن از [vagrant cloud](https://app.vagrantup.com/nrtc/boxes/carbon-qe-intel) دریافت شود.
‫بهتر است که حوصله‌ی شما متناسب با معکوس سرعت اینترنت‌تان باشد!‬

![lin14.vagrantupwait](./images/lin14.vagrantupwait.png)

‫اکنون توزیع محاسباتی CARBON بر روی رایانه شما راه اندازی شده است.‬

![lin15.vagrantupfinish](./images/lin15.vagrantupfinish.png)


  فقط‫ کافی است تا با دستور زیر وارد محیط CARBON شوید و مدیریت ماشین محاسباتی خود را در دست بگیرید:‬

```
$ vagrant ssh
```
![lin16.vagrantssh](./images/lin16.vagrantssh.png)
  
‫می‌بینید که خط‌فرمان شما از محیط سیستم عامل اصلی، به محیط سیستم‌عامل محاسباتی CARBON تغییر کرده است. ‬   

![lin17.commandline](./images/lin17.commandline.png)
  
‫شما هم اکنون می‌توانید در محیط جدید،‌ بدون نیاز به طی کردن مسیر  پردردسر نصب برنامه، از نرم افزار محاسباتی مد نظر به سادگی استفاده کنید.‬

‫برای این‌که به داده‌های خروجی و نتایج محاسباتتان در سیستم عامل اصلی دسترسی داشته باشید، کافیست تمام اطلاعاتتان را در ماشین مجازی در دایرکتوری ‪/vagrant‬ ذخیره کنید تا در همان مسیر ‪/data‬ در سیستم عامل اصلی آن‌ها را بیابید.‬

```
vagrant@nrtc/carbon:$ /vagrant
```
![lin18.cdslashvagrant](./images/lin18.cdslashvagrant.png)
  
‫برای خروج از CARBON و دسترسی به خط‌فرمان سیستم اصلی خود،کافی است که exit  را در ترمینال تایپ کنید: 

```
$ exit
```
![lin19.exit](./images/lin19.exit.png)

 ‫ویا از کلید میانبر "ctrl+D" استفاده کنید.‬

 ‫پس از خروج از ماشین مجازی CARBON،‌ برای خاموش کردن ماشین،‌ از ‬
 ```
 $ vagrant halt
 ``` 
 ‫استفاده کنید.‬

![lin20.vagranthalt](./images/lin20.vagranthalt.png)

‫داده‌های محاسباتی و همه تغییرات شما در سیستم عامل مجازی CARBON ذخیره شده است. ‬    
برای ورود و خروج‌های بعدی کافی است ‫دستورات زیر را پیش بگیرید:‬
‍‍‍
```
$ vagrant up
$ vagrant ssh
  انجام محاسبات
$ exit 
$ vagrant halt
```


------------

### **‫راهنمای کاربران Windows‬**


‫‫برای استفاده از CARBON شما باید دو برنامه‌ی virtualbox و vagrant را دریافت کنید تا بتوانید بواسطه آن‌ها توزیع محاسباتی CARBON را به طور مجازی روی سیستم خود اجرا و مدیریت کنید.‬    
‫هم‌چنین باید با محیط powershell در ویندوز خود کار کنید.‬


‫ابتدا آخرین نسخه virtualbox  را مطابق با سیستم عامل خود از آدرس زیر دریافت کنید:‫

https://www.virtualbox.org/wiki/Downloads

![win1.vbdownload](./images/win1.vbdownload.png)

![win2.vbwindows](./images/win2.vbwindows.png)



‫همچنین vagrant را نیز مطابق با سیستم عامل خود از آدرس زیر دریافت نمایید:‬

https://www.vagrantup.com/downloads.html

![win3.vagrantdownload](./images/win3.vagrantdownload.png)

![win4.vagrantwindows](./images/win4.vagrantwindows.png)

برنامه‌ها‫ی دانلود شده را طبق روال نصب کنید:‬

![win5.exe](./images/win5.exe.png)

![win6.vbinstall](./images/win6.vbinstall.png)

![win7.vagrantinstall](./images/win7.vagrantinstall.png)

‫پس از اتمام مراحل نصب، powershell ویندوز را باز کنید و به پوشه‌ای که دیتاهای محاسباتی شما در آن است بروید،‬

![win8.cd](./images/win8.cd.png)

![win9.cddata](./images/win9.cddata.png)

 
 ‫ ودستورات زیر را وارد کنید:

 ```
$ vagrant init nrtc/carbon-qe-intel --box-version  0.2
$ vagrant up
```

![win10.vagrantinit](./images/win10.vagrantinit.png)

![win11.vagrantinitfinish](./images/win11.vagrantinitfinish.png)

![win12.vagratntup](./images/win12.vagratntup.png)

‫این مرحله نیازمند اندکی حوصله است تا باکس کربن از  [vagrant cloud](https://app.vagrantup.com/nrtc/boxes/carbon-qe-intel) روی سیستم شما بارگذاری شود.‬

![win13.vagrantupfinish](./images/win13.vagrantupfinish.png)


‫حال، توزیع محاسباتی CARBON بر روی رایانه شما راه اندازی شده است.‬ فقط‫ کافی است تا با دستور زیر وارد محیط CARBON شوید و مدیریت ماشین محاسباتی خود را در دست بگیرید:‬

```
$ vagrant ssh
```
![win14.vagrantssh](./images/win14.vagrantssh.png)

‫می‌بینید که خط‌فرمان شما از محیط سیستم عامل اصلی، به محیط سیستم‌عامل محاسباتی CARBON تبدیل شده:‬

![win15.commandline](./images/win15.commandline.png)

‫شما در محیط جدید،‌ بدون نیاز به طی کردن مسیر پردردسر نصب برنامه، از نرم افزار محاسباتی مد نظر به سادگی استفاده می‌کنید.‬‬

‫برای این‌که به داده‌های خروجی و نتایج محاسبات خود در سیستم عامل اصلی هم ببینید، باید تمام اطلاعاتتان را در ماشین مجازی، در دایرکتوری ‪/vagrant‬ ذخیره کنید تا در همان مسیر ‪\data‬ در سیستم عامل اصلی به آن دسترسی داشته باشید.‬

```
vagrant@nrtc/carbon-qe-intel:$ ~/vagrant
```
![win16.cdslashvagrant](./images/win16.cdslashvagrant.png)


‫برای خروج از CARBON و دسترسی به خط‌فرمان سیستم اصلی خود،کافی است که exit  را در ترمینال تایپ کنید:‫ 

```
$ exit
```
![win17.exit](./images/win17.exit.png)

 ‫و یا از کلید میانبر "ctrl+D" استفاده کنید.‬


 ‫پس از خروج از ماشین مجازی CARBON،‌ برای خاموش کردن ماشین،‌ از دستور زیر استفاده کنید. ‬
 ```
 $ vagrant halt
 ``` 

![win18.vagranthalt](./images/win18.vagranthalt.png)

‫داده‌های محاسباتی و همه تغییرات شما در سیستم عامل مجازی CARBON ذخیره شده است. ‬    
برای ورود و خروج‌های بعدی کافی است ‫دستورات زیر را پیش بگیرید:‬
‍‍‍
```
$ vagrant up
$ vagrant ssh
  انجام محاسبات
$ exit 
$ vagrant halt
```
---

### **‫نحوه درمیان گذاشتن مشکلات CARBON با ما‬**


‫هرگونه مشکلی را که در حین کار کردن با CARBON به آن برخوردید، می‌توانید از طریق [github](https://github.com/) با ما در میان بگذراید.‬   
‫برای این‌کار باید در ریپازیتوریِ [carbon-linux](https://github.com/NRTC/carbon-linux) موجود در [اکانت گیت‌هابِ NRTC](https://github.com/NRTC) ، یک [issues](https://github.com/NRTC/carbon-linux/issues/new) ارسال کنید.‬

‫مراحل انجام این‌کار را با هم دنبال می کنیم:‬

‫برای این کار وارد اکانت github خود شده و به صفحه اصلی NRTC به آدرس زیر  بروید:‬
https://github.com/NRTC

![issue1.github](./issue1.github.png)

![issue2.login](./images/issue2.login.png)

‫به ریپازیتوری carbon-linux وارد شوید ‪

https://github.com/NRTC/carbon-linux

![issue3.repo](./images/issue3.repo.png)

‫و پایین تر از اسم مخزن، روی issue کلیک کنید.‬

![issue4.issue](./images/issue4.issue.png)

‫یک New Issue ایجاد کرده و عنوان و توضیح مشکل مدّنظر را بنویسید،‬

![issue5.newissue](./images/issue5.newissue.png)

‫و در پایان روی Submit new issue کلیک کرده و آن را ارسال کنید.‬

![issue6.submit](./images/issue6.submit.png)

‫با این روش می‌توانید، انتقاد و پیشنهادات و سایر درخواست‌های خود را با ما مطرح کنید.‬