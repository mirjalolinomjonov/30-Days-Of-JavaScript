<div align="center">
  <h1> JavaScript-ning 30 kuni: Console Obyekt Methodlari</h1>
  <a class="header-badge" target="_blank" href="https://www.linkedin.com/in/asabeneh/">
  <img src="https://img.shields.io/badge/style--5eba00.svg?label=LinkedIn&logo=linkedin&style=social">
  </a>
  <a class="header-badge" target="_blank" href="https://twitter.com/Asabeneh">
  <img alt="Twitter Follow" src="https://img.shields.io/twitter/follow/asabeneh?style=social">
  </a>

<sub>Author:
<a href="https://www.linkedin.com/in/asabeneh/" target="_blank">Asabeneh Yetayeh</a><br>
<small> January, 2022</small>
</sub>

</div>

[<< 12-kun](../12_Day_Regular_expressions/12_day_regular_expressions.md) | [14-kun>>](../14_Day_Error_handling/14_day_error_handling.md)

![Thirty Days Of JavaScript](../images/banners/day_1_13.png)

- [13-Kun](#13-kun)
  - [Console Obyekt Methodlari](#console-obyekt-methodlari)
    - [console.log()](#consolelog)
    - [console.warn()](#consolewarn)
    - [console.error()](#consoleerror)
    - [console.table()](#consoletable)
    - [console.time()](#consoletime)
    - [console.info()](#consoleinfo)
    - [console.assert()](#consoleassert)
    - [console.group()](#consolegroup)
    - [console.count()](#consolecount)
    - [console.clear()](#consoleclear)
  - [Mashqlar](#mashqlar)
    - [Mashqlar:Level 1](#mashqlarlevel-1)
    - [Mashqlar:Level 2](#mashqlarlevel-2)
    - [Mashqlar:Level 3](#mashqlarlevel-3)

# 13-Kun

## Console Obyekt Methodlari

Ushbu bo'limda biz konsol va konsol ob'ekt usullari haqida gapiramiz. Mutlaq yangi boshlanuvchilar odatda qaysi birini ishlatishni bilishmaydi: console.log(), document.write() yoki document.getElementById.

Brauzer konsolida chiqishni ko'rsatish uchun konsol ob'ekt usullaridan foydalanamiz va brauzer hujjatida (ko'rish porti) chiqishni ko'rsatish uchun document.write dan foydalanamiz. Ikkala usul ham faqat sinov va disk raskadrovka maqsadlarida qo'llaniladi. Konsol usuli brauzerdagi eng mashhur sinov va disk raskadrovka vositasidir. DOM bilan ishlashni xohlayotganimizda, biz document.getElementById() dan foydalanamiz, JavaScript-ni ishlatib ko'ring. Biz boshqa bo'limda DOMni ko'rib chiqamiz.

Mashhur, console.log() usulidan tashqari, konsol boshqa usullarni ham taqdim etadi.

### console.log()

Brauzer konsolida chiqishni ko'rsatish uchun console.log() dan foydalanamiz. Biz qiymatlarni almashtira olamiz va shuningdek, %c yordamida tizimdan chiqishni uslublashimiz mumkin.

- Brauzer konsolida chiqish ko'rsatilmoqda

```js
console.log('30 Days of JavaScript')
```

```sh
30 Days of JavaScript
```

- Almashtirish

```js
console.log('%d %s of JavaScript', 30, 'Days')
```

```sh
30 Days of JavaScript
```

- CSS

Biz CSS yordamida jurnalga yozish xabarini shakllantirishimiz mumkin. Natijani ko'rish uchun quyidagi koddan nusxa oling va brauzer konsoliga joylashtiring.

```js
console.log('%c30 Days Of JavaScript', 'color:green') // log output is green
console.log(
  '%c30 Days%c %cOf%c %cJavaScript%c',
  'color:green',
  '',
  'color:red',
  '',
  'color:yellow'
) // log output green red and yellow text
```

### console.warn()

Brauzerda ogohlantirish uchun console.warn() dan foydalanamiz. Masalan, paket versiyasi yoki noto'g'ri amaliyotlar haqida eskirish haqida xabar berish yoki ogohlantirish. Ogohlantirish xabarlarini ko'rish uchun quyidagi koddan nusxa oling va brauzer konsoliga joylashtiring.

```js
console.warn('This is a warning')
console.warn(
  'You are using React. Do not touch the DOM. Virtual DOM will take care of handling the DOM!'
)
console.warn('Warning is different from error')
```

### console.error()

console.error() usullari xato xabarlarini ko'rsatadi.

```js
console.error('This is an error message')
console.error('We all make mistakes')
```

### console.table()

console.table() usuli ma'lumotlarni konsoldagi jadval sifatida ko'rsatadi. Jadval ma'lumotlarini jadval sifatida ko'rsatadi. console.table() massiv yoki ob'ekt bo'lishi kerak bo'lgan bitta talab qilinadigan argument ma'lumotlarini va bitta qo'shimcha ixtiyoriy parametr ustunlarini oladi.

Avval oddiy massivdan boshlaylik. Quyidagi kod ikkita ustunli jadvalni ko'rsatadi. Nomlarni ko'rsatish uchun indeks va qiymat ustunini ko'rsatish uchun indeks ustuni

```js
const names = ['Asabeneh', 'Brook', 'David', 'John']
console.table(names)
```

Keling, ob'ektning natijasini ham tekshiramiz. Bu ikkita ustunli jadvalni yaratadi: kalitlarni o'z ichiga olgan indeks ustuni va qiymat ustuni ob'ektning qiymatlarini o'z ichiga oladi.

```js
const user = {
  name: 'Asabeneh',
  title: 'Programmer',
  country: 'Finland',
  city: 'Helsinki',
  age: 250
}
console.table(user)
```

Qolgan misollarni brauzer konsoliga nusxalash va joylashtirish orqali tekshiring.

```js
const countries = [
  ['Finland', 'Helsinki'],
  ['Sweden', 'Stockholm'],
  ['Norway', 'Oslo']
]
console.table(countries)
```

```js
const users = [
  {
    name: 'Asabeneh',
    title: 'Programmer',
    country: 'Finland',
    city: 'Helsinki',
    age: 250
  },
  {
    name: 'Eyob',
    title: 'Teacher',
    country: 'Sweden',
    city: 'London',
    age: 25
  },
  {
    name: 'Asab',
    title: 'Instructor',
    country: 'Norway',
    city: 'Oslo',
    age: 22
  },
  {
    name: 'Matias',
    title: 'Developer',
    country: 'Denmark',
    city: 'Copenhagen',
    age: 28
  }
]
console.table(users)
```

### console.time()

Operatsiya qancha davom etishini kuzatish uchun foydalanishingiz mumkin bo'lgan taymerni ishga tushiradi. Siz har bir taymerga o'ziga xos nom berasiz va ma'lum bir sahifada 10 000 tagacha taymer ishlaydi. Xuddi shu nom bilan console.timeEnd() ga qo'ng'iroq qilsangiz, brauzer taymer ishga tushirilgandan beri o'tgan vaqtni millisekundlarda chiqaradi.

```js
const countries = [
  ['Finland', 'Helsinki'],
  ['Sweden', 'Stockholm'],
  ['Norway', 'Oslo']
]

console.time('Regular for loop')
for (let i = 0; i < countries.length; i++) {
  console.log(countries[i][0], countries[i][1])
}
console.timeEnd('Regular for loop')

console.time('for of loop')
for (const [name, city] of countries) {
  console.log(name, city)
}
console.timeEnd('for of loop')

console.time('forEach loop')
countries.forEach(([name, city]) => {
  console.log(name, city)
})
console.timeEnd('forEach loop')
```

```sh
Finland Helsinki
Sweden Stockholm
Norway Oslo
Regular for loop: 0.34716796875ms
Finland Helsinki
Sweden Stockholm
Norway Oslo
for of loop: 0.26806640625ms
Finland Helsinki
Sweden Stockholm
Norway Oslo
forEach loop: 0.358154296875ms
```

Yuqoridagi natijaga ko'ra, muntazam for tsikli for of yoki forEach tsikliga qaraganda sekinroq.


### console.info()

U brauzer konsolida ma'lumot xabarini ko'rsatadi.

```js
console.info('30 Days Of JavaScript challenge is trending on Github')
console.info('30 Days Of fullStack challenge might be released')
console.info('30 Days Of HTML and CSS challenge might be released')
```

### console.assert()

Agar tasdiq noto'g'ri bo'lsa, console.assert() usullari konsolga xato xabari yozadi. Agar da'vo haqiqat bo'lsa, hech narsa bo'lmaydi. Birinchi parametr tasdiqlash ifodasidir. Agar bu ibora noto'g'ri bo'lsa, Tasdiqlash muvaffaqiyatsiz tugadi xato xabari ko'rsatiladi.

```js
console.assert(4 > 3, '4 is greater than 3') // hech qanday natija 
console.assert(3 > 4, '3 is not greater than 4') // Tasdiqlash bajarilmadi: 3 4 dan katta emas

for (let i = 0; i <= 10; i += 1) {
  let errorMessage = `${i} is not even`
  console.log('the # is ' + i)
  console.assert(i % 2 === 0, { number: i, errorMessage: errorMessage })
}
```

### console.group()

console.group() turli jurnal guruhlarini guruhlashga yordam beradi. Quyidagi koddan nusxa oling va uni brauzer konsoliga guruhlarga joylashtiring.

```js
const names = ['Asabeneh', 'Brook', 'David', 'John']
const countries = [
  ['Finland', 'Helsinki'],
  ['Sweden', 'Stockholm'],
  ['Norway', 'Oslo']
]
const user = {
  name: 'Asabeneh',
  title: 'Programmer',
  country: 'Finland',
  city: 'Helsinki',
  age: 250
}
const users = [
  {
    name: 'Asabeneh',
    title: 'Programmer',
    country: 'Finland',
    city: 'Helsinki',
    age: 250
  },
  {
    name: 'Eyob',
    title: 'Teacher',
    country: 'Sweden',
    city: 'London',
    age: 25
  },
  {
    name: 'Asab',
    title: 'Instructor',
    country: 'Norway',
    city: 'Oslo',
    age: 22
  },
  {
    name: 'Matias',
    title: 'Developer',
    country: 'Denmark',
    city: 'Copenhagen',
    age: 28
  }
]

console.group('Names')
console.log(names)
console.groupEnd()

console.group('Countries')
console.log(countries)
console.groupEnd()

console.group('Users')
console.log(user)
console.log(users)
console.groupEnd()
```

### console.count()

Bu console.count() chaqirilgan vaqt sonini chop etadi. U string label parametrini oladi. Funktsiyaning necha marta chaqirilishini hisoblash juda foydali. Quyidagi misolda console.count() usuli uch marta ishlaydi

```js
const func = () => {
  console.count('Function has been called')
}
func()
func()
func()
```

```sh
Function has been called: 1
Function has been called: 2
Function has been called: 3
```

### console.clear()

console.clear() brauzer konsolini tozalaydi.

🌕 Yaxshi ishlashda davom eting. Bosishda davom eting, osmon chegara! Siz hozirgina 13-kun sinovlarini yakunladingiz va siz buyuklik sari 13 qadam oldindasiz. Endi miyangiz va mushaklaringiz uchun bir nechta mashqlarni bajaring.

## Mashqlar

### Mashqlar:Level 1

1.  Mamlakatlar massivini jadval sifatida ko'rsatish
2.  Mamlakatlar ob'ektini jadval sifatida ko'rsatish
3.  Jurnallarni guruhlash uchun console.group() dan foydalaning

### Mashqlar:Level 2

1. 10 > 2 * 10 console.assert() dan foydalaning
2. console.warn() yordamida ogohlantirish xabarini yozing.
3. console.error() yordamida xato xabarini yozing

### Mashqlar:Level 3

1. Quyidagi tsikllar orasidagi tezlik farqini tekshiring: while, for, for of, forEach

🎉 TABRIKLAYMAN ! 🎉

[<< 12-kun](../12_Day_Regular_expressions/12_day_regular_expressions.md) | [14-kun>>](../14_Day_Error_handling/14_day_error_handling.md)
