Kod tuzilishi
Biz o'rganadigan birinchi narsa - kodning qurilish bloklari.

Bayonotlar
Bayonotlar sintaksis tuzilmalari va amallarni bajaradigan buyruqlardir.

Biz allaqachon alert('Hello, world!')"Salom, dunyo!" xabarini ko'rsatadigan bayonotni ko'rganmiz.

Kodimizda biz xohlagancha ko'p bayonotlar bo'lishi mumkin. Bayonotlarni nuqtali vergul bilan ajratish mumkin.

Misol uchun, bu erda biz "Salom dunyo" ni ikkita ogohlantirishga ajratamiz:

alert('Hello'); alert('World');
Odatda, kodni yanada o'qilishi uchun bayonotlar alohida satrlarda yoziladi:

alert('Hello');
alert('World');
Nuqtali vergul
Ko'p hollarda satr uzilishi mavjud bo'lsa, nuqta-vergul qoldirilishi mumkin.

Bu ham ishlaydi:

alert('Hello')
alert('World')
Bu erda JavaScript satr uzilishini "noto'g'ri" nuqtali vergul sifatida izohlaydi. Bu avtomatik nuqta-vergul qo'yish deyiladi .

Aksariyat hollarda yangi qator nuqta-vergulni bildiradi. Ammo "ko'p hollarda" "har doim" degani emas!

Yangi qator nuqtali vergulni bildirmaydigan holatlar mavjud. Masalan:

alert(3 +
1
+ 2);
Kod chiqadi 6, chunki JavaScript bu yerga nuqta-vergul qo'ymaydi. Ko'rinib turibdiki, agar chiziq plyus bilan tugasa, "+"bu "to'liq bo'lmagan ifoda" bo'lib, nuqta-vergul noto'g'ri bo'ladi. Va bu holda, bu maqsadga muvofiq ishlaydi.

Biroq, JavaScript haqiqatan ham zarur bo'lgan joyda nuqta-vergul qo'yishni "muvaffaqiyatsiz" qiladigan holatlar mavjud.

Bunday hollarda yuzaga keladigan xatolarni topish va tuzatish juda qiyin.

Xatoga misol
Agar siz bunday xatoning aniq misolini ko'rishni bilmoqchi bo'lsangiz, ushbu kodni tekshiring:

alert("Hello");

[1, 2].forEach(alert);
Qavslarning ma'nosi haqida o'ylashning hojati yo'q []va forEachhali. Biz ularni keyinroq o'rganamiz. Hozircha kodni ishga tushirish natijasini eslang: u Hello, keyin 1, keyin ni ko'rsatadi 2.

Endi dan keyin nuqta-vergulni olib tashlaymiz alert:

alert("Hello")

[1, 2].forEach(alert);
Yuqoridagi kod bilan solishtirganda farq faqat bitta belgidan iborat: birinchi qatorning oxiridagi nuqta-vergul yo'qolgan.

Agar biz ushbu kodni ishga tushirsak, faqat birinchisi Helloko'rinadi (va xatolik bor, uni ko'rish uchun konsolni ochishingiz kerak bo'lishi mumkin). Boshqa raqamlar yo'q.

Buning sababi, JavaScript kvadrat qavs oldidan nuqta-vergul qo'ymaydi [...]. Shunday qilib, oxirgi misoldagi kod bitta bayonot sifatida ko'rib chiqiladi.

Dvigatel buni qanday ko'radi:

alert("Hello")[1, 2].forEach(alert);
G'alati ko'rinadi, to'g'rimi? Bu holatda bunday birlashish noto'g'ri. alertKod to'g'ri ishlashi uchun keyin nuqta-vergul qo'yishimiz kerak .

Bu boshqa holatlarda ham sodir bo'lishi mumkin.

Agar ular yangi qatorlar bilan ajratilgan bo'lsa ham, gaplar orasiga nuqta-vergul qo'yishni tavsiya qilamiz. Bu qoida jamiyat tomonidan keng qabul qilingan. Yana bir bor ta'kidlaymiz - ko'pincha nuqta-vergul qo'yish mumkin . Ammo ulardan foydalanish xavfsizroq - ayniqsa yangi boshlanuvchilar uchun.

Izohlar
Vaqt o'tishi bilan dasturlar yanada murakkablashadi. Kod nima qilishini va nima uchun ekanligini tavsiflovchi sharhlarni qo'shish kerak bo'ladi .

Sharhlar skriptning istalgan joyiga qo'yilishi mumkin. Ular uning bajarilishiga ta'sir qilmaydi, chunki dvigatel ularni e'tiborsiz qoldiradi.

Bir qatorli sharhlar ikkita oldinga slash belgisi bilan boshlanadi //.

Qatorning qolgan qismi sharhdir. U o'zining to'liq qatorini egallashi yoki bayonotga amal qilishi mumkin.

Bu yerdagi kabi:

// This comment occupies a line of its own
alert('Hello');

alert('World'); // This comment follows the statement
Ko'p qatorli izohlar to'g'ridan-to'g'ri chiziq va yulduzcha bilan boshlanadi va yulduzcha /*va to'g'ri chiziq bilan tugaydi */.

Shunga o'xshash:

/* An example with two messages.
This is a multiline comment.
*/
alert('Hello');
alert('World');
Sharhlar mazmuni e'tiborga olinmaydi, shuning uchun kodni ichiga qo'ysak /* … */, u bajarilmaydi.

Ba'zan kodning bir qismini vaqtincha o'chirib qo'yish qulay bo'lishi mumkin:

/* Commenting out the code
alert('Hello');
*/
alert('World');
Issiq tugmalardan foydalaning!
Aksariyat muharrirlarda kod satrini bitta satrli sharh uchun qisqa tugmani bosish va ko'p qatorli sharhlar uchun (kod qismini tanlang va tezkor tugmani bosing) kabi narsalarni bosish orqali sharhlash mumkin. Mac uchun va oʻrniga harakat qilib koʻring .Ctrl+/Ctrl+Shift+/CmdCtrlOptionShift

Ichki izohlar qo'llab-quvvatlanmaydi!
/*...*/Ichkarida boshqasi bo'lmasligi mumkin /*...*/.

Bunday kod xato bilan o'ladi:

/*
  /* nested comment ?!? */
*/
alert( 'World' );
Iltimos, kodingizni sharhlashdan tortinmang.

Sharhlar umumiy kod izini oshiradi, lekin bu umuman muammo emas. Ishlab chiqarish serveriga nashr qilishdan oldin kodni kichiklashtiradigan ko'plab vositalar mavjud. Ular sharhlarni olib tashlaydi, shuning uchun ular ishchi skriptlarda ko'rinmaydi. Shuning uchun sharhlar ishlab chiqarishga umuman salbiy ta'sir ko'rsatmaydi.

Keyinchalik o'quv qo'llanmada yaxshiroq sharhlar yozishni tushuntirib beradigan " Kod sifati " bo'limi bo'ladi.