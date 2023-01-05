Ma'lumotlar turlari
JavaScript-dagi qiymat har doim ma'lum turdagi bo'ladi. Masalan, qator yoki raqam.

JavaScript-da sakkizta asosiy ma'lumotlar turi mavjud. Bu erda biz ularni umumiy ko'rib chiqamiz va keyingi boblarda ularning har biri haqida batafsil gaplashamiz.

O'zgaruvchiga har qanday turni qo'yishimiz mumkin. Misol uchun, o'zgaruvchi bir vaqtning o'zida satr bo'lishi va keyin raqamni saqlashi mumkin:

// no error
let message = "hello";
message = 123456;
JavaScript kabi bunday narsalarga ruxsat beruvchi dasturlash tillari "dinamik ravishda terilgan" deb nomlanadi, ya'ni ma'lumotlar turlari mavjud, lekin o'zgaruvchilar ularning hech biriga bog'lanmagan.

Raqam
let n = 123;
n = 12.345;
Raqam turi butun va suzuvchi nuqtali sonlarni ifodalaydi .

Raqamlar uchun ko'plab amallar mavjud, masalan, ko'paytirish *, bo'lish /, qo'shish +, ayirish -va hokazo.

Oddiy raqamlardan tashqari, ushbu ma'lumotlar turiga tegishli "maxsus raqamli qiymatlar" ham mavjud: Infinity, -Infinityva NaN.

Infinitymatematik Infinity ∞ ni ifodalaydi. Bu har qanday raqamdan kattaroq bo'lgan maxsus qiymat.

Biz uni nolga bo'lish natijasida olishimiz mumkin:

alert( 1 / 0 ); // Infinity
Yoki unga to'g'ridan-to'g'ri murojaat qiling:

alert( Infinity ); // Infinity
NaNhisoblash xatosini ifodalaydi. Bu noto'g'ri yoki aniqlanmagan matematik operatsiya natijasidir, masalan:

alert( "not a number" / 2 ); // NaN, such division is erroneous
NaNyopishqoq. Qaytish bo'yicha har qanday keyingi matematik NaNoperatsiya NaN:

alert( NaN + 1 ); // NaN
alert( 3 * NaN ); // NaN
alert( "not a number" / 2 - 1 ); // NaN
Shunday qilib, agar NaNmatematik ifodaning biror joyi bo'lsa, u butun natijaga tarqaladi (bundan faqat bitta istisno bor: NaN ** 0is 1).

Matematik operatsiyalar xavfsizdir
JavaScript-da matematika bilan shug'ullanish "xavfsiz". Biz hamma narsani qila olamiz: nolga bo'lish, raqamli bo'lmagan satrlarni raqamlar sifatida ko'rib chiqish va hokazo.

Skript hech qachon halokatli xato ("o'lish") bilan to'xtamaydi. Eng yomoni, biz NaNnatijaga erishamiz.

Maxsus raqamli qiymatlar rasmiy ravishda "raqam" turiga tegishli. Albatta, ular bu so'zning umumiy ma'nosida raqamlar emas.

Raqamlar bilan ishlash haqida ko'proq " Raqamlar " bo'limida ko'rib chiqamiz .

BigInt
JavaScript-da “raqam” turi manfiylardan kattaroq (bu ) yoki undan kichik butun son qiymatlarini ishonchli tarzda ifodalay olmaydi .(253-1)9007199254740991-(253-1)

Aniqroq qilib aytadigan bo'lsak, "raqam" turi kattaroq butun sonlarni (-gacha ) saqlashi mumkin, ammo xavfsiz tamsayı diapazonidan tashqarida aniqlik xatosi bo'ladi, chunki barcha raqamlar qattiq 64 bitli xotiraga mos kelmaydi. Shunday qilib, "taxminan" qiymat saqlanishi mumkin.1.7976931348623157 * 10308±(253-1)

Masalan, bu ikki raqam (xavfsiz diapazondan yuqori) bir xil:

console.log(9007199254740991 + 1); // 9007199254740992
console.log(9007199254740991 + 2); // 9007199254740992
Demak, barcha toq sonlarni “raqam” turida saqlash mumkin emas.(253-1)

Ko'pgina maqsadlar uchun diapazon juda etarli, lekin ba'zida bizga haqiqatan ham katta butun sonlarning butun diapazoni kerak bo'ladi, masalan, kriptografiya yoki mikrosoniyali aniqlikdagi vaqt belgilari.±(253-1)

BigInttype ixtiyoriy uzunlikdagi butun sonlarni ifodalash uchun tilga yaqinda qo‘shildi.

Qiymat butun sonning oxiriga qo'shilishi bilan BigIntyaratiladi :n

// the "n" at the end means it's a BigInt
const bigInt = 1234567890123456789012345678901234567890n;
BigIntRaqamlar kamdan-kam hollarda kerak bo'lganligi sababli , biz ularni bu erda ko'rib chiqmaymiz, lekin ularga BigInt ning alohida bobini bag'ishladik . Bunday katta raqamlar kerak bo'lganda uni o'qing.

