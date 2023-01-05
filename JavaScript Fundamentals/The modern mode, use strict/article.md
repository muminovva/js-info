Zamonaviy rejim, "qat'iy foydalaning"
Uzoq vaqt davomida JavaScript moslik muammosisiz rivojlandi. Tilga yangi funksiyalar qo‘shildi, eski funksiya esa o‘zgarmadi.

Bu mavjud kodni hech qachon buzmaslikning foydasiga ega edi. Ammo salbiy tomoni shundaki, JavaScript yaratuvchilari tomonidan qilingan har qanday xato yoki nomukammal qaror tilda abadiy qolib ketgan.

Bu 2009 yilgacha ECMAScript 5 (ES5) paydo bo'lgunga qadar shunday edi. U tilga yangi xususiyatlarni qo'shdi va mavjudlarini o'zgartirdi. Eski kodning ishlashini ta'minlash uchun bunday o'zgartirishlarning aksariyati sukut bo'yicha o'chirilgan. Siz ularni maxsus direktiva bilan aniq yoqishingiz kerak: "use strict".

"qat'iy foydalaning"
Direktiv satrga o'xshaydi: "use strict"yoki 'use strict'. Agar u skriptning yuqori qismida joylashgan bo'lsa, butun skript "zamonaviy" usulda ishlaydi.

Masalan:

"use strict";

// this code works the modern way
...
Tez orada biz funktsiyalarni o'rganamiz (buyruqlarni guruhlash usuli), shuning "use strict"uchun funksiya boshida qo'yilishi mumkinligini oldindan aytib o'tamiz. Buni qilish faqat ushbu funktsiyada qat'iy rejimni yoqadi. Lekin odatda odamlar uni butun skript uchun ishlatishadi.

Yuqorida "qat'iy foydalanish" ekanligiga ishonch hosil qiling
Iltimos, u skriptlaringizning yuqori qismida joylashganligiga ishonch hosil "use strict"qiling, aks holda qattiq rejim yoqilmasligi mumkin.

Bu yerda qattiq rejim yoqilmagan:

alert("some code");
// "use strict" below is ignored--it must be at the top

"use strict";

// strict mode is not activated
Yuqorida faqat sharhlar paydo bo'lishi mumkin "use strict".

Bekor qilishning iloji yo'quse strict
"no use strict"Dvigatelni eski holatga qaytaradigan hech qanday ko'rsatma yo'q .

Qattiq rejimga kirganimizdan keyin ortga qaytish yo'q.

Brauzer konsoli
Kodni ishga tushirish uchun dasturchi konsolidan foydalanganda , u use strictsukut bo'yicha emasligini unutmang .

Ba'zan, use strictfarq qilganda, siz noto'g'ri natijalarga erishasiz.

Xo'sh, qanday qilib aslida use strictkonsolda?

Birinchidan, siz bir nechta satrlarni kiritish uchun bosishga urinib ko'rishingiz va ustiga qo'yishingiz mumkin, masalan:Shift+Enteruse strict

'use strict'; <Shift+Enter for a newline>
//  ...your code
<Enter to run>
U ko'pgina brauzerlarda, ya'ni Firefox va Chrome brauzerlarida ishlaydi.

Agar bunday bo'lmasa, masalan, eski brauzerda, ni ta'minlashning yomon, ammo ishonchli usuli bor use strict. Uni shunday o'ramga soling:

(function() {
  'use strict';

  // ...your code here...
})()
Biz "qat'iy" foydalanishimiz kerakmi?
Savol aniq tuyulishi mumkin, ammo unday emas.

Skriptlarni boshlashni tavsiya qilish mumkin "use strict"... Lekin nima ajoyib ekanligini bilasizmi?

Zamonaviy JavaScript "sinflar" va "modullar" ni qo'llab-quvvatlaydi - ilg'or til tuzilmalari (biz ularga albatta etib boramiz), ular use strictavtomatik ravishda yoqadi. "use strict"Shunday qilib , agar biz ulardan foydalansak , direktivani qo'shishimiz shart emas .

Shunday qilib, hozircha "use strict";skriptlaringizning yuqori qismida xush kelibsiz mehmon. Keyinchalik, sizning kodingiz sinflar va modullarda bo'lganda, uni o'tkazib yuborishingiz mumkin.

Hozircha biz bu haqda use strictumuman bilishimiz kerak.

Keyingi boblarda, biz til xususiyatlarini o'rganar ekanmiz, biz qattiq va eski rejimlar o'rtasidagi farqni ko'ramiz. Yaxshiyamki, ular juda ko'p emas va ular hayotimizni yaxshilaydi.

Ushbu qo'llanmadagi barcha misollar, agar boshqacha ko'rsatilmagan bo'lsa (juda kamdan-kam hollarda) qat'iy rejimni nazarda tutadi.