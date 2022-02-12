<div align="center">
  <h1> JavaScript-ning 30 kuni: JSON</h1>
  <a class="header-badge" target="_blank" href="https://www.linkedin.com/in/asabeneh/">
  <img src="https://img.shields.io/badge/style--5eba00.svg?label=LinkedIn&logo=linkedin&style=social">
  </a>


<sub>Author:
<a href="https://www.linkedin.com/in/asabeneh/" target="_blank">Asabeneh Yetayeh</a><br>
<small> January, 2022</small>
</sub>

</div>

[<< 15-kun](../15_Day_Classes/15_day_classes.md) | [17-kun >>](../17_Day_Web_storages/17_day_web_storages.md)

![Thirty Days Of JavaScript](../images/banners/day_1_16.png)

- [16-Kun](#16-kun)
  - [JSON](#json)
    - [JSON-ni JavaScript obyektiga aylantirish](#json-ni-javascript-obyektiga-aylantirish)
      - [JSON.parse()](#jsonparse)
    - [JSON.parse() bilan reviver funksiyasidan foydalanish](#jsonparse-bilan-reviver-funksiyasidan-foydalanish)
    - [Ob'ektni JSONga aylantirish](#obektni-jsonga-aylantirish)
    - [JSON.stringify bilan filtr massividan foydalanish](#using-a-filter-array-with-jsonstringify)
  - [Mashqlar](#mashqlar)
    - [Mashqlar Level 1](#mashqlar-level-1)
    - [Mashqlar Level 2](#mashqlar-level-2)
    - [Mashqlar Level 3](#mashqlar-level-3)

# 16-Kun

## JSON

JSON JavaScript Object Notation degan ma'noni anglatadi. JSON sintaksisi JavaScript ob'ekt belgilari sintaksisidan olingan, ammo JSON formati faqat matn yoki satrdir. JSON saqlash va tashish uchun engil vaznli ma'lumotlar formatidir. JSON asosan serverdan mijozga maʼlumotlar yuborilganda ishlatiladi. JSON - bu XML ga ishlatish uchun qulay muqobil.

**Misol:**

```js
{
"users":[
  {
    "firstName":"Asabeneh",
    "lastName":"Yetayeh",
    "age":250,
    "email":"asab@asb.com"
  },
  {
    "firstName":"Alex",
    "lastName":"James",
    "age":25,
    "email":"alex@alex.com"
  },
  {
  "firstName":"Lidiya",
  "lastName":"Tekle",
  "age":28,
  "email":"lidiya@lidiya.com"
  }
]
}
```

Yuqoridagi JSON misoli oddiy ob'ekt uchun unchalik farq qilmaydi. Xo'sh, qanday farq bor? Farqi shundaki, JSON ob'ektining kaliti qo'sh tirnoqli bo'lishi kerak yoki u satr bo'lishi kerak. JavaScript Ob'ekti va JSON juda o'xshash, biz JSONni Ob'ektga va Ob'ektni JSONga o'zgartirishimiz mumkin.

Keling, yuqoridagi misolni batafsil ko'rib chiqaylik, u jingalak qavs bilan boshlanadi. Jingalak qavs ichida qiymatlar qatoriga ega bo'lgan "foydalanuvchilar" tugmasi mavjud. Massiv ichida bizda turli xil ob'ektlar bor va har bir ob'ektda kalitlar mavjud, har bir kalitda qo'sh tirnoq bo'lishi kerak. Misol uchun, biz faqat firstName o'rniga "firstNaMe" dan foydalanamiz, lekin ob'ektda biz qo'sh tirnoqsiz kalitlardan foydalanamiz. Bu ob'ekt va JSON o'rtasidagi asosiy farq. 
Keling, JSON haqida ko'proq misollarni ko'rib chiqaylik.

**Misol:**

```js
{
    "Alex": {
        "email": "alex@alex.com",
        "skills": [
            "HTML",
            "CSS",
            "JavaScript"
        ],
        "age": 20,
        "isLoggedIn": false,
        "points": 30
    },
    "Asab": {
        "email": "asab@asab.com",
        "skills": [
            "HTML",
            "CSS",
            "JavaScript",
            "Redux",
            "MongoDB",
            "Express",
            "React",
            "Node"
        ],
        "age": 25,
        "isLoggedIn": false,
        "points": 50
    },
    "Brook": {
        "email": "daniel@daniel.com",
        "skills": [
            "HTML",
            "CSS",
            "JavaScript",
            "React",
            "Redux"
        ],
        "age": 30,
        "isLoggedIn": true,
        "points": 50
    },
    "Daniel": {
        "email": "daniel@alex.com",
        "skills": [
            "HTML",
            "CSS",
            "JavaScript",
            "Python"
        ],
        "age": 20,
        "isLoggedIn": false,
        "points": 40
    },
    "John": {
        "email": "john@john.com",
        "skills": [
            "HTML",
            "CSS",
            "JavaScript",
            "React",
            "Redux",
            "Node.js"
        ],
        "age": 20,
        "isLoggedIn": true,
        "points": 50
    },
    "Thomas": {
        "email": "thomas@thomas.com",
        "skills": [
            "HTML",
            "CSS",
            "JavaScript",
            "React"
        ],
        "age": 20,
        "isLoggedIn": false,
        "points": 40
    },
    "Paul": {
        "email": "paul@paul.com",
        "skills": [
            "HTML",
            "CSS",
            "JavaScript",
            "MongoDB",
            "Express",
            "React",
            "Node"
        ],
        "age": 20,
        "isLoggedIn": false,
        "points": 40
    }
}
```

### JSON-ni JavaScript obyektiga aylantirish

Ko'pincha biz JSON ma'lumotlarini HTTP javobidan yoki fayldan olamiz, lekin biz JSONni satr sifatida saqlashimiz va namoyish qilish uchun Ob'ektga o'zgartirishimiz mumkin. JavaScript-da JSON kalit so'zida parse () va stringify() usullari mavjud. JSONni ob'ektga o'zgartirmoqchi bo'lganimizda, biz JSONni JSON.parse() yordamida tahlil qilamiz . Ob'ektni JSONga o'zgartirmoqchi bo'lganimizda biz JSON.stringify() dan foydalanamiz .

#### JSON.parse()

```js
JSON.parse(json[, reviver])
// json or text , the data
// reviver is an optional callback function
```

```js
const usersText = `{
"users":[
  {
    "firstName":"Asabeneh",
    "lastName":"Yetayeh",
    "age":250,
    "email":"asab@asb.com"
  },
  {
    "firstName":"Alex",
    "lastName":"James",
    "age":25,
    "email":"alex@alex.com"
  },
  {
  "firstName":"Lidiya",
  "lastName":"Tekle",
  "age":28,
  "email":"lidiya@lidiya.com"
  }
]
}`

const usersObj = JSON.parse(usersText, undefined, 4)
console.log(usersObj)
```

### JSON.parse() bilan reviver funksiyasidan foydalanish

Reviver funktsiyasidan formatlovchi sifatida foydalanish uchun biz ism va familiya qiymatini formatlashni xohlagan kalitlarni qo'yamiz. Aytaylik, biz JSON ma'lumotlarining ismi va familiyasini formatlashdan manfaatdormiz.

```js
const usersText = `{
"users":[
  {
    "firstName":"Asabeneh",
    "lastName":"Yetayeh",
    "age":250,
    "email":"asab@asb.com"
  },
  {
    "firstName":"Alex",
    "lastName":"James",
    "age":25,
    "email":"alex@alex.com"
  },
  {
  "firstName":"Lidiya",
  "lastName":"Tekle",
  "age":28,
  "email":"lidiya@lidiya.com"
  }
]
}`

const usersObj = JSON.parse(usersText, (key, value) => {
  let newValue =
    typeof value == 'string' && key != 'email' ? value.toUpperCase() : value
  return newValue
})
console.log(usersObj)
```

_JSON.parse ()_ dan foydalanish juda qulay. Siz ixtiyoriy parametrdan o'tishingiz shart emas, uni faqat kerakli parametr bilan ishlatishingiz mumkin va siz juda ko'p narsaga erishasiz.

### Ob'ektni JSONga aylantirish

Ob'ektni JSONga o'zgartirmoqchi bo'lganimizda biz _JSON.stringify()_ dan foydalanamiz . Stringify usuli bitta talab qilinadigan parametr va ikkita ixtiyoriy parametrni oladi. O'zgartirish moslamasi filtr sifatida ishlatiladi va bo'sh joy - chuqurchalar. Agar biz ob'ektdan biron bir kalitni filtrlashni istamasak, biz aniqlanmagan holda o'tishimiz mumkin.

```js
JSON.stringify(obj, replacer, space)
// json or text , the data
// reviver is an optional callback function
```

Keling, quyidagi ob'ektni satrga aylantiramiz. Avval foydalanishga ruxsat bering, barcha kalitlarni saqlab qo'ying va bizda 4 ta bo'sh joy bo'lsin.

```js
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
    skills: [
      'HTML',
      'CSS',
      'JavaScript',
      'Redux',
      'MongoDB',
      'Express',
      'React',
      'Node'
    ],
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
    skills: [
      'HTML',
      'CSS',
      'JavaScript',
      'MongoDB',
      'Express',
      'React',
      'Node'
    ],
    age: 20,
    isLoggedIn: false,
    points: 40
  }
}

const txt = JSON.stringify(users, undefined, 4)
console.log(txt) // matn JSON- degan ma'noni anglatadi, chunki json ob'ektning satr shaklidir.
```

```sh
{
    "Alex": {
        "email": "alex@alex.com",
        "skills": [
            "HTML",
            "CSS",
            "JavaScript"
        ],
        "age": 20,
        "isLoggedIn": false,
        "points": 30
    },
    "Asab": {
        "email": "asab@asab.com",
        "skills": [
            "HTML",
            "CSS",
            "JavaScript",
            "Redux",
            "MongoDB",
            "Express",
            "React",
            "Node"
        ],
        "age": 25,
        "isLoggedIn": false,
        "points": 50
    },
    "Brook": {
        "email": "daniel@daniel.com",
        "skills": [
            "HTML",
            "CSS",
            "JavaScript",
            "React",
            "Redux"
        ],
        "age": 30,
        "isLoggedIn": true,
        "points": 50
    },
    "Daniel": {
        "email": "daniel@alex.com",
        "skills": [
            "HTML",
            "CSS",
            "JavaScript",
            "Python"
        ],
        "age": 20,
        "isLoggedIn": false,
        "points": 40
    },
    "John": {
        "email": "john@john.com",
        "skills": [
            "HTML",
            "CSS",
            "JavaScript",
            "React",
            "Redux",
            "Node.js"
        ],
        "age": 20,
        "isLoggedIn": true,
        "points": 50
    },
    "Thomas": {
        "email": "thomas@thomas.com",
        "skills": [
            "HTML",
            "CSS",
            "JavaScript",
            "React"
        ],
        "age": 20,
        "isLoggedIn": false,
        "points": 40
    },
    "Paul": {
        "email": "paul@paul.com",
        "skills": [
            "HTML",
            "CSS",
            "JavaScript",
            "MongoDB",
            "Express",
            "React",
            "Node"
        ],
        "age": 20,
        "isLoggedIn": false,
        "points": 40
    }
}
```

### JSON.stringify bilan filtr massividan foydalanish

Keling, almashtirgichni filtr sifatida ishlatamiz. Foydalanuvchi ob'ektida kalitlarning uzoq ro'yxati mavjud, ammo biz ulardan faqat bir nechtasi bilan qiziqamiz. Biz saqlamoqchi bo'lgan kalitlarni misolda ko'rsatilganidek, massivga joylashtiramiz va uni almashtiruvchi o'rniga ishlatamiz.

```js
const user = {
  firstName: 'Asabeneh',
  lastName: 'Yetayeh',
  country: 'Finland',
  city: 'Helsinki',
  email: 'alex@alex.com',
  skills: ['HTML', 'CSS', 'JavaScript', 'React', 'Pyhton'],
  age: 250,
  isLoggedIn: false,
  points: 30
}

const txt = JSON.stringify(user,['firstName', 'lastName', 'country', 'city', 'age'],4)
console.log(txt)
```

```sh
{
    "firstName": "Asabeneh",
    "lastName": "Yetayeh",
    "country": "Finland",
    "city": "Helsinki",
    "age": 250
}
```

🌕 Siz g'ayrioddiysiz. Endi siz ma'lumotlarni saqlash yoki HTTP serverini yuborish uchun foydalanishingiz mumkin bo'lgan engil ma'lumotlar formatini bildingiz. Siz buyuklik sari 16 qadam oldindasiz. Endi miyangiz va mushaklaringiz uchun bir nechta mashqlarni bajaring.

## Mashqlar

```js
const skills = ['HTML', 'CSS', 'JS', 'React','Node', 'Python']
let age = 250;
let isMarried = true
const student = {
  firstName:'Asabeneh',
  lastName:'Yetayehe',
  age:250,
  isMarried:true,
  skills:['HTML', 'CSS', 'JS', 'React','Node', 'Python', ]
}
const txt = `{
    "Alex": {
        "email": "alex@alex.com",
        "skills": [
            "HTML",
            "CSS",
            "JavaScript"
        ],
        "age": 20,
        "isLoggedIn": false,
        "points": 30
    },
    "Asab": {
        "email": "asab@asab.com",
        "skills": [
            "HTML",
            "CSS",
            "JavaScript",
            "Redux",
            "MongoDB",
            "Express",
            "React",
            "Node"
        ],
        "age": 25,
        "isLoggedIn": false,
        "points": 50
    },
    "Brook": {
        "email": "daniel@daniel.com",
        "skills": [
            "HTML",
            "CSS",
            "JavaScript",
            "React",
            "Redux"
        ],
        "age": 30,
        "isLoggedIn": true,
        "points": 50
    },
    "Daniel": {
        "email": "daniel@alex.com",
        "skills": [
            "HTML",
            "CSS",
            "JavaScript",
            "Python"
        ],
        "age": 20,
        "isLoggedIn": false,
        "points": 40
    },
    "John": {
        "email": "john@john.com",
        "skills": [
            "HTML",
            "CSS",
            "JavaScript",
            "React",
            "Redux",
            "Node.js"
        ],
        "age": 20,
        "isLoggedIn": true,
        "points": 50
    },
    "Thomas": {
        "email": "thomas@thomas.com",
        "skills": [
            "HTML",
            "CSS",
            "JavaScript",
            "React"
        ],
        "age": 20,
        "isLoggedIn": false,
        "points": 40
    },
    "Paul": {
        "email": "paul@paul.com",
        "skills": [
            "HTML",
            "CSS",
            "JavaScript",
            "MongoDB",
            "Express",
            "React",
            "Node"
        ],
        "age": 20,
        "isLoggedIn": false,
        "points": 40
    }
}
`
```

### Mashqlar Level 1

1. JSON.stringify() yordamida ko'nikmalar massivini JSONga o'zgartiring

1. Yosh o'zgaruvchisini belgilang

1. isMarried o'zgaruvchisini chiziqqa aylantiring
   
1. Talaba ob'ektini chiziqlash

### Mashqlar Level 2

1. Talabalar ob'ektini faqat birinchi ism, familiya va ko'nikmalar xususiyatlari bilan ajratib oling

### Mashqlar Level 3

1. Ob'ekt uchun *txt* JSON faylini tahlil qiling.
2. _txt_ da saqlangan o'zgaruvchidan ko'plab ko'nikmalarga ega foydalanuvchini toping .

🎉 TABRIKLAYMAN ! 🎉

[<< 15-kun](../15_Day_Classes/15_day_classes.md) | [17-kun >>](../17_Day_Web_storages/17_day_web_storages.md)
