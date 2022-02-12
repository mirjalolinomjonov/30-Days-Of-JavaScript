<div align="center">
  <h1> JavaScript-ning 30 kuni: Web Storages(xotira)</h1>
  <a class="header-badge" target="_blank" href="https://www.linkedin.com/in/asabeneh/">
  <img src="https://img.shields.io/badge/style--5eba00.svg?label=LinkedIn&logo=linkedin&style=social">
  </a>


<sub>Author:
<a href="https://www.linkedin.com/in/asabeneh/" target="_blank">Asabeneh Yetayeh</a><br>
<small> January, 2022</small>
</sub>

</div>

[<< 16-kun](../16_Day_JSON/16_day_json.md) | [18-kun >>](../18_Day_Promises/18_day_promises.md)

![Thirty Days Of JavaScript](../images/banners/day_1_17.png)

- [17-Kun](#17-kun)
  - [HTML5 Web Storage](#html5-web-storage)
    - [sessionStorage](#sessionstorage)
    - [localStorage](#localstorage)
    - [Veb-xotiralardan foydalanish holati](#veb-xotiralardan-foydalanish-holati)
  - [HTML5 veb-xotira ob'ektlari](#html5-veb-xotira-obektlari)
    - [Elementni localStorage-ga sozlash](#elementni-localstorage-ga-sozlash)
    - [LocalStorage dan element olish](#localstorage-dan-element-olish)
    - [LokalStorage ni tozalash](#lokalstorage-ni-tozalash)
  - [Mashqlar](#mashqlar)
    - [Mashqlar: Level 1](#mashqlar-level-1)
    - [Mashqlar: Level 2](#mashqlar-level-2)
    - [Mashqlar: Level 3](#mashqlar-level-3)

# 17-Kun

## HTML5 Web Storage

Web Storage (sessionStorage va localStorage) yangi HTML5 API boʻlib, anʼanaviy cookie-fayllarga nisbatan muhim afzalliklarni taqdim etadi. HTML5 dan oldin dastur ma'lumotlari har bir server so'roviga kiritilgan cookie fayllarida saqlanishi kerak edi. Veb-saqlash yanada xavfsizroq va katta hajmdagi ma'lumotlar veb-sayt ishlashiga ta'sir qilmasdan mahalliy sifatida saqlanishi mumkin. Ko'pgina veb-brauzerlarda cookie-fayllarni saqlash chegarasi har bir cookie fayli uchun taxminan 4 KB ni tashkil qiladi. Biz saqlash joylari ancha kattaroq ma'lumotlarni (kamida 5 MB) saqlashi mumkin va hech qachon serverga o'tkazilmaydi. Bitta yoki bir kelib chiqishi barcha saytlar bir xil ma'lumotlarni saqlashi va ularga kirishi mumkin.

Saqlanayotgan ma'lumotlarga JavaScript yordamida kirish mumkin, bu sizga an'anaviy ravishda server tomonida dasturlash va relyatsion ma'lumotlar bazalarini o'z ichiga olgan ko'p narsalarni qilish uchun mijoz tomoni skriptlaridan foydalanish imkoniyatini beradi. Ikkita Web Storage obyekti mavjud:

- sessionStorage
- localStorage

localStorage sessionStorage-ga o'xshaydi, bundan tashqari localStorage-da saqlangan ma'lumotlarning amal qilish muddati bo'lmasa-da, sessionStorage-da saqlangan ma'lumotlar sahifa sessiyasi tugaganda, ya'ni sahifa yopilganda tozalanadi.

Shuni ta'kidlash kerakki, localStorage yoki sessionStorage-da saqlangan ma'lumotlar sahifaning protokoliga xosdir.

Kalitlar va qiymatlar har doim satrlardir (esda tutingki, ob'ektlarda bo'lgani kabi, butun sonli kalitlar avtomatik ravishda satrlarga aylantiriladi).

![web_storage](../images/web_storage.png)

### sessionStorage

sessionStorage faqat brauzer yorlig'i yoki oyna sessiyasida mavjud. U bitta veb-sahifa seansida ma'lumotlarni saqlash uchun mo'ljallangan. Ya'ni, agar oyna yopilsa, sessiya ma'lumotlari o'chiriladi. SessionStorage va localStorage shunga o'xshash usullarga ega bo'lgani uchun biz faqat localStorage-ga e'tibor qaratamiz.

### localStorage

HTML5 localStorage - bu veb-xotira API-ning paragrafi bo'lib, u brauzerda amal qilish muddati tugamaydigan ma'lumotlarni saqlash uchun ishlatiladi. Ma'lumotlar brauzer yopilgandan keyin ham brauzerda mavjud bo'ladi. localStorage brauzer seanslari orasida ham saqlanadi. Bu shuni anglatadiki, ma'lumotlar brauzer yopilganda va qayta ochilganda, shuningdek, yorliqlar va oynalar o'rtasida darhol mavjud bo'ladi.

Veb saqlash ma'lumotlari, har ikkala holatda ham, turli brauzerlar o'rtasida mavjud emas. Masalan, Firefox-da yaratilgan saqlash ob'ektlariga xuddi cookie fayllari kabi Internet Explorer-da kirish mumkin emas. Mahalliy xotirada ishlashning beshta usuli mavjud:
_setItem(), getItem(), removeItem(), clear(), key()_

### Veb-xotiralardan foydalanish holati

Veb-xotiralardan foydalanishning ba'zi holatlari

- ma'lumotlarni vaqtincha saqlash
- foydalanuvchi xarid qilish savatiga joylashtirgan mahsulotlarni saqlash
- ma'lumotlar sahifa so'rovlari, bir nechta brauzer yorliqlari, shuningdek, localStorage yordamida brauzer seanslari o'rtasida mavjud bo'lishi mumkin
- localStorage yordamida butunlay oflayn rejimda foydalanish mumkin
- Keyinchalik so'rovlar sonini kamaytirish uchun mijozda ba'zi statik ma'lumotlar saqlanganida veb-xotira ajoyib ishlash yutug'i bo'lishi mumkin. Base64 kodlash yordamida hatto tasvirlar ham satrlarda saqlanishi mumkin.
- foydalanuvchi autentifikatsiya usuli uchun foydalanish mumkin

Yuqorida keltirilgan misollar uchun localStorage-dan foydalanish mantiqan to'g'ri keladi. O'shanda biz sessionStorage-dan qachon foydalanishimiz kerak, deb hayron bo'lishingiz mumkin.

Bunday hollarda, oyna yopilishi bilanoq biz ma'lumotlardan xalos bo'lishni xohlaymiz. Yoki, ehtimol, agar dastur boshqa oynada ochilgan bir xil dasturga xalaqit berishini xohlamasak. Ushbu stsenariylar eng yaxshi sessionStorage bilan xizmat qiladi.

Keling, ushbu Web Storage API-laridan qanday foydalanishni ko'rib chiqaylik.

## HTML5 veb-xotira ob'ektlari

HTML veb-xotirasi mijozda ma'lumotlarni saqlash uchun ikkita ob'ektni taqdim etadi:

- window.localStorage -  amal qilish muddati tugamaydigan ma'lumotlarni saqlaydi
- window.sessionStorage - bir seans uchun ma'lumotlarni saqlaydi (brauzer yorlig'i yopilganda ma'lumotlar yo'qoladi) Ko'pgina zamonaviy brauzerlar veb-xotirani qo'llab-quvvatlaydi, ammo localStorage va sessionStorage uchun brauzer yordamini tekshirish yaxshidir. Keling, Web Storage ob'ektlari uchun mavjud usullarni ko'rib chiqaylik.

Web Storage objects:

- _localStorage_ - localStorage ob'ektini ko'rsatish uchun
- _localStorage.clear()_ - lokal xotiradagi hamma narsani o'chirish uchun
- _localStorage.setItem()_ - localStorage-da ma'lumotlarni saqlash uchun. U kalit va qiymat parametrlarini oladi.
- _localStorage.getItem()_ - localStorage-da saqlangan ma'lumotlarni ko'rsatish uchun. Parametr sifatida kalitni oladi.
- _localStorage.removeItem()_ - localStorage-dan saqlangan elementni olib tashlash uchun. U kalitni parametr sifatida oladi.
- _localStorage.key()_ - localStorage-da saqlangan ma'lumotlarni ko'rsatish uchun. Parametr sifatida indeksni oladi.

![local_storage](../images/local_storage.png)

### Elementni localStorage-ga sozlash

Biz ma'lumotlarni localStorage-da saqlashni o'rnatganimizda, u satr sifatida saqlanadi. Agar biz massiv yoki ob'ektni saqlayotgan bo'lsak, aks holda biz massiv tuzilishini yoki asl ma'lumotlarning ob'ekt tuzilishini yo'qotmasak, formatni saqlab qolish uchun avval uni qatorlashtiramiz.

Biz ma'lumotlarni localStorage-da _localStorage.setItem_ usuli yordamida saqlaymiz.

```js
//syntax
localStorage.setItem('key', 'value')
```

- Satrni localStorageda saqlash

```js
localStorage.setItem('firstName', 'Asabeneh') // since the value is string we do not stringify it
console.log(localStorage)
```

```sh
Storage {firstName: 'Asabeneh', length: 1}
```

- Raqamni localStorageda saqlash

```js
localStorage.setItem('age', 200)
console.log(localStorage)
```

```sh
 Storage {age: '200', firstName: 'Asabeneh', length: 2}
```

- Massivni localStorageda saqlash. Agar biz massiv, ob'ekt yoki ob'ekt massivini saqlayotgan bo'lsak, avval ob'ektni stringifikatsiya qilishimiz kerak. Quyidagi misolga qarang.

```js
const skills = ['HTML', 'CSS', 'JS', 'React']
//Formatni saqlab qolish uchun avvalo malakalar massivini stringizatsiya qilish kerak. 
const skillsJSON = JSON.stringify(skills, undefined, 4)
localStorage.setItem('skills', skillsJSON)
console.log(localStorage)
```

```sh
Storage {age: '200', firstName: 'Asabeneh', skills: 'HTML,CSS,JS,React', length: 3}
```

```js
let skills = [
  { tech: 'HTML', level: 10 },
  { tech: 'CSS', level: 9 },
  { tech: 'JS', level: 8 },
  { tech: 'React', level: 9 },
  { tech: 'Redux', level: 10 },
  { tech: 'Node', level: 8 },
  { tech: 'MongoDB', level: 8 }
]

let skillJSON = JSON.stringify(skills)
localStorage.setItem('skills', skillJSON)
```

- Ob'ektni localStorageda saqlash. Ob'ektlarni localStorage-ga saqlashdan oldin, ob'ektni stringizatsiya qilish kerak.

```js
const user = {
  firstName: 'Asabeneh',
  age: 250,
  skills: ['HTML', 'CSS', 'JS', 'React']
}

const userText = JSON.stringify(user, undefined, 4)
localStorage.setItem('user', userText)
```

### LocalStorage dan element olish

Mahalliy xotiradan ma'lumotlarni _localStorage.getItem()_ usuli yordamida olamiz.

```js
//syntax
localStorage.getItem('key')
```

```js
let firstName = localStorage.getItem('firstName')
let age = localStorage.getItem('age')
let skills = localStorage.getItem('skills')
console.log(firstName, age, skills)
```

```sh
 'Asabeneh', '200', '['HTML','CSS','JS','React']'
```

Ko'rib turganingizdek, mahorat string formatida. Uni oddiy massivga ajratish uchun JSON.parse() dan foydalanamiz.

```js
let skills = localStorage.getItem('skills')
let skillsObj = JSON.parse(skills, undefined, 4)
console.log(skillsObj)
```

```sh
['HTML','CSS','JS','React']
```

### LokalStorage ni tozalash

Aniq usul mahalliy xotirada saqlangan hamma narsani tozalaydi

```js
localStorage.clear()
```

🌕 Siz qaror qildingiz. Endi siz veb-xotiralarni bilardingiz va kichik ma'lumotlarni mijoz brauzerlarida qanday saqlashni bildingiz. Siz buyuklik sari 17 qadam oldindasiz. Endi miyangiz va mushaklaringiz uchun bir nechta mashqlarni bajaring.

## Mashqlar

### Mashqlar: Level 1

1. Ismingiz, familiyangiz, yoshingiz, mamlakatingiz, shaharingizni brauzeringizning localStorage-da saqlang.

### Mashqlar: Level 2

1. Talaba ob'ektini yarating. Talaba ob'ektida ism, familiya, yosh, malaka, mamlakat, ro'yxatga olingan kalitlar va kalitlar uchun qiymatlar bo'ladi. Talaba ob'ektini brauzeringizning localStorage-da saqlang.

### Mashqlar: Level 3

1. personAccount deb nomlangan ob'ekt yarating. Unda ism, familiya, daromadlar, xarajatlar xususiyatlari va jami daromad, jami xarajatlar, accountInfo, addIncome, addExpense va accountBalance usullari mavjud. Daromadlar - bu daromadlar majmui va uning tavsifi va xarajatlari ham xarajatlar va uning tavsifi.

🎉 TABRIKLAYMAN ! 🎉

[<< 16-kun](../16_Day_JSON/16_day_json.md) | [18-kun >>](../18_Day_Promises/18_day_promises.md)