Muvofiqlik muammolari
Hozirda BigIntFirefox/Chrome/Edge/Safari-da qo'llab-quvvatlanadi, lekin IE-da emas.

Brauzerning qaysi versiyalari qo'llab-quvvatlanishini bilish uchun MDN BigInt muvofiqlik jadvalini tekshirishingiz mumkin .

String
JavaScript-dagi satr tirnoqlar bilan o'ralgan bo'lishi kerak.

let str = "Hello";
let str2 = 'Single quotes are ok too';
let phrase = `can embed another ${str}`;
JavaScript-da tirnoqlarning 3 turi mavjud.

Ikkita tirnoq: "Hello".
Yagona tirnoq: 'Hello'.
Orqa tizmalar: `Hello`.
Ikki va bitta tirnoq "oddiy" tirnoqdir. JavaScript-da ular o'rtasida deyarli farq yo'q.

Backticks - bu "kengaytirilgan funksionallik" tirnoqlari. Ular bizga o'zgaruvchilar va ifodalarni qatorga o'rash orqali kiritish imkonini beradi ${…}, masalan:

let name = "John";

// embed a variable
alert( `Hello, ${name}!` ); // Hello, John!

// embed an expression
alert( `the result is ${1 + 2}` ); // the result is 3
Ichidagi ifoda ${…}baholanadi va natija satrning bir qismiga aylanadi. Biz u erda hamma narsani qo'yishimiz mumkin: o'xshash o'zgaruvchi nameyoki arifmetik ifoda kabi 1 + 2yoki murakkabroq narsa.

Shuni esda tutingki, bu faqat teskari belgilarda amalga oshirilishi mumkin. Boshqa tirnoqlarda bu joylashtirish funksiyasi yo'q!

alert( "the result is ${1 + 2}" ); // the result is ${1 + 2} (double quotes do nothing)
Biz satrlarni Stringlar bobida batafsil yoritamiz .

Belgilar turi yo'q .
Ba'zi tillarda bitta belgi uchun maxsus "belgi" turi mavjud. Masalan, C tilida va Java-da u "char" deb ataladi.

JavaScript-da bunday tur mavjud emas. Faqat bitta turi bor: string. Satr nol belgilardan (bo'sh bo'lishi), bitta belgidan yoki ularning ko'plaridan iborat bo'lishi mumkin.

Mantiqiy (mantiqiy tur)
Boolean turi faqat ikkita qiymatga ega: trueva false.

Ushbu tur odatda ha/yo'q qiymatlarini saqlash uchun ishlatiladi: true"ha, to'g'ri" va false"yo'q, noto'g'ri" degan ma'noni anglatadi.

Masalan; misol uchun:

let nameFieldChecked = true; // yes, name field is checked
let ageFieldChecked = false; // no, age field is not checked
Mantiqiy qiymatlar ham taqqoslash natijasida kelib chiqadi:

let isGreater = 4 > 1;

alert( isGreater ); // true (the comparison result is "yes")
Biz mantiqiy operatorlar bobida mantiqiy qiymatlarni chuqurroq yoritamiz .

"Nul" qiymati
Maxsus nullqiymat yuqorida tavsiflangan turlarning hech biriga tegishli emas.

U o'zining alohida turini hosil qiladi, unda faqat nullqiymat mavjud:

let age = null;
JavaScript null-da ba'zi boshqa tillardagi kabi "mavjud bo'lmagan ob'ektga havola" yoki "null ko'rsatgich" emas.

Bu shunchaki "hech narsa", "bo'sh" yoki "qiymat noma'lum" ni ifodalovchi maxsus qiymat.

Yuqoridagi kod agenoma'lumligini bildiradi.

"Aniqlanmagan" qiymat
Maxsus qiymat undefinedham alohida turadi. Xuddi ga o'xshab o'ziga xos tur yaratadi null.

Ma'nosi undefined"qiymat belgilanmagan".

Agar o'zgaruvchi e'lon qilingan, lekin tayinlanmagan bo'lsa, uning qiymati quyidagicha bo'ladi undefined:

let age;

alert(age); // shows "undefined"
undefinedTexnik jihatdan, o'zgaruvchiga aniq belgilash mumkin :

let age = 100;

// change the value to undefined
age = undefined;

alert(age); // "undefined"
…Ammo buni qilishni tavsiya etmaymiz. Odatda, nullo'zgaruvchiga "bo'sh" yoki "noma'lum" qiymat belgilash uchun foydalaniladi, bu esa undefinedtayinlanmagan narsalar uchun standart boshlang'ich qiymat sifatida saqlanadi.

Ob'ektlar va belgilar
Turi objectalohida.

Boshqa barcha turlar "ibtidoiy" deb ataladi, chunki ularning qiymatlari faqat bitta narsani o'z ichiga olishi mumkin (u qator yoki raqam yoki boshqa narsa). Bundan farqli o'laroq, ob'ektlar ma'lumotlar to'plamini va murakkabroq ob'ektlarni saqlash uchun ishlatiladi.

