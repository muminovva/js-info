O'zaro ta'sir: ogohlantirish, tezlashtirish, tasdiqlash
Brauzerdan demo muhit sifatida foydalanar ekanmiz, keling, foydalanuvchi bilan ishlash uchun bir nechta funksiyalarni ko‘rib chiqamiz: alert, promptva confirm.

ogohlantirish
Bu biz allaqachon ko'rganmiz. U xabarni ko'rsatadi va foydalanuvchi "OK" tugmasini bosishini kutadi.

Masalan:

alert("Hello");
Xabarga ega mini-oyna modal oyna deb ataladi . "Modal" so'zi tashrif buyuruvchi oyna bilan ishlamaguncha sahifaning qolgan qismi bilan aloqa qila olmasligini, boshqa tugmalarni bosishini va hokazolarni bildiradi. Bu holda - ular "OK" tugmasini bosmaguncha.

taklif
Funktsiya promptikkita argumentni qabul qiladi:

result = prompt(title, [default]);
U matnli xabarga ega modal oynani, tashrif buyuruvchi uchun kiritish maydonini va OK/Bekor qilish tugmalarini ko'rsatadi.

title
Mehmonga ko'rsatish uchun matn.
default
Ixtiyoriy ikkinchi parametr, kiritish maydoni uchun dastlabki qiymat.
Sintaksisdagi kvadrat qavslar[...]
Yuqoridagi sintaksisdagi kvadrat qavslar defaultparametrning ixtiyoriy ekanligini, shart emasligini bildiradi.

Mehmon so'rov kiritish maydoniga biror narsa yozishi va OK tugmasini bosishi mumkin. Keyin biz o'sha matnni olamiz result. Yoki ular Bekor qilish yoki tugmani bosish orqali kiritishni bekor qilishlari mumkin , Esckeyin biz .nullresult

Qo'ng'iroq promptmatnni kiritish maydonidan qaytaradi yoki nullagar kiritish bekor qilingan bo'lsa.

Masalan; misol uchun:

let age = prompt('How old are you?', 100);

alert(`You are ${age} years old!`); // You are 100 years old!
IEda: har doim adefault
Ikkinchi parametr ixtiyoriy, lekin agar biz uni taqdim qilmasak, Internet Explorer matnni taklifga kiritadi "undefined".

Ko'rish uchun ushbu kodni Internet Explorer-da ishga tushiring:

let test = prompt("Test");
Shunday qilib, so'rovlar IEda yaxshi ko'rinishi uchun har doim ikkinchi argumentni taqdim etishni tavsiya qilamiz:

let test = prompt("Test", ''); // <-- for IE
tasdiqlang
Sintaksis:

result = confirm(question);
Funktsiya confirma questionva ikkita tugmachali modal oynani ko'rsatadi: OK va Bekor qilish.

Natija, trueagar OK bosilsa va falseboshqacha bo'lsa.

Masalan:

let isBoss = confirm("Are you the boss?");

alert( isBoss ); // true if OK is pressed
Xulosa
Biz tashrif buyuruvchilar bilan muloqot qilish uchun 3 ta brauzer funksiyasini ko‘rib chiqdik:

alert
xabarni ko'rsatadi.
prompt
foydalanuvchidan matn kiritishni so'ragan xabarni ko'rsatadi. U matnni qaytaradi yoki Bekor qilish tugmasi yoki bosilsa Esc, null.
confirm
xabarni ko'rsatadi va foydalanuvchi "OK" yoki "Bekor qilish" tugmasini bosishini kutadi. trueU OK va falseBekor qilish/ uchun qaytadi Esc.
Bu usullarning barchasi modaldir: ular skriptning bajarilishini to'xtatib turadi va tashrif buyuruvchiga oyna o'chirilmaguncha sahifaning qolgan qismi bilan o'zaro aloqada bo'lishiga ruxsat bermaydi.

Yuqoridagi barcha usullar bilan birgalikda ikkita cheklov mavjud:

Modal oynaning aniq joylashuvi brauzer tomonidan aniqlanadi. Odatda, u markazda joylashgan.
Oynaning aniq ko'rinishi brauzerga ham bog'liq. Biz uni o'zgartira olmaymiz.
Bu oddiylik uchun narx. Chiroyli derazalar va tashrif buyuruvchi bilan yanada boy muloqot qilishning boshqa usullari mavjud, ammo agar "qo'ng'iroq va hushtak" unchalik muhim bo'lmasa, bu usullar juda yaxshi ishlaydi.

Vazifalar
Oddiy sahifa
ahamiyati: 4
Ism so'raydigan va uni chiqaradigan veb-sahifa yarating.

Demoni ishga tushiring