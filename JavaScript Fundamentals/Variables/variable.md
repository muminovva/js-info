O'zgaruvchilar
Ko'pincha JavaScript ilovasi ma'lumot bilan ishlashi kerak. Mana ikkita misol:

Onlayn do'kon - ma'lumotlar sotilayotgan tovarlar va xarid qilish savatini o'z ichiga olishi mumkin.
Chat ilovasi - ma'lumotlar foydalanuvchilar, xabarlar va boshqalarni o'z ichiga olishi mumkin.
Ushbu ma'lumotlarni saqlash uchun o'zgaruvchilar ishlatiladi.

Oʻzgaruvchi
O'zgaruvchi ma'lumotlar uchun "nomli xotira" dir . Biz o'zgaruvchilardan shirinliklar, tashrif buyuruvchilar va boshqa ma'lumotlarni saqlash uchun foydalanishimiz mumkin.

JavaScript-da o'zgaruvchi yaratish uchun letkalit so'zdan foydalaning.

Quyidagi bayonot “xabar” nomli o‘zgaruvchini yaratadi (boshqacha aytganda: e’lon qiladi ):

let message;
Endi biz tayinlash operatoridan foydalanib, unga ba'zi ma'lumotlarni kiritishimiz mumkin =:

let message;

message = 'Hello'; // store the string 'Hello' in the variable named message
Endi satr o'zgaruvchi bilan bog'langan xotira maydoniga saqlanadi. Biz unga o'zgaruvchi nomi yordamida kirishimiz mumkin:

let message;
message = 'Hello!';

alert(message); // shows the variable content
Qisqacha aytganda, biz o'zgaruvchan deklaratsiyani va tayinlashni bitta qatorga birlashtira olamiz:

let message = 'Hello!'; // define the variable and assign the value

alert(message); // Hello!
Shuningdek, biz bir qatorda bir nechta o'zgaruvchilarni e'lon qilishimiz mumkin:

let user = 'John', age = 25, message = 'Hello';
Bu qisqaroq tuyulishi mumkin, lekin biz buni tavsiya etmaymiz. Yaxshiroq o'qilishi uchun har bir o'zgaruvchiga bitta qatordan foydalaning.

Ko'p qatorli variant biroz uzunroq, ammo o'qish osonroq:

let user = 'John';
let age = 25;
let message = 'Hello';
Ba'zi odamlar ushbu ko'p qatorli uslubda bir nechta o'zgaruvchilarni ham belgilaydilar:

let user = 'John',
  age = 25,
  message = 'Hello';
…Yoki “birinchi vergul” uslubida ham:

let user = 'John'
  , age = 25
  , message = 'Hello';
Texnik jihatdan, bu variantlarning barchasi bir xil ishni bajaradi. Demak, bu shaxsiy did va estetika masalasi.

varo'rnigalet
Eski skriptlarda siz boshqa kalit so'zni ham topishingiz mumkin: varo'rniga let:

var message = 'Hello';
varKalit so'z deyarlilet bir xil . Shuningdek, u o'zgaruvchini e'lon qiladi, lekin biroz boshqacha, "eski maktab" usulida.

letva o'rtasida nozik farqlar mavjud var, ammo ular biz uchun hali muhim emas. Biz ularni eski "var" bobida batafsil ko'rib chiqamiz .

Haqiqiy hayotdagi o'xshashlik
Agar biz uni ma'lumotlar uchun "quti" sifatida tasavvur qilsak, "o'zgaruvchi" tushunchasini osongina tushunishimiz mumkin, unda noyob nomli stiker.

Masalan, o'zgaruvchini undagi qiymat bilan messagebelgilangan quti sifatida tasavvur qilish mumkin :"message""Hello!"


Biz qutiga istalgan qiymatni qo'yishimiz mumkin.

Shuningdek, biz uni xohlagancha o'zgartirishimiz mumkin:

let message;

message = 'Hello!';

message = 'World!'; // value changed

alert(message);
Qiymat o'zgartirilganda, eski ma'lumotlar o'zgaruvchidan o'chiriladi:


Shuningdek, biz ikkita o'zgaruvchini e'lon qilishimiz va ma'lumotlarni biridan ikkinchisiga nusxalashimiz mumkin.

let hello = 'Hello world!';

let message;

// copy 'Hello world' from hello into message
message = hello;

