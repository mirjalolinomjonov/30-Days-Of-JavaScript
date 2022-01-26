<div align="center">
  <h1> 30 kunlik JavaScript: Obyektlar</h1>
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

[<< 7-kun](../07_Day_Functions/07_day_functions.md) | [9-kun >>](../09_Day_Higher_order_functions/09_day_higher_order_functions.md)

![Thirty Days Of JavaScript](../images/banners/day_1_8.png)

- [📔 8-Kun](#-8-kun)
  - [Qo'llanish doirasi](#qollanish-doirasi)
    - [Window (Qo'llanish doirasi)](#window-qollanish-doirasi)
    - [Global (Qo'llanish doirasi)](#global-qollanish-doirasi)
    - [Local (Qo'llanish doirasi)](#local-qollanish-doirasi)
  - [📔 Object](#-object)
    - [Bo'sh Obyekt yaratish](#bosh-obyekt-yaratish)
    - [Qiymatlar bilan Obyekt yaratish](#qiymatlar-bilan-obyekt-yaratish)
    - [Ob'ektdan qiymatlarni olish](#obektdan-qiymatlarni-olish)
    - [Ob'ekt methodlarini yaratish](#obekt-methodlarini-yaratish)
    - [Ob'ekt uchun yangi kalitni o'rnatish](#obekt-uchun-yangi-kalitni-ornatish)
    - [Ob'ekt methodlari](#obekt-methodlari)
      - [Object.keys() yordamida obyekt kalitlarini olish](#objectkeys-yordamida-obyekt-kalitlarini-olish)
      - [Object.values() yordamida obyekt qiymatlarini olish](#objectvalues-yordamida-obyekt-qiymatlarini-olish)
      - [Object.entries() yordamida obyekt kalitlari va qiymatlarini olish](#objectentries-yordamida-obyekt-kalitlari-va-qiymatlarini-olish)
      - [hasOwnProperty() yordamida xususiyatlarni tekshirish](#hasownproperty-yordamida-xususiyatlarni-tekshirish)
  - [💻 Mashqlar](#-mashqlar)
    - [Mashqlar: Level 1](#mashqlar-level-1)
    - [Mashqlar: Level 2](#mashqlar-level-2)
    - [Mashqlar: Level 3](#mashqlar-level-3)

# 📔 8-Kun

## Qo'llanish doirasi

O'zgaruvchi dasturlashning asosiy qismidir. Biz turli xil ma'lumotlar turlarini saqlash uchun o'zgaruvchini e'lon qilamiz. O'zgaruvchini e'lon qilish uchun var , let va const kalit so'zidan foydalanamiz . O'zgaruvchi turli sohalarda e'lon qilinishi mumkin. Ushbu bo'limda biz var yoki let dan foydalanganda o'zgaruvchilar doirasi, qamrovini ko'ramiz.
O'zgaruvchilar doirasi quyidagilar bo'lishi mumkin:

- Window
- Global
- Local

O'zgaruvchi global yoki mahalliy yoki oyna doirasida e'lon qilinishi mumkin. Biz global va mahalliy miqyosni ko'ramiz. Let, var yoki constsiz e'lon qilingan har qanday narsa oyna darajasida qamrab olinadi.

Tasavvur qilaylik, bizda scope.js fayli bor.

### Window (Qo'llanish doirasi)

console.log() dan foydalanmasdan brauzeringizni oching va tekshiring, agar brauzerda a yoki b yozsangiz, a va b qiymatini ko'rasiz. Bu oynada a va b allaqachon mavjud degan ma'noni anglatadi.

```js
//scope.js
a = 'JavaScript' // har qanday joyda topiladigan oyna doirasi 
b = 10 // bu oyna doirasi o'zgaruvchisi 
function letsLearnScope() {
  console.log(a, b)
  if (true) {
    console.log(a, b)
  }
}
console.log(a, b) // chaqirish mumkin
```

### Global (Qo'llanish doirasi)

Global e'lon qilingan o'zgaruvchiga bitta faylning hamma joyidan kirish mumkin. Ammo global atama nisbiydir. U fayl uchun global bo'lishi mumkin yoki ba'zi kodlar blokiga nisbatan global bo'lishi mumkin.

```js
//scope.js
let a = 'JavaScript' //  global qamrov bu faylning istalgan joyidan topiladi 
let b = 10 //  global qamrov bu fayl 
function letsLearnScope() {
  console.log(a, b) //  JavaScript 10, kirish mumkin 
  if (true) {
    let a = 'Python'
    let b = 100
    console.log(a, b) // Python 100
  }
  console.log(a, b)
}
letsLearnScope()
console.log(a, b) // JavaScript 10, kirish mumkin
```

### Local (Qo'llanish doirasi)

Mahalliy deb e'lon qilingan o'zgaruvchiga faqat ma'lum blok kodida kirish mumkin.

```js
//scope.js
let a = 'JavaScript' // global qamrov bu faylning istalgan joyidan topiladi 
let b = 10 // global qamrov bu fayl 
function letsLearnScope() {
  console.log(a, b) //  JavaScript 10, kirish mumkin 
  let value = false
  if (true) {
    // biz funksiyadan va funksiyadan tashqariga kira olamiz, lekin 
    // if ichida eʼlon qilingan oʻzgaruvchilarga if blokidan tashqari kirish imkoni boʻlmaydi.
    let a = 'Python'
    let b = 20
    let c = 30
    let d = 40
    value = !value
    console.log(a, b, c) // Python 20 30
  }
  // biz c ga kira olmaymiz, chunki c ning qamrovi faqat if blok
  console.log(a, b, value) // JavaScript 10 true
}
letsLearnScope()
console.log(a, b) //  JavaScript 10, kirish mumkin 
```

Endi siz qamrov haqida tushunchaga egasiz. Var bilan e'lon qilingan o'zgaruvchi faqat funktsiya uchun mo'ljallangan, lekin let yoki const bilan e'lon qilingan o'zgaruvchi blok doirasi (funktsiya bloki, if bloki, sikl bloki va boshqalar). JavaScript-dagi blokirovka bu ikki jingalak qavs ({}) orasidagi koddir.

```js
//scope.js
function letsLearnScope() {
  var gravity = 9.81
  console.log(gravity)

}
// console.log(gravity), Tugallanmagan ReferenceError: tortishish aniqlanmagan

if (true){
  var gravity = 9.81
  console.log(gravity) // 9.81
}
console.log(gravity)  // 9.81

for(var i = 0; i < 3; i++){
  console.log(i) // 1, 2, 3
}
console.log(i)

```

ES6 va undan yuqori versiyalarda let va const mavjud, shuning uchun siz var ning hiyla-nayrangidan aziyat chekmaysiz . Biz ishlatganimizda let o'zgaruvchimiz bloklangan bo'ladi va u kodimizning boshqa qismlarini yuqtirmaydi.

```js
//scope.js
function letsLearnScope() {
  //  let yoki const dan foydalanishingiz mumkin, lekin tortishish kuchi doimiy Men const 
  const gravity = 9.81
  console.log(gravity)

}
// console.log(gravity), Tugallanmagan ReferenceError: tortishish aniqlanmagan

if (true){
  const  gravity = 9.81
  console.log(gravity) // 9.81
}
// console.log(gravity),  Tugallanmagan ReferenceError: tortishish aniqlanmagan

for(let i = 0; i < 3; i++){
  console.log(i) // 1, 2, 3
}
// console.log(i), Tugallanmagan ReferenceError: i aniqlanmagan

```

Let va const doirasi bir xil. Farqi faqat qayta tayinlash. Biz const o'zgaruvchisining qiymatini o'zgartira olmaymiz yoki qayta tayinlay olmaymiz. Let va const dan foydalanishni qat'iy tavsiya qilaman, let va const dan foydalanib , siz toza kod yozasiz va disk raskadrovka qilish qiyin bo'lgan xatolardan qochasiz. Qoida tariqasida, har qanday o'zgaruvchan qiymat uchun let , har qanday doimiy qiymat uchun const va massiv, ob'ekt, o'q funktsiyasi va funksiya ifodasi uchun foydalanishingiz mumkin.

## 📔 Object

Hamma narsa ob'ekt bo'lishi mumkin va ob'ektlarning xususiyatlari va xususiyatlari qiymatlarga ega, shuning uchun ob'ekt kalit qiymat juftligidir. Kalitning tartibi zaxiralanmagan yoki buyurtma yo'q. Ob'ektning literalini yaratish uchun biz ikkita jingalak qavsdan foydalanamiz.

### Bo'sh Obyekt yaratish

Bo'sh ob'ekt

```js
const person = {}
```

### Qiymatlar bilan Obyekt yaratish

Endi shaxs ob'ekti ismi, familiyasi, yoshi, joylashuvi, ko'nikmalari va isMarried xususiyatlariga ega. Xususiyatlar yoki kalitlarning qiymati qator, raqam, mantiqiy, ob'ekt, null, aniqlanmagan yoki funktsiya bo'lishi mumkin.

Keling, ob'ektning ba'zi misollarini ko'rib chiqaylik. Har bir kalit ob'ektda qiymatga ega.

```js
const rectangle = {
  length: 20,
  width: 20
}
console.log(rectangle) // {length: 20, width: 20}

const person = {
  firstName: 'Asabeneh',
  lastName: 'Yetayeh',
  age: 250,
  country: 'Finland',
  city: 'Helsinki',
  skills: [
    'HTML',
    'CSS',
    'JavaScript',
    'React',
    'Node',
    'MongoDB',
    'Python',
    'D3.js'
  ],
  isMarried: true
}
console.log(person)
```

### Ob'ektdan qiymatlarni olish

Ob'ektning qiymatlariga ikkita usul yordamida kirishimiz mumkin:

- yordamida. Agar kalit nomi bitta so'zdan iborat bo'lsa, keyin kalit nomi
- kvadrat qavs va tirnoq yordamida

```js
const person = {
  firstName: 'Asabeneh',
  lastName: 'Yetayeh',
  age: 250,
  country: 'Finland',
  city: 'Helsinki',
  skills: [
    'HTML',
    'CSS',
    'JavaScript',
    'React',
    'Node',
    'MongoDB',
    'Python',
    'D3.js'
  ],
  getFullName: function() {
    return `${this.firstName}${this.lastName}`
  },
  'phone number': '+3584545454545'
}

//  yordamida qiymatlarga kirish. 
console.log(person.firstName)
console.log(person.lastName)
console.log(person.age)
console.log(person.location)

// qiymatga kvadrat qavs va kalit nomi yordamida kirish mumkin
console.log(person['firstName'])
console.log(person['lastName'])
console.log(person['age'])
console.log(person['age'])
console.log(person['location'])

// masalan, telefon raqamiga kirish uchun biz faqat kvadrat qavs usulidan foydalanamiz
console.log(person['phone number'])
```

### Ob'ekt methodlarini yaratish

Endi shaxs obyekti getFullName xususiyatlariga ega. getFullName - bu shaxs ob'ektidagi funksiya va biz uni ob'ekt usuli deb ataymiz. Ushbu kalit so'z ob'ektning o'ziga tegishli. Ob'ektning turli xususiyatlarining qiymatlariga kirish uchun this so'zidan foydalanishimiz mumkin . Biz strelka funksiyasidan ob'ekt usuli sifatida foydalana olmaymiz, chunki bu so'z ob'ektning o'rniga o'q funksiyasi ichidagi oynaga ishora qiladi.
Ob'ektga misol:

```js
const person = {
  firstName: 'Asabeneh',
  lastName: 'Yetayeh',
  age: 250,
  country: 'Finland',
  city: 'Helsinki',
  skills: [
    'HTML',
    'CSS',
    'JavaScript',
    'React',
    'Node',
    'MongoDB',
    'Python',
    'D3.js'
  ],
  getFullName: function() {
    return `${this.firstName} ${this.lastName}`
  }
}

console.log(person.getFullName())
// Asabeneh Yetayeh
```

### Ob'ekt uchun yangi kalitni o'rnatish

Ob'ekt - bu o'zgaruvchan ma'lumotlar tuzilmasi va biz ob'ekt yaratilgandan so'ng uning mazmunini o'zgartirishimiz mumkin.

Ob'ektga yangi kalitlarni o'rnatish

```js
const person = {
  firstName: 'Asabeneh',
  lastName: 'Yetayeh',
  age: 250,
  country: 'Finland',
  city: 'Helsinki',
  skills: [
    'HTML',
    'CSS',
    'JavaScript',
    'React',
    'Node',
    'MongoDB',
    'Python',
    'D3.js'
  ],
  getFullName: function() {
    return `${this.firstName} ${this.lastName}`
  }
}
person.nationality = 'Ethiopian'
person.country = 'Finland'
person.title = 'teacher'
person.skills.push('Meteor')
person.skills.push('SasS')
person.isMarried = true

person.getPersonInfo = function() {
  let skillsWithoutLastSkill = this.skills
    .splice(0, this.skills.length - 1)
    .join(', ')
  let lastSkill = this.skills.splice(this.skills.length - 1)[0]

  let skills = `${skillsWithoutLastSkill}, and ${lastSkill}`
  let fullName = this.getFullName()
  let statement = `${fullName} is a ${this.title}.\nHe lives in ${this.country}.\nHe teaches ${skills}.`
  return statement
}
console.log(person)
console.log(person.getPersonInfo())
```

```sh
Asabeneh Yetayeh is a teacher.
He lives in Finland.
He teaches HTML, CSS, JavaScript, React, Node, MongoDB, Python, D3.js, Meteor, and SasS.
```

### Ob'ekt methodlari

Ob'ektni manipulyatsiya qilishning turli usullari mavjud. Keling, ba'zi mavjud usullarni ko'rib chiqaylik.

_Object.assign_:  Asl ob'ektni o'zgartirmasdan ob'ektni nusxalash uchun

```js
const person = {
  firstName: 'Asabeneh',
  age: 250,
  country: 'Finland',
  city:'Helsinki',
  skills: ['HTML', 'CSS', 'JS'],
  title: 'teacher',
  address: {
    street: 'Heitamienkatu 16',
    pobox: 2002,
    city: 'Helsinki'
  },
  getPersonInfo: function() {
    return `I am ${this.firstName} and I live in ${this.city}, ${this.country}. I am ${this.age}.`
  }
}

//Obyekt methodlari: Object.assign, Object.keys, Object.values, Object.entries
//hasOwnProperty

const copyPerson = Object.assign({}, person)
console.log(copyPerson)
```

#### Object.keys() yordamida obyekt kalitlarini olish

_Object.keys_: Ob'ektning kalitlari yoki xususiyatlarini massiv sifatida olish uchun

```js
const keys = Object.keys(copyPerson)
console.log(keys) //['name', 'age', 'country', 'skills', 'address', 'getPersonInfo']
const address = Object.keys(copyPerson.address)
console.log(address) //['street', 'pobox', 'city']
```

#### Object.values() yordamida obyekt qiymatlarini olish

_Object.values_: Ob'ektning qiymatlarini massiv sifatida olish uchun

```js
const values = Object.values(copyPerson)
console.log(values)
```

#### Object.entries() yordamida obyekt kalitlari va qiymatlarini olish

_Object.entries_: Massivdagi kalit va qiymatlarni olish uchun

```js
const entries = Object.entries(copyPerson)
console.log(entries)
```

#### hasOwnProperty() yordamida xususiyatlarni tekshirish

_hasOwnProperty_: ob'ektda ma'lum bir kalit yoki xususiyat mavjudligini tekshirish uchun

```js
console.log(copyPerson.hasOwnProperty('name'))
console.log(copyPerson.hasOwnProperty('score'))
```

🌕 Siz hayratda qoldirasiz. Endi siz ob'ektlarning kuchi bilan juda zaryadlangansiz. Siz hozirgina 8 kunlik sinovlarni yakunladingiz va siz buyuklik sari 8 qadam oldindasiz. Endi miyangiz va mushaklaringiz uchun bir nechta mashqlarni bajaring.

## 💻 Mashqlar

### Mashqlar: Level 1

1. It deb nomlangan bo'sh ob'ekt yarating
2. Konsolda it ob'ektini chop eting
3. It ob'ekti uchun ism, oyoq, rang, yosh va qobiq xususiyatlarini qo'shing. Poʻstloq xossasi jun ipini qaytaradigan usuldir
4. It ob'ektidan ism, oyoq, rang, yosh va qobiq qiymatini oling
5. It ob'ektining yangi xususiyatlarini o'rnating: zot, getDogInfo

### Mashqlar: Level 2

1. Foydalanuvchilar ob'ektida ko'plab ko'nikmalarga ega bo'lgan odamni toping.
2. Tizimga kirgan foydalanuvchilarni sanash, quyidagi obyektdan 50 balldan kattaroq ball olgan foydalanuvchilarni sanash.

   ````js
   const users = {
     Alex: {
       email: 'alex@alex.com',
       skills: ['HTML', 'CSS', 'JavaScript'],
       age: 20,
       isLoggedIn: false,
       points: 30
     },
     Asab: {
       email: 'asab@asab.com',
       skills: ['HTML', 'CSS', 'JavaScript', 'Redux', 'MongoDB', 'Express', 'React', 'Node'],
       age: 25,
       isLoggedIn: false,
       points: 50
     },
     Brook: {
       email: 'daniel@daniel.com',
       skills: ['HTML', 'CSS', 'JavaScript', 'React', 'Redux'],
       age: 30,
       isLoggedIn: true,
       points: 50
     },
     Daniel: {
       email: 'daniel@alex.com',
       skills: ['HTML', 'CSS', 'JavaScript', 'Python'],
       age: 20,
       isLoggedIn: false,
       points: 40
     },
     John: {
       email: 'john@john.com',
       skills: ['HTML', 'CSS', 'JavaScript', 'React', 'Redux', 'Node.js'],
       age: 20,
       isLoggedIn: true,
       points: 50
     },
     Thomas: {
       email: 'thomas@thomas.com',
       skills: ['HTML', 'CSS', 'JavaScript', 'React'],
       age: 20,
       isLoggedIn: false,
       points: 40
     },
     Paul: {
       email: 'paul@paul.com',
       skills: ['HTML', 'CSS', 'JavaScript', 'MongoDB', 'Express', 'React', 'Node'],
       age: 20,
       isLoggedIn: false,
       points: 40
     }
   }```

3. Foydalanuvchilar ob'ektidan MERN stek ishlab chiqaruvchisi bo'lgan odamlarni toping
4. Asl foydalanuvchilar ob'ektini o'zgartirmasdan foydalanuvchilar ob'ektida ismingizni o'rnating
5. Foydalanuvchi ob'ektining barcha kalitlari yoki xususiyatlarini oling
6. Foydalanuvchilar ob'ektining barcha qiymatlarini oling
7. Mamlakat nomi, poytaxti, aholisi va tillarini chop etish uchun mamlakatlar ob'ektidan foydalaning.

### Mashqlar: Level 3

1. personAccount deb nomlangan ob'ektni yarating . Unda ism, familiya, daromadlar, xarajatlar xossalari mavjud va jami daromad, jami xarajat, accountInfo, addIncome, addExpense va accountBalance usullari mavjud. Daromadlar - bu daromadlar yig'indisi va uning tavsifi va xarajatlari - daromadlar va uning tavsifi.
2. **** Savollar: 2, 3 va 4 quyidagi ikkita massivga asoslangan: foydalanuvchilar va mahsulotlar ()

  ```js
      const users = [
      {
          _id: 'ab12ex',
          username: 'Alex',
          email: 'alex@alex.com',
          password: '123123',
          createdAt:'08/01/2022 9:00 AM',
          isLoggedIn: false
      },
      {
          _id: 'fg12cy',
          username: 'Asab',
          email: 'asab@asab.com',
          password: '123456',
          createdAt:'08/01/2022 9:30 AM',
          isLoggedIn: true
      },
      {
          _id: 'zwf8md',
          username: 'Brook',
          email: 'brook@brook.com',
          password: '123111',
          createdAt:'08/01/2022 9:45 AM',
          isLoggedIn: true
      },
      {
          _id: 'eefamr',
          username: 'Martha',
          email: 'martha@martha.com',
          password: '123222',
          createdAt:'08/01/2022 9:50 AM',
          isLoggedIn: false
      },
      {
          _id: 'ghderc',
          username: 'Thomas',
          email: 'thomas@thomas.com',
          password: '123333',
          createdAt:'08/01/2022 10:00 AM',
          isLoggedIn: false
      }
      ];

      const products = [
    {
      _id: 'eedfcf',
      name: 'mobile phone',
      description: 'Huawei Honor',
      price: 200,
      ratings: [
        { userId: 'fg12cy', rate: 5 },
        { userId: 'zwf8md', rate: 4.5 }
      ],
      likes: []
    },
    {
      _id: 'aegfal',
      name: 'Laptop',
      description: 'MacPro: System Darwin',
      price: 2500,
      ratings: [],
      likes: ['fg12cy']
    },
    {
      _id: 'hedfcg',
      name: 'TV',
      description: 'Smart TV:Procaster',
      price: 400,
      ratings: [{ userId: 'fg12cy', rate: 5 }],
      likes: ['fg12cy']
    }
  ]
  ```

  Tasavvur qiling-a, siz yuqoridagi foydalanuvchilar to'plamini MongoDB ma'lumotlar bazasidan olasiz.
    a. Foydalanuvchiga to'plamga qo'shish imkonini beruvchi signUp nomli funksiya yarating. Agar foydalanuvchi mavjud bo'lsa, foydalanuvchiga uning allaqachon hisobi borligi haqida xabar bering.
    b. Foydalanuvchiga ilovaga kirish imkonini beruvchi signIn deb nomlangan funksiya yarating  

3. Mahsulotlar massivida uchta element mavjud va ularning har biri oltita xususiyatga ega.
    a. Mahsulotni baholaydigan rateProduct nomli funksiya yarating
    b. Mahsulotning o'rtacha reytingini hisoblaydigan o'rtachaRating funksiyasini yarating

4. LikeProduct deb nomlangan funksiya yarating. Bu funksiya mahsulot yoqmasa, uni yoqtirishga va yoqqan bo'lsa, o'chirishga yordam beradi.


🎉 TABRIKLAYMAN ! 🎉

[<< 7-kun](../07_Day_Functions/07_day_functions.md) | [9-kun >>](../09_Day_Higher_order_functions/09_day_higher_order_functions.md)
