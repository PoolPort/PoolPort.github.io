---
layout: default
title: "پکیج PoolPort"
---

# پکیج PoolPort

- [PoolPort چیست؟](#what-is-poolport)
- [نسخه 3](#version-3)
- [راه‌اندازی سریع](#quick-start)
- [توسعه دهندگان](#developers)

<a name="what-is-poolport"></a>
## PoolPort چیست؟

پکیج PoolPort یک پکیج Composer برای زبان PHP است و در تمام پروژه های PHP قابل استفاده است. این پکیج برای برقراری با درگاه های بانک های مختلف است. با استفاده از این پکیج میتوانید به تمام درگاه هایی که در این پکیج پشتیبانی میشوند با یک API یکسان دسترسی داشته باشید.

<a name="version-3"></a>
## نسخه 3

ما واقعا برای انتشار نسخه 3 هیجان زده هستیم. این نسخه تغییرات زیادی نسبت به نسخه‌های پیشین داشته و استفاده از این نسخه بسیار راحت است.

در حال حاظر ما در نسخه بتا ورژن 3 هستیم. لطفا برای کمک به این پکیج، این کتابخانه را در نصب و خطاهای آن را در قسمت [Issues](https://github.com/mohsen-shafiee/IPay/issues) پکیج گزارش دهید تا برای انتشار نسخه 3 آماده شویم.

<a name="quick-start"></a>
## راه اندازی سریع
در این بخش می‌توانید بسیار سریع پروژه خود را به درگاه متصل کنید.

***نکته مهم: پکیج در حال حاظر در نسخه بتا است، لطفا در محیط Production از آن استفاده نکنید.***

### نصب
دستور زیر را در ترمینال اجرا کنید تا PoolPort نسخه بتا نصب شود.

```
composer require poolport/poolport:v3.0.0-beta1
```

### تنظیمات پکیج

فایلی با نام ```poolport.php``` را در کنار پوشه ```vendor``` ایجاد کرده و درون آن کدهای موجود در
<a href="https://github.com/PoolPort/PoolPort/blob/master/poolport-sample.php" target="_blank">این صفحه</a>
را قرار دهید.

تنظیمات واضح هستند. به هر درگاه‌یی که میخواهید متصل شوید، ابتدا تنظیمات آن را در این فایل پر کنید.

نکته: پس از اولین اجرای درست پکیج، حتما مقدار ```create``` در ```database``` را برابر ```false``` قرار دهید.

### نوشتن کدها
خب کدهای زیر را در فایل منتقل کننده به درگاه قرار دهید.

```php
<?php
use PoolPort\PoolPort;

$poolPort = new PoolPort(PoolPort::P_MELLAT);
try {
    $refId = $poolPort->set(1000)->ready()->refId();

    // Your code here

    $poolPort->redirect();
} catch (Exception $e) {
    echo $e->getMessage();
}
```

* به جای ```P_MELLAT``` میتوانید درگاه‌های دیگر را بنویسید: {```P_MELLAT```, ```P_SADAD```, ```P_ZARINPAL```, ```P_PAYLINE```}

* در متد ```set``` می‌توانید هزینه را به ریال وارد کنید.

کدهای زیر را نیز در فایل callback بنویسید.

```php
<?php
use PoolPort\PoolPort;

try {
    $poolPort = new PoolPort;
    $trackingCode = $poolPort->verify()->trackingCode();
    $refId = $poolPort->refId();
    $cardNumber = $poolPort->cardNumber();

    // Your code here

} catch (Exception $e) {
    echo $e->getMessage();
}
```

تبریک میگم. اگر تنظیمات را به درستی وارد کرده باشید و درگاه شما نیز درست باشد، با موفقیت به درگاه متصل شدید.

اطلاعات بیشتر در مورد API را می‌توانید در <a href="./doc/version-3.html">اینجا</a> مشاهده کنید.

<a name="developers"></a>
## توسعه دهندگان

PoolPort یک پکیج متن باز است و ما از همکاری شما در توسعه این پکیج به شدت استقبال میکنیم. شما می‌توانید از یکی از راه‌های زیر به توسعه بیشتر این پکیج کمک کنید:

* نصب PoolPort و گزارش خطاها و پیشنهادات
* بهبود مستندات پکیج
* همکاری در نوشتن کدهای اصلی پکیج
* پورت کردن PoolPort به سیستم‌های دیگر نظیر وردپرس

### لیست توسعه دهندگان اصلی پکیج

* محسن شفیعی [Github](https://github.com/m-jch), [Email](mailto:mohsen.sh12@hotmail.com)
* رضا زارع [Github](https://github.com/Reza1607), [Email](mailto:rz.zare@gmail.com)
* [و همه دوستانی که به ما در توسعه این پکیج کمک میکنند](https://github.com/PoolPort/PoolPort/graphs/contributors).