// now two variables hold the same data
alert(hello); // Hello world!
alert(message); // Hello world!
Ikki marta e'lon qilish xatolikni keltirib chiqaradi
O'zgaruvchi faqat bir marta e'lon qilinishi kerak.

Xuddi shu o'zgaruvchining takroriy deklaratsiyasi xato hisoblanadi:

let message = "This";

// repeated 'let' leads to an error
let message = "That"; // SyntaxError: 'message' has already been declared
Shunday qilib, biz o'zgaruvchini bir marta e'lon qilishimiz va keyin unga holda murojaat qilishimiz kerak let.

Funktsional tillar
Shunisi qiziqki, o'zgaruvchan qiymatlarni o'zgartirishni taqiqlovchi Haskell kabi sof funktsional dasturlash tillari mavjud.

Bunday tillarda qiymat “qutida” saqlanganidan keyin u abadiy qoladi. Agar boshqa biror narsani saqlashimiz kerak bo'lsa, til bizni yangi quti yaratishga majbur qiladi (yangi o'zgaruvchini e'lon qilish). Biz eskisini qayta ishlata olmaymiz.

Bir qarashda g'alati tuyulishi mumkin bo'lsa-da, bu tillar jiddiy rivojlanishga qodir. Bundan tashqari, parallel hisoblash kabi sohalar mavjud bo'lib, bu cheklash ma'lum afzalliklarni beradi.

O'zgaruvchilarni nomlash
JavaScript-da o'zgaruvchilar nomlarida ikkita cheklov mavjud:

Ism faqat harflar, raqamlar yoki belgilarni o'z ichiga olishi $kerak _.
Birinchi belgi raqam bo'lmasligi kerak.
To'g'ri nomlarga misollar:

let userName;
let test123;
Agar nomda bir nechta so'z bo'lsa, camelCase odatda ishlatiladi. Ya'ni: so'zlar birin-ketin boradi, har bir so'z birinchi bosh harf bilan boshlanadi: myVeryLongName.

Qizig'i shundaki, ismlarda dollar belgisi '$'va pastki chiziq '_'ham ishlatilishi mumkin. Ular har qanday maxsus ma'noga ega bo'lmagan harflar kabi muntazam belgilardir.

Bu nomlar amal qiladi:

let $ = 1; // declared a variable with the name "$"
let _ = 2; // and now a variable with the name "_"

alert($ + _); // 3
Noto'g'ri o'zgaruvchilar nomlariga misollar:

let 1a; // cannot start with a digit

let my-name; // hyphens '-' aren't allowed in the name
Vaziyat muhim
O'zgaruvchilar nomli appleva APPLEikki xil o'zgaruvchilardir.

Lotin bo'lmagan harflarga ruxsat beriladi, lekin tavsiya etilmaydi
Har qanday tildan foydalanish mumkin, jumladan kirill harflari, xitoy logogrammalari va boshqalar:

let имя = '...';
let 我 = '...';
Texnik jihatdan, bu erda hech qanday xatolik yo'q. Bunday nomlarga ruxsat beriladi, ammo o'zgaruvchan nomlarda ingliz tilidan foydalanish bo'yicha xalqaro konventsiya mavjud. Kichik stsenariy yozayotgan bo'lsak ham, uni uzoq umr ko'rishi mumkin. Boshqa mamlakatlardagi odamlar uni biroz vaqt o'qishlari kerak bo'lishi mumkin.

Zaxiralangan nomlar
Zaxiralangan so'zlar ro'yxati mavjud bo'lib , ularni o'zgaruvchan nom sifatida ishlatib bo'lmaydi, chunki ular tilning o'zi tomonidan qo'llaniladi.

Masalan: let, class, return, va functionajratilgan.

Quyidagi kod sintaksis xatosini beradi:

let let = 5; // can't name a variable "let", error!
let return = 5; // also can't name it "return", error!
Topshiriqsizuse strict
Odatda, biz uni ishlatishdan oldin o'zgaruvchini aniqlashimiz kerak. Ammo qadimgi davrlarda dan foydalanmasdan faqat qiymatni belgilash orqali o'zgaruvchini yaratish texnik jihatdan mumkin edi let. Agar biz use stricteski skriptlar bilan moslikni saqlab qolish uchun skriptlarimizni kiritmasak, bu hozir ham ishlaydi.

// note: no "use strict" in this example

num = 5; // the variable "num" is created if it didn't exist

alert(num); // 5
Bu yomon amaliyot va qattiq rejimda xatolikka olib keladi:

"use strict";

