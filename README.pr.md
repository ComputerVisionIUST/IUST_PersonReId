# مجموعه داده IUST_PersonReId <p align="left"> [![per](https://img.shields.io/badge/lang-en-red.svg)](https://github.com/ComputerVisionIUST/IUST_PersonReId/blob/main/README.md) [![tr](https://img.shields.io/badge/lang-pr-yellow.svg)](https://github.com/aytakg /reid/blob/main/README.pr.md) </p>

![1](https://github.com/IRUIST/Iranians_Reid_dataset/assets/141324225/782122d5-235a-4314-9d81-7eceec56c960)

### درباره مجموعه داده

مجموعه داده IRUST با مجموعه داده های بین المللی متفاوت است و با توجه به فرهنگ و محیط ایران تهیه شده است. در این مجموعه داده، سعی شده است فیلم داده های خام از مکان ها و شرایطی که طیف وسیعی از چالش ها (کیفیت فیلم، نور، تنوع، زاویه دوربین و ...) را در مجموعه داده ها حفظ می کند، ضبط شود. همپوشانی میدان دید در بین دوربین های مختلف وجود دارد. بنابراین، این مجموعه داده می تواند نماینده خوبی برای مجموعه داده های دنیای واقعی باشد.
این فیلم ها در مکان هایی مانند دانشگاه علم و صنعت ایران، مسجد الائمه، راهپیمایی اربعین، میوه فروشی محلی و سوپرمارکت تهران توسط دوربین هایی با کیفیت وضوح متفاوت ضبط شده است که جزئیات آن به تفکیک در جدول زیر آمده است.

| مکان | دوربین ها | کل ساعت | وضوح |تعداد روز|
| ------ | :---: | :---: | :---: | :---: |
| دانشگاه علم و صنعت ایران | 17 | 383 ساعت| متغیر| 5|
| مسجد الائمه | 5 | 40 ساعت| 960×1080 | 2|
| میوه فروشی محلی | 7 | 38 ساعت | 944×1080 | 1 |
| سوپرمارکت محلی | 6 | 124 ساعت | 1280×1944 | 4 |
| راهپیمایی اربعین | 2 | 3 ساعت | 1280×720 | 5 |

مقایسه آماری مجموعه داده های برچسب دار معروف جهان با مجموعه داده های ما در جدول زیر آورده شده است:

| مجموعه داده | مکان | ID-چند دوربین | ID-تک دوربین | صحنه ها | تصاویر |
| ----- | ------ | :---: | :---: | :---: | :---: |
| ScoreNet | لیگ های فوتبال | 243432 | - | -| 340993|
| MSMT17 | پردیس دانشگاه | 4101 | - | 15| 126441 |
| Duke | پردیس دانشگاه دوک | 1413 | 439 | 8 | 466261 |
| MARS | پردیس دانشگاه Tsinghua | 1261 | - | 6 | 1191003 |
| Market1501 | سوپرمارکت در دانشگاه Tsinghua | 1501 | - | 6 | 32217 |
| IUST | جاهای مختلف داخل ایران | 1878 | 1327 | 19 | - |



تعداد شناسه هایی که در چندین دوربین همگام شده اند مشاهده شده است:
<p align="center"><img src="![_Labeled Data](https://github.com/user-attachments/assets/67226f29-5ab6-4e36-ac66-b910b48faad1)" width="750"/ </p>

![356862965-67af25b9-d743-44a2-96f3-b51eed0e8a08](https://github.com/user-attachments/assets/490f0d3e-db4a-47a0-a719b-59)


### به روز رسانی...
در حال حاضر، بیش از 270000 فریم حاوی 32668 جعبه حاشیه نویسی با 3205 هویت در بین ویدیوهای خام حاشیه نویسی شده است. از این میان، 1878 هویت متعلق به افرادی است که در 2 دوربین یا بیشتر دیده شده اند و 1327 هویت متعلق به افرادی است که تنها در محدوده 1 دوربین حضور داشته اند. همچنین از نظر جنسیت، این مجموعه داده شامل 50 هویت زنانه و 20 هویت مردانه است. مجموعه داده IRUST دارای چهار ویژگی برجسته است:

ابتدا، از مدل [YOLOE](https://github.com/PaddlePaddle/PaddleDetection/blob/release/2.7/deploy/pipeline/docs/tutorials/pphuman_mot_en.md) استفاده می کند که در [crowdhuman] (https:/) /www.crowdhuman.org/) مجموعه داده به عنوان ردیابی عابر پیاده.

دوم، از آنجایی که مدل‌های هوش مصنوعی بالا ممکن است به اندازه کافی کارآمد نباشند (مانند عدم شناسایی هنگام ورود و خروج از محدوده دوربین، عدم شناسایی افراد محجبه، عدم شناسایی تجهیزات عابر پیاده، یا تعویض شناسه‌ها و غیره)، حاشیه‌نویس‌های انسانی حاشیه‌نویسی را تغییر می‌دهند. می دهند. به گونه ای ساخته شده است که کمترین خطای ممکن در آموزش مدل ها از نظر مجموعه داده رخ دهد.

سوم، یک مدل اولیه شناسایی مجدد افراد با استفاده از [Swin Transformer] (https://github.com/layumi/Person_reID_baseline_pytorch) روی تصاویر برش خورده فریم ها اجرا شد.

چهارم، از ناظران انسانی برای تصحیح خطاهای شناسایی مجدد افراد در دوربین های مختلف به همراه الگوریتم شناسایی مجدد زمانی استفاده شد. این کار در چارچوب یک برنامه کاربردی توسعه یافته خاص با موضوع شناسایی مجدد انجام می شود.


برای اطلاع از جزئیات قوانین حاشیه نویسی، می توانید به [لینک] زیر مراجعه کنید (https://docs.google.com/document/d/1Upnm1nJ9e8Jn3odAjlbICwgNXtRzPghF7wl5_eQRcdo/edit?usp=sharing)


در دموهای زیر، به ترتیب دلیل عدم کفایت استفاده از مدل های هوش مصنوعی در بازشناسی افراد و تشخیص انسان مشخص است
https://github.com/IRUIST/Iranians_Reid_dataset/assets/141324225/fde81249-5d40-4a11-9be4-2117e11c2896
<p align="center">
 <img src="https://github.com/user-attachments/assets/28014e07-35b1-47c8-b7e5-0abfdcafec30" alt="animated" />
</p>

<p align="center">
 <img src="https://github.com/user-attachments/assets/11399f88-e4a1-4f0b-80ea-75225e1ac246" alt="animated" />
</p>



<div align="center">
 <video src="https://github.com/user-attachments/assets/ef987d49-9f29-423d-a4c4-b7f0a9b2b612" />
</div>



<div align="center">
 <video src="https://github.com/user-attachments/assets/aa5ee71a-a359-484e-8e5b-da43611097a5" width="600" />
</div>




همچنین این مجموعه داده شامل تصاویر افرادی است که با لباس های مشابه جلوی دوربین نیستند.
به تصویر زیر دقت کنید این هویت در چند قاب با چادر و در بقیه قاب ها با مانتو وجود داشت.


![image](https://github.com/user-attachments/assets/03590215-9ce6-42d7-8e50-36a6baea79d5)



### مجموعه داده را دانلود کنید
می‌توانید بسته مجموعه داده را از [اینجا] دانلود کنید (https://drive.google.com/file/d/1BoBmL1FtYON4coItUbvBFWlS4vUw8Qz_/view?usp=sharing)

### فرمت نامگذاری Bboxes

به عنوان مثال: C1_F6595_ID10.jpeg

"C1" شماره دوربین در آن مکان خاص است.

"F6595" شماره فریم آن شخص در فیلم پارتیشن بندی شده است.

«ID10» شماره هویت فرد در مجموعه ارائه شده است.
