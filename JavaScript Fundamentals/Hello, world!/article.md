Salom Dunyo!
Qo'llanmaning ushbu qismi asosiy JavaScript, tilning o'zi haqida.

Ammo skriptlarimizni ishga tushirish uchun bizga ish muhiti kerak va bu kitob onlayn bo'lgani uchun brauzer yaxshi tanlovdir. alertAgar diqqatingizni boshqa muhitga (masalan, Node.js) qaratmoqchi bo‘lsangiz, ularga vaqt sarflamaslik uchun brauzerga xos buyruqlar miqdorini (masalan, ) minimal darajada ushlab turamiz . Qo'llanmaning keyingi qismida brauzerda JavaScript-ga e'tibor qaratamiz .

Shunday qilib, avval veb-sahifaga skriptni qanday biriktirishimizni ko'rib chiqamiz. Server tomonidagi muhitlar uchun (masalan, Node.js) skriptni kabi buyruq bilan bajarishingiz mumkin "node my.js".

"Skript" yorlig'i
<script>JavaScript dasturlari teg yordamida HTML hujjatining deyarli hamma joyiga kiritilishi mumkin .

Masalan; misol uchun:

<!DOCTYPE HTML>
<html>

<body>

  <p>Before the script...</p>

  <script>
    alert( 'Hello, world!' );
  </script>

  <p>...After the script.</p>

</body>

</html>
Yuqoridagi oynaning o'ng yuqori burchagidagi "Play" tugmasini bosish orqali misolni ishga tushirishingiz mumkin.

Teg <script>JavaScript kodini o'z ichiga oladi, u brauzer tegni qayta ishlaganda avtomatik ravishda bajariladi.

Zamonaviy belgilash
Teg <script>bugungi kunda kamdan-kam qo'llaniladigan bir nechta atributlarga ega, ammo ularni hali ham eski kodda topish mumkin:

Atribut type:<script type=…>
Eski HTML standarti, HTML4, skriptga ega bo'lishi kerak edi type. Odatda shunday edi type="text/javascript". Bu endi talab qilinmaydi. Bundan tashqari, zamonaviy HTML standarti ushbu atributning ma'nosini butunlay o'zgartirdi. Endi u JavaScript modullari uchun ishlatilishi mumkin. Lekin bu ilg‘or mavzu, biz modullar haqida darslikning boshqa qismida gaplashamiz.

Atribut language:<script language=…>
Bu atribut skript tilini ko'rsatish uchun mo'ljallangan edi. Bu atribut endi mantiqiy emas, chunki JavaScript standart tildir. Uni ishlatishning hojati yo'q.

Skriptlardan oldin va keyin sharhlar.
<script>Haqiqatan ham qadimiy kitoblar va qo'llanmalarda siz teglar ichida sharhlarni topishingiz mumkin , masalan:

<script type="text/javascript"><!--
    ...
//--></script>
Ushbu hiyla zamonaviy JavaScript-da qo'llanilmaydi. <script>Ushbu sharhlar JavaScript kodini tegni qanday qayta ishlashni bilmagan eski brauzerlardan yashiradi . So'nggi 15 yil ichida chiqarilgan brauzerlarda bunday muammo bo'lmaganligi sababli, bunday sharh haqiqatan ham eski kodni aniqlashga yordam beradi.

Tashqi skriptlar
Agar bizda juda ko'p JavaScript kodi bo'lsa, uni alohida faylga qo'yishimiz mumkin.

srcSkript fayllari HTML-ga atribut bilan biriktirilgan :

<script src="/path/to/script.js"></script>
Mana, /path/to/script.jssayt ildizidan skriptga mutlaq yo'l. Joriy sahifadan nisbiy yo'lni ham taqdim etish mumkin. Misol uchun, src="script.js"xuddi , kabi , joriy jilddagi src="./script.js"faylni bildiradi ."script.js"

To'liq URL manzilini ham berishimiz mumkin. Masalan; misol uchun:

<script src="https://cdnjs.cloudflare.com/ajax/libs/lodash.js/4.17.11/lodash.js"></script>
Bir nechta skriptlarni biriktirish uchun bir nechta teglardan foydalaning:

<script src="/js/script1.js"></script>
<script src="/js/script2.js"></script>
…
Esda tuting:
Qoidaga ko'ra, HTMLga faqat eng oddiy skriptlar qo'yiladi. Keyinchalik murakkablari alohida fayllarda joylashgan.

Alohida faylning foydasi shundaki, brauzer uni yuklab oladi va keshda saqlaydi .

Xuddi shu skriptga havola qilingan boshqa sahifalar uni yuklab olish o'rniga keshdan oladi, shuning uchun fayl aslida bir marta yuklab olinadi.

Bu trafikni kamaytiradi va sahifalarni tezroq qiladi.

Agar srco'rnatilgan bo'lsa, skript tarkibi e'tiborga olinmaydi.
Bitta tegda atribut ham, kod <script>ham bo‘lishi mumkin emas .src

Bu ishlamaydi:

<script src="file.js">
  alert(1); // the content is ignored, because src is set
</script>
Biz tashqi <script src="…">yoki oddiy <script>kodni tanlashimiz kerak.

Yuqoridagi misolni ishlash uchun ikkita skriptga bo'lish mumkin:

<script src="file.js"></script>
<script>
  alert(1);
</script>
Xulosa
Biz <script>sahifaga JavaScript kodini qo'shish uchun tegdan foydalanishimiz mumkin.
va atributlari shart emas type.language
Tashqi fayldagi skript bilan kiritilishi mumkin <script src="path/to/script.js"></script>.
Brauzer skriptlari va ularning veb-sahifa bilan o'zaro ta'siri haqida ko'proq bilib olish mumkin. Ammo shuni yodda tutaylikki, o'quv qo'llanmaning ushbu qismi JavaScript tiliga bag'ishlangan, shuning uchun biz o'zimizni uning brauzerga xos ilovalari bilan chalg'itmasligimiz kerak. Biz brauzerdan JavaScript-ni ishga tushirish usuli sifatida foydalanamiz, bu onlayn o'qish uchun juda qulay, lekin ko'plaridan faqat bittasi.

Vazifalar
Ogohlantirishni ko'rsatish
ahamiyati: 5
“Men JavaScriptman!” xabarini ko‘rsatadigan sahifa yarating.

Buni sandboxda yoki qattiq diskingizda bajaring, bu muhim emas, shunchaki uning ishlashiga ishonch hosil qiling.

Demo yangi oynada

yechim
Tashqi skript bilan ogohlantirishni ko'rsatish
ahamiyati: 5
Oldingi vazifaning yechimini oling Ogohlantirishni ko'rsatish . alert.jsSkript tarkibini bir xil papkada joylashgan tashqi faylga chiqarish orqali uni o'zgartiring .

Sahifani oching, ogohlantirish ishlayotganiga ishonch hosil qiling.

yechim