Shu qadar muhim bo'lgan ob'ektlar alohida muomalaga loyiqdir. Biz ibtidoiy narsalar haqida ko'proq bilib olganimizdan so'ng, ular bilan keyinroq Ob'ektlar bo'limida ko'rib chiqamiz.

Turi symbolob'ektlar uchun noyob identifikatorlarni yaratish uchun ishlatiladi. To'liqlik uchun biz bu erda eslatib o'tishimiz kerak, lekin biz narsalarni bilib olguncha tafsilotlarni kechiktirishimiz kerak.

Operator turi
Operator typeofoperand turini qaytaradi. Biz har xil turdagi qiymatlarni boshqacha qayta ishlashni yoki shunchaki tezkor tekshirishni xohlayotganimizda foydalidir.

Qo'ng'iroq typeof xturi nomi bilan qatorni qaytaradi:

typeof undefined // "undefined"

typeof 0 // "number"

typeof 10n // "bigint"

typeof true // "boolean"

typeof "foo" // "string"

typeof Symbol("id") // "symbol"

typeof Math // "object"  (1)

typeof null // "object"  (2)

typeof alert // "function"  (3)
Oxirgi uchta satr qo'shimcha tushuntirishga muhtoj bo'lishi mumkin:

Mathmatematik amallarni ta'minlovchi o'rnatilgan ob'ektdir. Biz buni Raqamlar bobida bilib olamiz . Bu erda u ob'ektga misol sifatida xizmat qiladi.
typeof nullning natijasidir "object". typeofBu JavaScript-ning dastlabki kunlaridan kelib chiqqan va muvofiqlik uchun saqlangan rasman tan olingan xato . Albatta, nullob'ekt emas. Bu o'zining alohida turiga ega bo'lgan maxsus qiymatdir. Bu erda xatti-harakati typeofnoto'g'ri.
ning natijasi typeof alert, "function"chunki alertfunksiyadir. Biz keyingi boblarda funksiyalarni o‘rganamiz, unda JavaScript-da maxsus “funksiya” turi yo‘qligini ham ko‘ramiz. Funktsiyalar ob'ekt turiga tegishli. Lekin typeofularga boshqacha munosabatda bo'ladi, qaytib keladi "function". Bu ham JavaScript-ning dastlabki kunlaridan kelib chiqadi. Texnik jihatdan bunday xatti-harakatlar to'g'ri emas, lekin amalda qulay bo'lishi mumkin.
typeof(x)Sintaksis _
Siz boshqa sintaksisga ham duch kelishingiz mumkin: typeof(x). bilan bir xil typeof x.

Aniqroq qilib aytganda: typeofbu funksiya emas, operator. Bu yerdagi qavslar ning bir qismi emas typeof. Bu matematik guruhlash uchun ishlatiladigan qavslar turi.

Odatda, bunday qavslar matematik ifodani o'z ichiga oladi, masalan, (2 + 2), lekin bu erda ular faqat bitta argumentni o'z ichiga oladi (x). Sintaktik jihatdan ular operator va uning argumenti o'rtasidagi bo'shliqdan qochishga imkon beradi typeofva ba'zilarga buni yoqtiradi.

Ba'zi odamlar ni afzal ko'rishadi typeof(x), garchi typeof xsintaksis ancha keng tarqalgan.

Xulosa
JavaScript-da 8 ta asosiy ma'lumotlar turi mavjud.

Etti ibtidoiy ma'lumotlar turi:
numberhar qanday turdagi raqamlar uchun: butun yoki suzuvchi nuqta, butun sonlar bilan cheklangan .±(253-1)
bigintixtiyoriy uzunlikdagi butun sonlar uchun.
stringiplar uchun. Satrda nol yoki undan ortiq belgilar bo'lishi mumkin, alohida bitta belgi turi mavjud emas.
booleanuchun true/ false.
nullnoma'lum qiymatlar uchun - bitta qiymatga ega bo'lgan mustaqil tur null.
undefinedtayinlanmagan qiymatlar uchun - bitta qiymatga ega bo'lgan mustaqil tur undefined.
symbolnoyob identifikatorlar uchun.
Va bitta oddiy bo'lmagan ma'lumotlar turi:
objectmurakkabroq ma'lumotlar tuzilmalari uchun.
Operator typeofbizga o'zgaruvchida qaysi tur saqlanganligini ko'rish imkonini beradi.

Odatda sifatida ishlatiladi typeof x, lekin typeof(x)bu ham mumkin.
Tur nomi bilan qatorni qaytaradi, masalan "string".
nullQaytish uchun "object"- bu tildagi xato, bu aslida ob'ekt emas.
Keyingi boblarda biz ibtidoiy qadriyatlarga e'tibor qaratamiz va ular bilan tanishganimizdan so'ng, biz ob'ektlarga o'tamiz.

Vazifalar
String tirnoqlari
ahamiyati: 5
Skriptning chiqishi nima?

let name = "Ilya";

alert( `hello ${1}` ); // ?

alert( `hello ${"name"}` ); // ?

alert( `hello ${name}` ); // ?