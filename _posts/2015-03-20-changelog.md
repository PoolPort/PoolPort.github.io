---
layout: page
title: "تغییرات پکیج"
subtitle: "Change log"
category: others
date: 2015-03-20 13:08:28
---
### تغیرات نسخه 3.7.1
* اضافه شدن متد ``verifyLock`` - این متد با استفاده از قابلیت قفل رکورد در mySQL جلوی درخواست‌های تکراری در زمان verify کردن را میگیرد.

### تغیرات نسخه 3.7.0
* اضافه شدن درگاه جیبیت
* رفع خطای درگاه زرین پال - ذخیره تومان به جای ریال در دیتابیس
* تغییر در دیتابیس - فیلد result_code در جدول poolport_status_log از varchar 10 به varchar 255 تغییر کرد

### تغیرات نسخه 3.6.0
* اضافه شدن درگاه بانک پارسیان

### تغیرات نسخه 3.5.0
* اضافه شدن درگاه بانک سامان
* اضافه شدن درگاه سایت pay.ir

### تغییرات نسخه 3.4.0
* اضافه شدن درگاه شبیه سازی کننده
* اضافه شدن متد ```setGlobalCallbackUrl``` برای تغییر همه آدرسهای بازگشت برای همه درگاه‌ها

### تغییرات نسخه 3.3.0
* اضافه شدن درگاه ایران کیش
* اضافه شدن ویژگی soap attempts - تلاش دوباره اگر ارتباط با سرور soap برقرار نشد

### تغییرات نسخه 3.2.0
* اضافه شدن درگاه بانک صادرات

### تغییرات نسخه 3.0.0
* تغییر نام پکیج از IPay به PoolPort
* اضافه شدن درگاه جهان‌پی
* اضافه شدن درگاه پی‌لاین
* اضافه شدن درگاه پارسیان
* ساخت یک API برای تمام درگاه‌ها
* ساخت جدول برای تمام درگاه‌ها

### تغییرات نسخه 2.0.0
* استفاده از فایل تنظمیات برای گرفتن تنظیمات مورد نیاز کاربر (عالیه!)
* ایجاد خودکار جدول‌های دیتابیس
* {زرین پال} امکان ریدارکت به زرین گیت

### تغییرات نسخه 1.1.0
* اضافه شده درگاه زرین پال
* ویرایش ```namespace``` پکیج (حذف ```mohsen``` از ```namespace```)
* استفاده از ```PSR-4``` به جای ```PSR-0```
* برطرف کردن باگ در API بانک ملت

### تغییرات نسخه 1.0.0
* انتشار نسخه اولیه
* اضافه شدن درگاه بانک ملت
