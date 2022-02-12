<div align="center">
  <h1> JavaScript-ning 30 kuni: Toza kod yozish</h1>
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

[<< 19-kun](../19_Day_Closures/19_day_closures.md) | [Day 21 >>](../21_Day_DOM/21_day_dom.md)

![Thirty Days Of JavaScript](../images/banners/day_1_20.png)
- [20-Kun](#20-kun)
  - [Toza kod yozish](#toza-kod-yozish)
    - [JavaScript Style Guide(Uslublar bo'yicha qo'llanma)](#javascript-style-guideuslublar-boyicha-qollanma)
    - [Nima uchun bizga uslublar bo'yicha qo'llanma kerak](#nima-uchun-bizga-uslublar-boyicha-qollanma-kerak)
      - [Airbnb JavaScript Style Guide](#airbnb-javascript-style-guide)
      - [Standard JavaScript Style Guide](#standard-javascript-style-guide)
      - [Google JavaScript Style Guide](#google-javascript-style-guide)
    - [JavaScript kodlash konventsiyalari](#javascript-kodlash-konventsiyalari)
      - [Konventsiyalar 30DaysOfJavaScript-da qo'llaniladi](#konventsiyalar-30daysofjavascript-da-qollaniladi)
      - [O'zgaruvchilar](#ozgaruvchilar)
      - [Massivlar](#massivlar)
      - [Funksiyalar](#funksiyalar)
      - [Tsikllar](#tsikllar)
      - [Ob'ektlar](#obektlar)
      - [Shartlar](#shartlar)
      - [Klasslar](#klasslar)

# 20-Kun

## Toza kod yozish

### JavaScript Style Guide(Uslublar bo'yicha qo'llanma)

JavaScript uslubi uchun qo'llanma - bu JavaScript kodini qanday yozish va tartibga solish kerakligini ko'rsatadigan standartlar to'plami. Ushbu bo'limda biz JavaScript qo'llanmalari va toza kodni qanday yozish haqida gaplashamiz.

JavaScript - bu dasturlash tili va inson tili kabi sintaksisga ega. JavaScript sintaksisi ishonchli va sodda bo'lishi uchun ma'lum bir uslub ko'rsatmalariga muvofiq yozilishi kerak.

### Nima uchun bizga uslublar bo'yicha qo'llanma kerak

Siz uzoq vaqtdan beri yolg'iz kodlashdingiz, lekin hozir u jamoada ishlayotganga o'xshaydi. Baribir, u ishlayotgan ekan, kod yozishingiz muhim emas, lekin bitta loyihada va bir xil kod bazasida 10 yoki 20 yoki undan ortiq dasturchidan iborat jamoada ishlaganingizda, kod tartibsiz va agar mavjud bo'lsa, uni boshqarish qiyin bo'ladi. amal qilish uchun hech qanday ko'rsatmalar yo'q.

Siz o'zingizning ko'rsatmalaringiz va konventsiyalaringizni ishlab chiqishingiz yoki yaxshi ishlab chiqilgan ko'rsatmalarni moslashingiz mumkin. Keling, eng keng tarqalgan ko'rsatmalarni bilib olaylik. 
Eng keng tarqalgan JavaScript uslubiy qo'llanmalar:

- Airbnb JavaScript Style Guide
- JavaScript Standard Style Guide
- Google JavaScript Style Guide

#### Airbnb JavaScript Style Guide

[Airbnb style guide](https://github.com/airbnb/javascript) internetdagi eng mashhur JavaScript uslubiy qo'llanmalaridan biriga ega. U JavaScript-ning deyarli barcha jihatlarini qamrab oladi va u ko'plab ishlab chiquvchilar va kompaniyalar tomonidan qabul qilinadi. Airbnb uslubi bo'yicha qo'llanmani tekshirishingiz mumkin . Men ham sinab ko'rishni tavsiya qilaman. Ularning uslubini ishlatish juda oson va tushunish oson.

#### Standard JavaScript Style Guide

Bu [style guide](https://standardjs.com/) Airbnb kabi mashhur emas, lekin uni ko'rib chiqishga arziydi. Ular uslubiy qo'llanmada nuqta-vergulni olib tashladilar.

#### Google JavaScript Style Guide

Men Google yo'riqnomasi haqida ko'p gapirmayman va men foydalanmadim, aksincha, ushbu [havolani](https://google.github.io/styleguide/jsguide.html) ko'rib chiqishingizni tavsiya qilaman.

### JavaScript kodlash konventsiyalari

Ushbu muammoni hal qilishda biz umumiy JavaScript kodlash yozish qoidalari va qo'llanmalaridan ham foydalandik. Kodlash konventsiyalari - bu shaxs, jamoa yoki kompaniya tomonidan ishlab chiqilgan dasturlash uslubi bo'yicha ko'rsatmalar.

Kodlash konventsiyalari yordam beradi:

- toza kod yozish uchun
- kodni o'qishni yaxshilash uchun
- kodni qayta ishlatish va texnik xizmat ko'rsatishni yaxshilash

Kodlash konventsiyalari o'z ichiga oladi

- O'zgaruvchilar uchun nom berish va e'lon qilish qoidalari
- Funktsiyalarni nomlash va e'lon qilish qoidalari
- Oq bo'shliq, chekinish va sharhlardan foydalanish qoidalari
- Dasturlash amaliyoti va tamoyillari

#### Konventsiyalar 30DaysOfJavaScript-da qo'llaniladi

Ushbu tanlovda biz odatiy JavaScript konventsiyasiga amal qilamiz, lekin men yozishni afzal ko'rganimni ham qo'shdim.

- Biz o'zgaruvchilar va funktsiyalar uchun camelCase-dan foydalandik.
- Barcha o'zgaruvchilar nomlari harf bilan boshlanadi.
- Biz konstantalar, massivlar, obyektlar va funksiyalar uchun const dan foydalanishni tanladik . Ikki tirnoq o'rniga biz bitta qo'shtirnoq yoki teskari belgidan foydalanishni tanladik. Yagona tirnoq modaga aylanib bormoqda.
- Kodimizdan nuqtali vergulni ham olib tashladik, ammo bu shaxsiy imtiyozlar masalasidir.
- Arifmetik operatorlar, belgilash operatorlari atrofida va verguldan keyin bo'sh joy
- Funktsiya deklaratsiyasi o'rniga o'q funktsiyasi
- Agar funktsiya bitta chiziq bo'lsa, yashirin qaytish o'rniga aniq qaytish
- Ob'ektning oxirgi qiymatida oxirgi vergul yo'q
- Biz uzunroq versiya o'rniga +=, -=, *= /=, **= ma'qullaymiz
- Biz console.log() dan foydalanganda, konsol qayerdan kelayotganini aniqlash uchun teglar qatori bilan chop etish yaxshidir.

#### O'zgaruvchilar

```js

let firstName = 'Asabeneh'
let lastName = 'Yetayeh'
let country = 'Finland'
let city = 'Helsinki'

const PI = Math.PI
const gravity = 9.81
```

#### Massivlar

Biz massiv nomlarini ko‘plik qilishni tanladik

- names
- numbers
- countries
- languages
- skills
- fruits
- vegetables

```js
// arrays
const names = ['Asabeneh', 'Mathias', 'Elias', 'Brook']
const numbers = [0, 3.14, 9.81, 37, 98.6, 100]
const countries = ['Finland', 'Denmark', 'Sweden', 'Norway', 'Iceland']
const languages = ['Amharic', 'Arabic', 'English', 'French', 'Spanish']
const skills = ['HTML', 'CSS', 'JavaScript', 'React', 'Python']
const fruits = ['banana', 'orange', 'mango', 'lemon']
const vegetables = ['Tomato', 'Potato', 'Cabbage', 'Onion', 'Carrot']
```

#### Funksiyalar

Hozircha siz funksiya deklaratsiyasi, ifoda funksiyasi, strelka funksiyasi va anonim funksiyani juda yaxshi bilasiz. Ushbu muammoni hal qilishda biz boshqa funktsiyalar o'rniga o'q funktsiyasidan foydalanamiz. Ok funksiyasi boshqa funksiyalarni almashtirmaydi. Bundan tashqari, o'q funktsiyalari va funksiya deklaratsiyasi mutlaqo bir xil emas. Shuning uchun siz qachon va qachon foydalanmasligingizni bilishingiz kerak. Farqni boshqa bo'limlarda batafsil yoritib beraman. Agar funktsiya bitta chiziq bo'lsa, biz yashirin qaytarish o'rniga aniq qaytarishdan foydalanamiz

```js
// shaxsning toʻliq ismini chop etadigan funksiya 
const printFullName = (firstName, lastName) => firstName + ' ' + lastName

// sonning kvadratini hisoblaydigan funksiya 
const square = (n) => n * n

// tasodifiy hexa ranglarini yaratuvchi funktsiya 
const hexaColor = () => {
  const str = '0123456789abcdef'
  let hexa = '#'
  let index
  for (let i = 0; i < 6; i++) {
    index = Math.floor(Math.random() * str.length)
    hexa += str[index]
  }
  return hexa
}

// sana va vaqtni ko'rsatadigan funktsiya
const showDateTime = () => {
  const now = new Date()
  const year = now.getFullYear()
  const month = now.getMonth() + 1
  const date = now.getDate()
  let hours = now.getHours()
  let minutes = now.getMinutes()
  if (hours < 10) {
    hours = '0' + hours
  }
  if (minutes < 10) {
    minutes = '0' + minutes
  }

  const dateMonthYear = date + '.' + month + '.' + year
  const time = hours + ':' + minutes
  const fullTime = dateMonthYear + ' ' + time
  return fullTime
}
```

#### Tsikllar

Ushbu qiyinchiliklarda biz ko'p turdagi halqalarni ko'rib chiqamiz. Muntazam for sikli, while sikli, do while sikli, for of loop, forEach tsikli va for in tsikli. 
Keling, ulardan qanday foydalanishimizni ko'rib chiqaylik:

```js
for (let i = 0; i < n; i++){
    console.log()
}

// massiv oʻzgaruvchisini eʼlon qilish
const names = ['Asabeneh', 'Mathias', 'Elias', 'Brook']

//  massivni muntazam for siklidan foydalanib iteratsiya qilish
let len = names.length;
for(let i = 0; i < len; i++){
    console.log(names[i].toUpperCase())
}


// for of yordamida massivni takrorlash
for( const name of names) {
    console.log(name.toUpperCasee())
}

//  forEach yordamida massivni takrorlash
names.forEach((name) => name.toUpperCase())


const person = {
  firstName: 'Asabeneh',
  lastName: 'Yetayeh',
  age: 250,
  country: 'Finland',
  city: 'Helsinki',
  skills: ['HTML','CSS','JavaScript','React','Node','MongoDB','Python','D3.js'],
  isMarried: true
}
for(const key in user) {
    console.log(key)
}

```

#### Ob'ektlar

Biz ob'ektni **const** bilan literal deb e'lon qilamiz .


```js
// declaring object literal
const person = {
  firstName: 'Asabeneh',
  lastName: 'Yetayeh',
  age: 250,
  country: 'Finland',
  city: 'Helsinki',
  skills: ['HTML','CSS','JavaScript','React','Node','MongoDB','Python','D3.js'],
  isMarried: true
}
// ob'ekt kalitlari orqali iteratsiya
for(const key in person) {
    console.log(key, person[key])
}


```

#### Shartlar

Oldingi qiyinchiliklarda if, if other, if another if, switch va uchlik operatorlarni aytamiz.

 ```js
 // sintaksis
if (condition) {
  // kodning bu qismi to'g'ri shart uchun ishlaydi 
} else {
  // kodning bu qismi noto'g'ri holat uchun ishlaydi 
}
 ```

 ```js
 // if else
let num = 3
if (num > 0) {
  console.log(`${num} is a positive number`)
} else {
  console.log(`${num} is a negative number`)
}
//  3 is a positive number
 ```

 ```js
 // if else if else if else

let a = 0
if (a > 0) {
  console.log(`${a} is a positive number`)
} else if (a < 0) {
  console.log(`${a} is a negative number`)
} else if (a == 0) {
  console.log(`${a} is zero`)
} else {
  console.log(`${a} is not a number`)
}
 ```

 ```js
 // Switch More Examples
let dayUserInput = prompt('What day is today ?')
let day = dayUserInput.toLowerCase()

switch (day) {
  case 'monday':
    console.log('Today is Monday')
    break
  case 'tuesday':
    console.log('Today is Tuesday')
    break
  case 'wednesday':
    console.log('Today is Wednesday')
    break
  case 'thursday':
    console.log('Today is Thursday')
    break
  case 'friday':
    console.log('Today is Friday')
    break
  case 'saturday':
    console.log('Today is Saturday')
    break
  case 'sunday':
    console.log('Today is Sunday')
    break
  default:
    console.log('It is not a week day.')
}
 ```

 ```js
 // ternary

 let isRaining = true
isRaining
  ? console.log('You need a rain coat.')
  : console.log('No need for a rain coat.')
 ```

#### Klasslar

Biz katta harf bilan boshlanadigan CamelCase bilan sinfni e'lon qilamiz.

```js
// sintaksis 
class ClassName {
    // code goes here
}
```

```js
// defining class
class Person {
  constructor(firstName, lastName) {
    console.log(this) // Check the output from here
    this.firstName = firstName
    this.lastName = lastName
  }
}

```

Qaysi uslub qo'llanmasiga amal qilsangiz, izchil bo'ling. Ba'zi dasturlash paradigmalari va dizayn naqshlariga amal qiling. Esingizda bo'lsin, agar siz kodingizni ma'lum tartibda yoki uslubda yozmasangiz, kodingizni o'qish qiyin bo'ladi. Shunday qilib, o'zingiz uchun yoki o'qilishi mumkin bo'lgan kod yozish orqali kodingizni o'qimoqchi bo'lgan kishi uchun yaxshilik qiling.

🌕 Siz tartiblisiz. Endi siz toza kod yozishni bilasiz, shuning uchun ingliz tilini biladigan har bir kishi sizning kodingizni tushunishi mumkin. Siz doimo rivojlanib borasiz va siz buyuklik sari 20 qadam oldindasiz.

🎉 TABRIKLAYMAN ! 🎉

[<< 19-kun](../19_Day_Closures/19_day_closures.md) | [Day 21 >>](../21_Day_DOM/21_day_dom.md)
