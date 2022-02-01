<div align="center">
  <h1> 30 kunlik JavaScript: Destructuring and Spreading</h1>
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

[<< 10-kun](../10_Day_Sets_and_Maps/10_day_Sets_and_Maps.md) | [12-kun>>](../12_Day_Regular_expressions/12_day_regular_expressions.md)

![11-Kun](../images/banners/day_1_11.png)

- [11-Kun](#11-kun)
  - [Destructuring (Tarqatish) va Spread (Yig'ish)](#destructuring-tarqatish-va-spread-yigish)
    - [Massivlarni destruktizatsiyalash](#massivlarni-destruktizatsiyalash)
    - [Iteratsiya paytida massivni tarqatish](#iteratsiya-paytida-massivni-tarqatish)
    - [Ob'ektni destruktizatsiyalash](#obektni-destruktizatsiyalash)
    - [Strukturalash mobaynida qayta nomlash](#strukturalash-mobaynida-qayta-nomlash)
    - [Ob'ekt parametri destrukturalashsiz](#obekt-parametri-destrukturalashsiz)
    - [Ob'ekt parametri destrukturalash bilan](#obekt-parametri-destrukturalash-bilan)
    - [Iteratsiya paytida ob'ektni tarqatish](#iteratsiya-paytida-obektni-tarqatish)
    - [Spread va Rest Operatorlari](#spread-va-rest-operatorlari)
    - [Massivning qolgan elementlarini olish uchun Spread operatori](#massivning-qolgan-elementlarini-olish-uchun-spread-operatori)
    - [Massivni nusxalash uchun Spread operatori](#massivni-nusxalash-uchun-spread-operatori)
    - [Ob'ektni nusxalash uchun Spread operatori](#obektni-nusxalash-uchun-spread-operatori)
      - [Spread operatori strelkali funksiya bilan](#spread-operatori-strelkali-funksiya-bilan)
  - [Mashqlar](#mashqlar)
    - [Mashqlar: Level 1](#mashqlar-level-1)
    - [Mashqlar: Level 2](#mashqlar-level-2)
    - [Mashqlar: Level 3](#mashqlar-level-3)

# 11-Kun

## Destructuring (Tarqatish) va Spread (Yig'ish)

Destrukturizatsiya - massivlar va ob'ektlarni ochish va alohida o'zgaruvchiga belgilash usuli.

### Massivlarni destruktizatsiyalash

```js
  const numbers = [1, 2, 3]
  let [numOne, numTwo, numThree] = numbers

  console.log(numOne, numTwo, numThree)
```

```sh
  1 2 3
```

```js
  const names = ['Asabeneh', 'Brook', 'David', 'John']
  let [firstPerson, secondPerson, thirdPerson, fourthPerson] = names

  console.log(firstPerson, secondPerson,thirdPerson, fourthPerson)
```

```sh
Asabeneh Brook David John
```

```js
  const scientificConstants = [2.72, 3.14, 9.81, 37, 100]
  let [e, pi, gravity, bodyTemp, boilingTemp] = scientificConstants

  console.log(e,pi,gravity, bodyTemp, boilingTemp)
```

```sh
2.72 3.14 9.81 37 100
```

```js
const fullStack = [
  ['HTML', 'CSS', 'JS', 'React'],
  ['Node', 'Express', 'MongoDB']
]
const [frontEnd, backEnd] = fullStack

console.log(frontEnd)
console.log(backEnd)
```

```sh
["HTML", "CSS", "JS", "React"]
["Node", "Express", "MongoDB"]
```

Agar biz massivdagi qiymatlarni o'tkazib yubormoqchi bo'lsak, biz qo'shimcha verguldan foydalanamiz. Vergul o'sha maxsus indeksdagi qiymatni olib tashlashga yordam beradi

```js
  const numbers = [1, 2, 3]
  let [numOne, , numThree] = numbers // 2 o'tkazib yuborilgan 

  console.log(numOne, numThree)
```

```sh
1 3
```

```js
  const names = ['Asabeneh', 'Brook', 'David', 'John']
  let [, secondPerson, , fourthPerson] = name // birinchi va uchinchi shaxslar o'tkazib yuborilgan 

  console.log(secondPerson, fourthPerson)
```

```sh
Brook John
```

Agar ushbu indeks uchun massiv qiymati aniqlanmagan bo'lsa, biz standart qiymatdan foydalanishimiz mumkin:

```js
const names = [undefined, 'Brook', 'David']
let [
  firstPerson = 'Asabeneh',
  secondPerson,
  thirdPerson,
  fourthPerson = 'John'
] = names

console.log(firstPerson, secondPerson, thirdPerson, fourthPerson)  
```

```sh
Asabeneh Brook David John
```

Biz massivdagi barcha elementlarga o‘zgaruvchini tayinlay olmaymiz. Biz birinchisidan bir nechtasini yo'q qilishimiz mumkin, qolganini esa spread operatori (...) yordamida massiv sifatida olishimiz mumkin.

```js
const nums = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
let [num1, num2, num3, ...rest] = nums

console.log(num1, num2, num3)
console.log(rest)
```

```sh
1 2 3
[4, 5, 6, 7, 8, 9, 10]
```

### Iteratsiya paytida massivni tarqatish

```js
const countries = [['Finland', 'Helsinki'], ['Sweden', 'Stockholm'], ['Norway', 'Oslo']]

for (const [country, city] of countries) {
console.log(country, city)
}
```

```sh
Finland Helsinki
Sweden Stockholm
Norway Oslo
```

```js
const fullStack = [
  ['HTML', 'CSS', 'JS', 'React'],
  ['Node', 'Express', 'MongoDB']
]

for(const [first, second, third] of fullStack) {
console.log(first, second, third)
}
```

```sh
HTML CSS JS
Node Express MongoDB
```

### Ob'ektni destruktizatsiyalash

Biz tuzilmani buzganimizda, biz yo'q qilish uchun foydalanadigan o'zgaruvchining nomi ob'ektning kaliti yoki xususiyati bilan aynan bir xil bo'lishi kerak. Quyidagi misolga qarang.

```js
const rectangle = {
  width: 20,
  height: 10,
  area: 200
}
let { width, height, area, perimeter } = rectangle

console.log(width, height, area, perimeter)
```

```sh
20 10 200 undefined
```

### Strukturalash mobaynida qayta nomlash

```js
const rectangle = {
  width: 20,
  height: 10,
  area: 200
}
let { width: w, height: h, area: a, perimeter: p } = rectangle

console.log(w, h, a, p)
```

```sh
20 10 200 undefined
```

Agar kalit ob'ektda topilmasa, o'zgaruvchi undefined ga tayinlanadi. Agar kalit ob'ektda bo'lmasa, biz deklaratsiya paytida standart qiymatni berishimiz mumkin. Misolga qarang.

```js
const rectangle = {
  width: 20,
  height: 10,
  area: 200
}
let { width, height, area, perimeter = 60 } = rectangle

console.log(width, height, area, perimeter) //20 10 200 60
//Ob'ektni o'zgartirishga ruxsat bering: eni 30 ga va perimetri 80 ga
```

```js
const rectangle = {
  width: 30,
  height: 10,
  area: 200,
  perimeter: 80
}
let { width, height, area, perimeter = 60 } = rectangle
console.log(width, height, area, perimeter) //30 10 200 80
```

Funktsiya parametrlari sifatida kalitlarni destruksiya qilish. To'rtburchak ob'ektni oladigan va to'rtburchak perimetrini qaytaradigan funksiya yarataylik.

### Ob'ekt parametri destrukturalashsiz

```js
// destrukturalashsiz
const rect = {
  width: 20,
  height: 10
}
const calculatePerimeter = rectangle => {
  return 2 * (rectangle.width + rectangle.height)
}

console.log(calculatePerimeter(rect)) // 60
//destrukturizatsiya bilan
```

```js
//Boshqa bir misol 
const person = {
  firstName: 'Asabeneh',
  lastName: 'Yetayeh',
  age: 250,
  country: 'Finland',
  job: 'Instructor and Developer',
  skills: [
    'HTML',
    'CSS',
    'JavaScript',
    'React',
    'Redux',
    'Node',
    'MongoDB',
    'Python',
    'D3.js'
  ],
  languages: ['Amharic', 'English', 'Suomi(Finnish)']
}
// Keling destrukturalashsiz shaxs ob'ekti haqida ma'lumot beradigan funksiya yaratamiz

const getPersonInfo = obj => {
  const skills = obj.skills
  const formattedSkills = skills.slice(0, -1).join(', ')
  const languages = obj.languages
  const formattedLanguages = languages.slice(0, -1).join(', ')

  personInfo = `${obj.firstName} ${obj.lastName} lives in ${obj.country}. He is  ${
    obj.age
  } years old. He is an ${obj.job}. He teaches ${formattedSkills} and ${
    skills[skills.length - 1]
  }. He speaks ${formattedLanguages} and a little bit of ${languages[2]}.`

  return personInfo
}

console.log(getPersonInfo(person))
```

### Ob'ekt parametri destrukturalash bilan

```js

const calculatePerimeter = ({ width, height }) => {
  return 2 * (width + height)
}

console.log(calculatePerimeter(rect)) // 60
```

```js
// Keling destrukturalash bilan shaxs ob'ekti haqida ma'lumot beradigan funksiya yaratamiz
const getPersonInfo = ({
  firstName,
  lastName,
  age,
  country,
  job,
  skills,
  languages
}) => {
  const formattedSkills = skills.slice(0, -1).join(', ')
  const formattedLanguages = languages.slice(0, -1).join(', ')

  personInfo = `${firstName} ${lastName} lives in ${country}. He is ${age} years old. He is an ${job}. He teaches ${formattedSkills} and ${
    skills[skills.length - 1]
  }. He speaks ${formattedLanguages} and a little bit of ${languages[2]}.`

  return personInfo
}
console.log(getPersonInfo(person))
/*
Asabeneh Yetayeh lives in Finland. He is  200 years old. He is an Instructor and Developer. He teaches HTML, CSS, JavaScript, React, Redux, Node, MongoDB, Python and D3.js. He speaks Amharic, English and a little bit of Suomi(Finnish)
*/
```

### Iteratsiya paytida ob'ektni tarqatish

```js
const todoList = [
{
  task:'Prepare JS Test',
  time:'4/1/2022 8:30',
  completed:true
},
{
  task:'Give JS Test',
  time:'4/1/2022 10:00',
  completed:false
},
{
  task:'Assess Test Result',
  time:'4/1/2022 1:00',
  completed:false
}
]

for (const {task, time, completed} of todoList){
  console.log(task, time, completed)
}
```

```sh
Prepare JS Test 4/1/2022 8:30 true
Give JS Test 4/1/2022 10:00 false
Assess Test Result 4/1/2022 1:00 false
```

### Spread va Rest Operatorlari

Massivni yo'q qilganda, qolgan elementlarni massiv sifatida olish uchun tarqalish operatoridan (...) foydalanamiz. Bunga qo'shimcha ravishda biz arr elementlarini boshqa massivga yoyish uchun tarqalish operatoridan foydalanamiz.

### Massivning qolgan elementlarini olish uchun Spread operatori

```js
const nums = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
let [num1, num2, num3, ...rest] = nums
​
console.log(num1, num2, num3)
console.log(rest)
```

```sh
1 2 3
[4, 5, 6, 7, 8, 9, 10]
```

```js
const countries = [
  'Germany',
  'France',
  'Belgium',
  'Finland',
  'Sweden',
  'Norway',
  'Denmark',
  'Iceland'
]

let [gem, fra, , ...nordicCountries] = countries

console.log(gem)
console.log(fra)
console.log(nordicCountries)
```

```sh
Germany
France
["Finland", "Sweden", "Norway", "Denmark", "Iceland"]
```

### Massivni nusxalash uchun Spread operatori

```js
const evens = [0, 2, 4, 6, 8, 10]
const evenNumbers = [...evens]

const odds = [1, 3, 5, 7, 9]
const oddNumbers = [...odds]

const wholeNumbers = [...evens, ...odds]

console.log(evenNumbers)
console.log(oddNumbers)
console.log(wholeNumbers)


```

```sh
[0, 2, 4, 6, 8, 10]
[1, 3, 5, 7, 9]
[0, 2, 4, 6, 8, 10, 1, 3, 5, 7, 9]
```

```js
const frontEnd = ['HTML', 'CSS', 'JS', 'React']
const backEnd = ['Node', 'Express', 'MongoDB']
const fullStack = [...frontEnd, ...backEnd]

console.log(fullStack)
```

```sh
["HTML", "CSS", "JS", "React", "Node", "Express", "MongoDB"]
```

### Ob'ektni nusxalash uchun Spread operatori

Biz Spread operatori yordamida ob'ektni nusxalashimiz mumkin

```js
const user = {
  name:'Asabeneh',
  title:'Programmer',
  country:'Finland',
  city:'Helsinki'
}

const copiedUser = {...user}
console.log(copiedUser)
```

```sh
{name: "Asabeneh", title: "Programmer", country: "Finland", city: "Helsinki"}
```

Nusxa olish paytida ob'ektni tahrirlash yoki o'zgartirish

```js
const user = {
  name:'Asabeneh',
  title:'Programmer',
  country:'Finland',
  city:'Helsinki'
}

const copiedUser = {...user, title:'instructor'}
console.log(copiedUser)
```

```sh
{name: "Asabeneh", title: "instructor", country: "Finland", city: "Helsinki"}
```

#### Spread operatori strelkali funksiya bilan

Cheksiz ko'p argumentlarni oladigan o'q funksiyasini yozishni xohlaganimizda biz tarqalish operatoridan foydalanamiz. Parametr sifatida tarqalish operatoridan foydalansak, funktsiyani chaqirganimizda berilgan argument massivga o'zgaradi.

```js

const sumAllNums = (...args) => {
  console.log(args)
}

sumAllNums(1, 2, 3,4,5)

```

```sh
[1, 2, 3, 4, 5]

```

```js

const sumAllNums = (...args) => {
  let sum = 0
  for (const num of args){
    sum += num
  }
  return sum
  
}

console.log(sumAllNums(1, 2, 3,4,5))
```

```sh
15

```

🌕 Siz hozirgacha juda ko'p narsaga erishdingiz. Endi sizning JavaScript darajangiz o'rta darajada. Davom eting! Siz hozirgina 11-kun sinovlarini yakunladingiz va siz buyuklik sari 11 qadam oldindasiz. Endi miyangiz va mushaklaringiz uchun bir nechta mashqlarni bajaring.

## Mashqlar

### Mashqlar: Level 1

```js
const constants = [2.72, 3.14, 9.81, 37, 100]
const countries = ['Finland', 'Estonia', 'Sweden', 'Denmark', 'Norway']
const rectangle = {
  width: 20,
  height: 10,
  area: 200,
  perimeter: 60
}
const users = [
{
  name:'Brook',
  scores:75,
  skills:['HTM', 'CSS', 'JS'],
  age:16
},
{
  name:'Alex',
  scores:80,
  skills:['HTM', 'CSS', 'JS'],
  age:18
},
{
  name:'David',
  scores:75,
  skills:['HTM', 'CSS'],
  age:22
},
{
  name:'John',
  scores:85,
  skills:['HTML'],
  age:25
},
{
  name:'Sara',
  scores:95,
  skills:['HTM', 'CSS', 'JS'],
  age: 26
},
{
  name:'Martha',
  scores:80,
  skills:['HTM', 'CSS', 'JS'],
  age:18
},
{
  name:'Thomas',
  scores:90,
  skills:['HTM', 'CSS', 'JS'],
  age:20
}
]
```

1. E, pi, gravitatsiya, humanBodyTemp, waterBoilingTemp ga konstantalar massivining elementlarini destruksiya qiling va tayinlang.
2. fin, est, sw, den va na mamlakatlar massivi elementlarini destruksiya qilish va belgilash
3. To'rtburchak ob'ektni xossalari yoki kalitlari bo'yicha destruksiya qiling.

### Mashqlar: Level 2

1. Foydalanuvchilar massivi bo'ylab takrorlang va tuzilmani buzish yordamida ob'ektning barcha kalitlarini oling
2. Ikkitadan kam malakaga ega bo'lgan odamlarni toping


### Mashqlar: Level 3

1. Mamlakatlar ob'ektini yo'q qilish barcha mamlakatlarning nomi, poytaxti, aholisi va tillarini chop etish
2. Kichik dasturchi tuzilmasi o‘qish oson bo‘lmasligi mumkin bo‘lgan massivlar massivlarida talabaning nomi, ko‘nikmalari va ballarini tuzadi. Quyidagi massiv nomini nomlash, malakalar massivini ko‘nikmalarga, ballar massivini ballarga, JavaScript ballini jsScorega va reactScore o‘zgaruvchisi uchun React ballni bir qatorda o‘zgartiring.

  ```js
    const student = ['David', ['HTM', 'CSS', 'JS', 'React'], [98, 85, 90, 95]]
    console.log(name, skills, jsScore, reactScore)
  ```

  ```sh
  David (4) ["HTM", "CSS", "JS", "React"] 90 95
  ```

3. Massivni struktura obyektiga aylantira oladigan _**convertArrayToObject**_ funksiyasini yozing .
   
  ```js
      const students = [
          ['David', ['HTM', 'CSS', 'JS', 'React'], [98, 85, 90, 95]],
          ['John', ['HTM', 'CSS', 'JS', 'React'], [85, 80, 85, 80]]
        ]

      console.log(convertArrayToObject(students))
      [
        {
          name: 'David',
          skills: ['HTM','CSS','JS','React'],
          scores: [98,85,90,95]
        },
        {
          name: 'John',
          skills: ['HTM','CSS','JS','React'],
          scores: [85, 80,85,80]
        }
      ]
  ```

4. Talaba ob'ektini asl ob'ektni o'zgartirmasdan newStudent ga nusxalash. Yangi ob'ektga quyidagilarni qo'shing?

- Oldin mahorat to'plamlariga 8-darajali Bootstrap-ni qo'shing
- 9-darajali ekspressni orqa tomondagi mahorat to'plamlariga qo'shing
- Ma'lumotlar bazasi ko'nikmalar to'plamiga 8-darajali SQL qo'shing
- Ma'lumotlar fanlari bo'yicha ko'nikmalar to'plamlariga darajasiz SQL qo'shing

```js
    const student = {
      name: 'David',
      age: 25,
      skills: {
        frontEnd: [
          { skill: 'HTML', level: 10 },
          { skill: 'CSS', level: 8 },
          { skill: 'JS', level: 8 },
          { skill: 'React', level: 9 }
        ],
        backEnd: [
          { skill: 'Node',level: 7 },
          { skill: 'GraphQL', level: 8 },
        ],
        dataBase:[
          { skill: 'MongoDB', level: 7.5 },
        ],
        dataScience:['Python', 'R', 'D3.js']
      }
    }
  ```

  Nusxalangan ob'ekt chiqishi quyidagicha ko'rinishi kerak:

```js
    {
    name: 'David',
    age: 25,
    skills: {
      frontEnd: [
        {skill: 'HTML',level: 10},
        {skill: 'CSS',level: 8},
        {skill: 'JS',level: 8},
        {skill: 'React',level: 9},
        {skill: 'BootStrap',level: 8}
      ],
      backEnd: [
        {skill: 'Node',level: 7},
        {skill: 'GraphQL',level: 8},
        {skill: 'Express',level: 9}
      ],
      dataBase: [
        { skill: 'MongoDB',level: 7.5},
        { skill: 'SQL',level: 8}
      ],
      dataScience: ['Python','R','D3.js','SQL']
    }
  }

```
🎉 TABRIKLAYMAN ! 🎉

[<< 10-kun](../10_Day_Sets_and_Maps/10_day_Sets_and_Maps.md) | [12-kun >>](../12_Day_Regular_expressions/12_day_regular_expressions.md)