num = 5; // error: num is not defined
Konstantalar
Doimiy (o'zgarmas) o'zgaruvchini e'lon qilish uchun consto'rniga foydalaning let:

const myBirthday = '18.04.1982';
Foydalanish orqali e'lon qilingan o'zgaruvchilar const"doimiy" deb ataladi. Ularni qayta tayinlash mumkin emas. Bunga urinish xatoga olib keladi:

const myBirthday = '18.04.1982';

myBirthday = '01.01.2001'; // error, can't reassign the constant!
Agar dasturchi o'zgaruvchi hech qachon o'zgarmasligiga amin bo'lsa, uni constkafolatlash va bu faktni hammaga aniq etkazish uchun e'lon qilishi mumkin.

Katta harf konstantalari
Amalga oshirishdan oldin ma'lum bo'lgan eslab qolish qiyin bo'lgan qiymatlar uchun konstantalarni taxallus sifatida ishlatish keng tarqalgan.

Bunday doimiylar bosh harflar va pastki chiziq yordamida nomlanadi.

Misol uchun, keling, ranglar uchun "veb" (o'n oltilik) formatda konstantalar yarataylik:

const COLOR_RED = "#F00";
const COLOR_GREEN = "#0F0";
const COLOR_BLUE = "#00F";
const COLOR_ORANGE = "#FF7F00";

// ...when we need to pick a color
let color = COLOR_ORANGE;
alert(color); // #FF7F00
Foydasi:

COLOR_ORANGEga qaraganda eslash ancha oson "#FF7F00".
"#FF7F00"ga qaraganda xato yozish ancha oson COLOR_ORANGE.
Kodni o'qiyotganda, COLOR_ORANGEga qaraganda ancha mazmunli #FF7F00.
Qachon doimiy uchun bosh harflardan foydalanishimiz kerak va qachon uni normal nomlashimiz kerak? Keling, buni aniq qilib olaylik.

"Doimiy" bo'lish shunchaki o'zgaruvchining qiymati hech qachon o'zgarmasligini anglatadi. Lekin shunday konstantalar bajarilgunga qadar ma'lum bo'ladi (masalan, qizil rang uchun o'n oltilik qiymat) va shunday konstantalar borki, ular bajarilish vaqtida, bajarilish vaqtida hisoblab chiqiladi , lekin dastlabki tayinlanganidan keyin o'zgarmaydi.

Masalan; misol uchun:

const pageLoadTime = /* time taken by a webpage to load */;
ning qiymati pageLoadTimesahifa yuklanishidan oldin noma'lum, shuning uchun u odatdagidek nomlanadi. Ammo bu hali ham doimiy, chunki u topshiriqdan keyin o'zgarmaydi.

Boshqacha qilib aytganda, katta harflar bilan atalgan konstantalar faqat “qattiq kodlangan” qiymatlar uchun taxallus sifatida ishlatiladi.

Narsalarni to'g'ri nomlang
O'zgaruvchilar haqida gapiradigan bo'lsak, yana bir juda muhim narsa bor.

O'zgaruvchining nomi u saqlaydigan ma'lumotlarni tavsiflovchi toza, aniq ma'noga ega bo'lishi kerak.

O'zgaruvchilarni nomlash dasturlashning eng muhim va murakkab ko'nikmalaridan biridir. O'zgaruvchilar nomlariga tezkor qarash qaysi kodni tajribali dasturchiga nisbatan yangi boshlovchi tomonidan yozilganligini aniqlashi mumkin.

Haqiqiy loyihada ko'p vaqt noldan butunlay alohida biror narsa yozishdan ko'ra mavjud kod bazasini o'zgartirish va kengaytirishga sarflanadi. Bir muncha vaqt boshqa biror narsa qilganimizdan so'ng, kodga qaytsak, yaxshi etiketlangan ma'lumotlarni topish ancha oson bo'ladi. Yoki, boshqacha qilib aytganda, o'zgaruvchilar yaxshi nomga ega bo'lganda.

Iltimos, o'zgaruvchini e'lon qilishdan oldin uning to'g'ri nomi haqida o'ylab ko'ring. Agar shunday qilsangiz, sizga yaxshi to'lanadi.

Ba'zi yaxshi qoidalarga rioya qilish kerak:

userNameyoki kabi odam oʻqiy oladigan nomlardan foydalaning shoppingCart.
a, b, kabi qisqartmalar yoki qisqa nomlardan uzoqroq turing c, agar nima qilayotganingizni bilmasangiz.
Ismlarni maksimal darajada tavsiflovchi va qisqacha qiling. Yomon nomlarga misollar datava value. Bunday nomlar hech narsa demaydi. Agar kod konteksti o'zgaruvchi qaysi ma'lumotlar yoki qiymatga havola qilinayotganini juda aniq ko'rsatsa, ulardan foydalanish mumkin.
Jamoangiz ichida va o'zingizning fikringizcha shartlarga rozi bo'ling. Agar saytga tashrif buyuruvchi "foydalanuvchi" deb atalsa, biz yoki o'rniga tegishli o'zgaruvchilarni yoki nomlashimiz currentUserkerak .newUsercurrentVisitornewManInTown
Oddiy tuyuladimi? Haqiqatan ham shunday, lekin tavsiflovchi va qisqacha o'zgaruvchilar nomlarini yaratish amalda bunday emas. Olg'a.

Qayta ishlatilsinmi yoki yaratilsinmi?
Va oxirgi eslatma. Ba'zi dangasa dasturchilar borki, ular yangi o'zgaruvchilarni e'lon qilish o'rniga, mavjudlarini qayta ishlatishga moyildirlar.

Natijada, ularning o'zgaruvchilari odamlar stikerlarini o'zgartirmasdan turli narsalarni tashlaydigan qutilarga o'xshaydi. Endi qutining ichida nima bor? Kim biladi? Biz yaqinlashib, tekshirishimiz kerak.

Bunday dasturchilar o'zgaruvchan deklaratsiyada biroz tejashadi, lekin disk raskadrovkada o'n barobar ko'proq yo'qotishadi.

Qo'shimcha o'zgaruvchi yomon emas, yaxshi.

Zamonaviy JavaScript minifikatorlari va brauzerlari kodni etarlicha optimallashtiradi, shuning uchun u ishlash bilan bog'liq muammolarni keltirib chiqarmaydi. Turli xil qiymatlar uchun turli xil o'zgaruvchilardan foydalanish hatto dvigatelga kodingizni optimallashtirishga yordam beradi.

Xulosa
varBiz , let, yoki constkalit so'zlar yordamida ma'lumotlarni saqlash uchun o'zgaruvchilarni e'lon qilishimiz mumkin .

let- zamonaviy o'zgaruvchilar deklaratsiyasi.
var- eski maktab o'zgaruvchan deklaratsiyasi. Odatda biz uni umuman ishlatmaymiz, lekin eski "var"let bobidagi nozik farqlarni sizga kerak bo'lganda ko'rib chiqamiz.
const– ga o‘xshaydi let, lekin o‘zgaruvchining qiymatini o‘zgartirib bo‘lmaydi.
O'zgaruvchilar ularning ichida nima borligini osongina tushunishimizga imkon beradigan tarzda nomlanishi kerak.

Vazifalar
O'zgaruvchilar bilan ishlash
ahamiyati: 2
Ikkita o'zgaruvchini e'lon qiling: adminva name.
Qiymatni "John"ga belgilang name.
nameQiymatni dan ga nusxalash admin.
Foydalanish qiymatini ko'rsating admin( alert"Jon" chiqishi kerak).
yechim
To'g'ri nom berish
ahamiyati: 3
Sayyoramiz nomi bilan o'zgaruvchi yarating. Bunday o'zgaruvchini qanday nomlagan bo'lardingiz?
Veb-saytga joriy tashrif buyuruvchining ismini saqlash uchun o'zgaruvchi yarating. Bu o'zgaruvchini qanday nomlagan bo'lardingiz?
yechim
Katta harf const?
ahamiyati: 4
Quyidagi kodni ko'rib chiqing:

const birthday = '18.04.1982';

const age = someCode(birthday);
Bu erda bizda birthdaysana uchun doimiy, shuningdek, agedoimiy.

agedan birthdayfoydalanish orqali hisoblanadi , someCode()ya'ni biz hali tushuntirmagan funksiya chaqiruvini bildiradi (tez orada aytamiz!), lekin bu erda tafsilotlar muhim emas, gap shundaki, ageu qandaydir tarzda birthday.

uchun bosh harfdan foydalanish to'g'ri birthdaybo'ladimi? uchun age? Yoki ikkalasi uchunmi?

const BIRTHDAY = '18.04.1982'; // make birthday uppercase?

const AGE = someCode(BIRTHDAY); // make age uppercase?