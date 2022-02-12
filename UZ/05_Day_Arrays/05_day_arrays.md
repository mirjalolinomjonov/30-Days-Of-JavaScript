<div align="center">
  <h1> JavaScript-ning 30 kuni: Arrays (Massivlar)</h1>
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

[<< 4-kun](../04_Day_Conditionals/04_day_conditionals.md) | [6-kun >>](../06_Day_Loops/06_day_loops.md)

![5-Kun](../images/banners/day_1_5.png)

- [📔 5-Kun](#-5-kun)
  - [Massivlar](#massiv)
    - [Bo'sh massivni qanday yaratish kerak](#bosh-massivni-qanday-yaratish-kerak)
    - [Qiymatlar bilan massivni qanday yaratish mumkin](#qiymatlar-bilan-massivni-qanday-yaratish-mumkin)
    - [Split yordamida massiv yaratish](#split-yordamida-massiv-yaratish)
    - [Indeks yordamida massiv elementlariga kirish](#indeks-yordamida-massiv-elementlariga-kirish)
    - [Massiv elementini o'zgartirish](#massiv-elementini-ozgartirish)
    - [Massivni manipulyatsiya qilish usullari](#massivni-manipulyatsiya-qilish-usullari)
      - [Massiv konstruktori](#massiv-konstruktori)
      - [To'ldirish bilan statik qiymatlarni yaratish](#toldirish-bilan-statik-qiymatlarni-yaratish)
      - [Concat yordamida massivni birlashtirish](#concat-yordamida-massivni-birlashtirish)
      - [Massiv uzunligini olish](#massiv-uzunligini-olish)
      - [arr massivida indeks elementini olish](#arr-massivida-indeks-elementini-olish)
      - [Massivdagi elementning oxirgi indeksini olish](#massivdagi-elementning-oxirgi-indeksini-olish)
      - [Massivni tekshirish](#massivni-tekshirish)
      - [Massivni satrga aylantirish](#massivni-satrga-aylantirish)
      - [Massiv elementlarini birlashtirish](#massiv-elementlarini-birlashtirish)
      - [Massiv elementlarini kesish](#massiv-elementlarini-kesish)
      - [Massivni tarkibini o'zgartirish usuli](#massivni-tarkibini-ozgartirish-usuli)
      - [Push yordamida massivga element qo'shish](#push-yordamida-massivga-element-qoshish)
      - [Pop yordamida oxirgi elementni olib tashlash](#pop-yordamida-oxirgi-elementni-olib-tashlash)
      - [Elementni boshidan olib tashlash](#elementni-boshidan-olib-tashlash)
      - [Elementni boshidan qo'shish](#elementni-boshidan-qoshish)
      - [Massiv tartibini teskari aylantirish](#massiv-tartibini-teskari-aylantirish)
      - [Massivdagi elementlarni saralash](#massivdagi-elementlarni-saralash)
    - [Massivlar massivi](#massivlar-massivi)
  - [💻 Mashq](#-mashq)
    - [Mashq: Level 1](#mashq-level-1)
    - [Mashq: Level 2](#mashq-level-2)
    - [Mashq: Level 3](#mashq-level-3)

# 📔 5-Kun

## Massivlar

O'zgaruvchilardan farqli o'laroq, massiv bir nechta qiymatlarni saqlashi mumkin . Massivdagi har bir qiymat indeksga ega va har bir indeks xotira manzilida mos yozuvlarga ega . Har bir qiymatga ularning indekslari yordamida kirish mumkin . Massiv indeksi noldan boshlanadi va oxirgi element indeksi massiv uzunligidan bittaga kichikdir.

Massiv - bu tartiblangan va o'zgartirilishi mumkin bo'lgan (o'zgartirilishi mumkin bo'lgan) turli xil ma'lumotlar to'plami. Massiv ikki nusxadagi elementlarni va turli xil ma'lumotlar turlarini saqlashga imkon beradi. Massiv bo'sh bo'lishi mumkin yoki u turli xil ma'lumotlar turi qiymatlariga ega bo'lishi mumkin.

### Bo'sh massivni qanday yaratish kerak

JavaScript-da biz massivni turli usullarda yaratishimiz mumkin. Keling, massivni yaratishning turli usullarini ko'rib chiqaylik. Massiv o'zgaruvchisini e'lon qilish uchun let o'rniga const dan foydalanish juda keng tarqalgan . Agar siz const dan foydalansangiz, bu o'zgaruvchi nomini boshqa ishlatmasligingizni anglatadi.

- Massiv konstruktoridan foydalanish

```js
// sintaksis
const arr = Array()
// yoki
// let arr = new Array()
console.log(arr) // []
```

- Kvadrat qavslardan foydalanish([])

```js
// sintaksis
// Bu bo'sh ro'yxat yaratishning eng tavsiya etilgan usuli 
const arr = []
console.log(arr)
```

### Qiymatlar bilan massivni qanday yaratish mumkin

Boshlang'ich qiymatlari bo'lgan massiv. Massiv uzunligini topish uchun biz length xususiyatidan foydalanamiz.

```js
const numbers = [0, 3.14, 9.81, 37, 98.6, 100] // raqamlar massivi
const fruits = ['banana', 'orange', 'mango', 'lemon'] // satrlar massivi, mevalar
const vegetables = ['Tomato', 'Potato', 'Cabbage', 'Onion', 'Carrot'] // satrlar massivi, sabzavotlar 
const animalProducts = ['milk', 'meat', 'butter', 'yoghurt'] // satrlar massivi, mahsulotlar
const webTechs = ['HTML', 'CSS', 'JS', 'React', 'Redux', 'Node', 'MongDB'] // web-texnologiyalar massivi
const countries = ['Finland', 'Denmark', 'Sweden', 'Norway', 'Iceland'] // satrlar massivi, mamlakatlar

// Massiv va uning uzunligini chop eting

console.log('Numbers:', numbers)
console.log('Number of numbers:', numbers.length)

console.log('Fruits:', fruits)
console.log('Number of fruits:', fruits.length)

console.log('Vegetables:', vegetables)
console.log('Number of vegetables:', vegetables.length)

console.log('Animal products:', animalProducts)
console.log('Number of animal products:', animalProducts.length)

console.log('Web technologies:', webTechs)
console.log('Number of web technologies:', webTechs.length)

console.log('Countries:', countries)
console.log('Number of countries:', countries.length)
```

```sh
Numbers: [0, 3.14, 9.81, 37, 98.6, 100]
Number of numbers: 6
Fruits: ['banana', 'orange', 'mango', 'lemon']
Number of fruits: 4
Vegetables: ['Tomato', 'Potato', 'Cabbage', 'Onion', 'Carrot']
Number of vegetables: 5
Animal products: ['milk', 'meat', 'butter', 'yoghurt']
Number of animal products: 4
Web technologies: ['HTML', 'CSS', 'JS', 'React', 'Redux', 'Node', 'MongDB']
Number of web technologies: 7
Countries: ['Finland', 'Estonia', 'Denmark', 'Sweden', 'Norway']
Number of countries: 5
```

- Massivda har xil turdagi ma'lumotlar bo'lishi mumkin

```js
const arr = [
    'Asabeneh',
    250,
    true,
    { country: 'Finland', city: 'Helsinki' },
    { skills: ['HTML', 'CSS', 'JS', 'React', 'Python'] }
] //  turli xil ma'lumotlar o'z ichiga olgan arr
console.log(arr)
```

### Split yordamida massiv yaratish

Avvalgi bo'limda ko'rganimizdek, biz satrni turli pozitsiyalarga bo'lishimiz va massivga o'zgartirishimiz mumkin. Keling, quyidagi misollarni ko'rib chiqaylik.

```js
let js = 'JavaScript'
const charsInJavaScript = js.split('')

console.log(charsInJavaScript) // ["J", "a", "v", "a", "S", "c", "r", "i", "p", "t"]

let companiesString = 'Facebook, Google, Microsoft, Apple, IBM, Oracle, Amazon'
const companies = companiesString.split(',')

console.log(companies) // ["Facebook", " Google", " Microsoft", " Apple", " IBM", " Oracle", " Amazon"]
let txt =
  'I love teaching and empowering people. I teach HTML, CSS, JS, React, Python.'
const words = txt.split(' ')

console.log(words)
// matnda faqat so'zlarni qanday qilib olish mumkinligini o'ylaydigan maxsus belgilar mavjud 
// ["I", "love", "teaching", "and", "empowering", "people.", "I", "teach", "HTML,", "CSS,", "JS,", "React,", "Python"]
```

### Indeks yordamida massiv elementlariga kirish

Biz massivdagi har bir elementga ularning indeksidan foydalanamiz. Massiv indeksi 0 dan boshlanadi. Quyidagi rasmda massivdagi har bir elementning indeksi aniq ko'rsatilgan.

![arr index](../images/array_index.png)

```js
const fruits = ['banana', 'orange', 'mango', 'lemon']
let firstFruit = fruits[0] // biz uning indeksidan foydalanib birinchi elementga kiramiz.

console.log(firstFruit) // banana

secondFruit = fruits[1]
console.log(secondFruit) // orange

let lastFruit = fruits[3]
console.log(lastFruit) // lemon
// Oxirgi indeksni quyidagicha hisoblash mumkin

let lastIndex = fruits.length - 1
lastFruit = fruits[lastIndex]

console.log(lastFruit)  // lemon
```

```js
const numbers = [0, 3.14, 9.81, 37, 98.6, 100]  // raqamlar toʻplami

console.log(numbers.length)  // => massiv hajmini bilish uchun, qaysi 6
console.log(numbers)         // -> [0, 3.14, 9.81, 37, 98.6, 100]
console.log(numbers[0])      //  -> 0
console.log(numbers[5])      //  -> 100

let lastIndex = numbers.length - 1;
console.log(numbers[lastIndex]) // -> 100
```

```js
const webTechs = [
  'HTML',
  'CSS',
  'JavaScript',
  'React',
  'Redux',
  'Node',
  'MongoDB'
] // Veb-texnologiyalar ro'yxati

console.log(webTechs)        // barcha massiv elementlari 
console.log(webTechs.length) // => massiv hajmini bilish uchun 7 ta 
console.log(webTechs[0])     //  -> HTML
console.log(webTechs[6])     //  -> MongoDB

let lastIndex = webTechs.length - 1
console.log(webTechs[lastIndex]) // -> MongoDB
```

```js
const countries = [
  'Albania',
  'Bolivia',
  'Canada',
  'Denmark',
  'Ethiopia',
  'Finland',
  'Germany',
  'Hungary',
  'Ireland',
  'Japan',
  'Kenya'
] // Davlatlar ro'yxati

console.log(countries)      // -> barcha mamlakatlar
console.log(countries[0])   //  -> Albania
console.log(countries[10])  //  -> Kenya

let lastIndex = countries.length - 1;
console.log(countries[lastIndex]) //  -> Kenya
```

```js
const shoppingCart = [
  'Milk',
  'Mango',
  'Tomato',
  'Potato',
  'Avocado',
  'Meat',
  'Eggs',
  'Sugar'
] // Oziq-ovqat mahsulotlari ro'yxati

console.log(shoppingCart) // -> barcha mahsulotlar
console.log(shoppingCart[0]) //  -> Milk
console.log(shoppingCart[7]) //  -> Sugar

let lastIndex = shoppingCart.length - 1;
console.log(shoppingCart[lastIndex]) //  -> Sugar
```

### Massiv elementini o'zgartirish

Massiv o'zgaruvchan (o'zgartirilishi mumkin). Massiv yaratilgandan so'ng, biz massiv elementlarining tarkibini o'zgartirishimiz mumkin.

```js
const numbers = [1, 2, 3, 4, 5]
numbers[0] = 10      // 0 indeksidagi 1 ni 10 
numbers[1] = 20      // indeks 1 dan 20 gacha

console.log(numbers) // [10, 20, 3, 4, 5]

const countries = [
  'Albania',
  'Bolivia',
  'Canada',
  'Denmark',
  'Ethiopia',
  'Finland',
  'Germany',
  'Hungary',
  'Ireland',
  'Japan',
  'Kenya'
]

countries[0] = 'Afghanistan'  // Albaniyani Afg'oniston bilan almashtirish
let lastIndex = countries.length - 1
countries[lastIndex] = 'Korea' // Keniya o'rniga Koreya

console.log(countries)
```

```sh
["Afghanistan", "Bolivia", "Canada", "Denmark", "Ethiopia", "Finland", "Germany", "Hungary", "Ireland", "Japan", "Korea"]
```

### Massivni manipulyatsiya qilish usullari

Massivni manipulyatsiya qilishning turli usullari mavjud. Massivlar bilan ishlashning mavjud usullaridan ba'zilari quyidagilardir:_Array, length, concat, indexOf, slice, splice, join, toString, includes, lastIndexOf, isArray, fill, push, pop, shift, unshift_

#### Massiv konstruktori

Array: massiv yaratish uchun.

```js
const arr = Array() // bo'sh massiv 
console.log(arr)

const eightEmptyValues = Array(8) // sakkizta bo'sh qiymat  konsolini yaratadi 
console.log(eightEmptyValues) // [bo'sh x 8]
```

#### To'ldirish bilan statik qiymatlarni yaratish

fill: massivning barcha elementlarini statik qiymat bilan to'ldiring

```js
const arr = Array() //  bo'sh massiv yaratish
console.log(arr)

const eightXvalues = Array(8).fill('X') // "X" qiymati bilan to'ldirilgan sakkizta element qiymatini yaratadi 
console.log(eightXvalues) // ['X', 'X','X','X','X','X','X','X']

const eight0values = Array(8).fill(0) // '0' qiymati bilan to'ldirilgan sakkizta element qiymatini yaratadi
console.log(eight0values) // [0, 0, 0, 0, 0, 0, 0, 0]

const four4values = Array(4).fill(4) //'4' qiymati bilan to'ldirilgan 4 element qiymatini yaratadi
console.log(four4values) // [4, 4, 4, 4]
```

#### Concat yordamida massivni birlashtirish

concat:Ikki massivni birlashtirish uchun.

```js
const firstList = [1, 2, 3]
const secondList = [4, 5, 6]
const thirdList = firstList.concat(secondList)

console.log(thirdList) // [1, 2, 3, 4, 5, 6]
```

```js
const fruits = ['banana', 'orange', 'mango', 'lemon']                 // mevalar 
const vegetables = ['Tomato', 'Potato', 'Cabbage', 'Onion', 'Carrot'] // sabzavot 
const fruitsAndVegetables = fruits.concat(vegetables)                 // ikkita massivni birlashtirish

console.log(fruitsAndVegetables)
```

```sh
["banana", "orange", "mango", "lemon", "Tomato", "Potato", "Cabbage", "Onion", "Carrot"]
```

#### Massiv uzunligini olish

Length:Massiv hajmini bilish uchun

```js
const numbers = [1, 2, 3, 4, 5]
console.log(numbers.length) // ->  5 - massivning o'lchami
```

#### arr massivida indeks elementini olish

indexOf:Massivda element mavjudligini tekshirish uchun. Agar u mavjud bo'lsa, u indeksni qaytaradi, aks holda u -1 ni qaytaradi.

```js
const numbers = [1, 2, 3, 4, 5]

console.log(numbers.indexOf(5)) // -> 4
console.log(numbers.indexOf(0)) // -> -1
console.log(numbers.indexOf(1)) // -> 0
console.log(numbers.indexOf(6)) // -> -1
```

Element massivda mavjudligini tekshiring.

- Ro'yxatdagi narsalarni tekshiring
  
```js
// massivda banan mavjudligini tekshiramiz

const fruits = ['banana', 'orange', 'mango', 'lemon']
let index = fruits.indexOf('banana')  // 0

if(index != -1){
   console.log('Bu meva massivda mavjud')  
} else {
    console.log('Bu meva massivda mavjud emas')
}
// Bu meva massivda mavjud

// biz bu yerda ternar operatori( shart ? true bo'lsa : false bo'lsa)dan ham foydalanishimiz mumkin
index != -1 ? console.log('This fruit does exist in the array'): console.log('This fruit does not exist in the array')

// Keling, massivda avakado mavjudligini tekshiramiz
let indexOfAvocado = fruits.indexOf('avocado')  // -1, agar element topilmasa indeks -1
if(indexOfAvocado!= -1){
   console.log('Bu meva massivda mavjud')  
} else {
    console.log('Bu meva massivda mavjud emas')
}
// Bu meva massivda mavjud emas
```

#### Massivdagi elementning oxirgi indeksini olish

lastIndexOf: Bu massivdagi oxirgi elementning o'rnini beradi. Agar mavjud bo'lsa, u indeksni qaytaradi, aks holda u -1 ni qaytaradi.

```js
const numbers = [1, 2, 3, 4, 5, 3, 1, 2]

console.log(numbers.lastIndexOf(2)) // 7
console.log(numbers.lastIndexOf(0)) // -1
console.log(numbers.lastIndexOf(1)) //  6
console.log(numbers.lastIndexOf(4)) //  3
console.log(numbers.lastIndexOf(6)) // -1
```

includes:Massivda element mavjudligini tekshirish uchun. Agar u mavjud bo'lsa, u rostni qaytaradi, aksincha, yolg'onni qaytaradi.

```js
const numbers = [1, 2, 3, 4, 5]

console.log(numbers.includes(5)) // true
console.log(numbers.includes(0)) // false
console.log(numbers.includes(1)) // true
console.log(numbers.includes(6)) // false

const webTechs = [
  'HTML',
  'CSS',
  'JavaScript',
  'React',
  'Redux',
  'Node',
  'MongoDB'
] // Veb-texnologiyalar 

console.log(webTechs.includes('Node'))  // true
console.log(webTechs.includes('C'))     // false
```

#### Massivni tekshirish

Array.isArray:Ma'lumotlar turi massiv ekanligini tekshirish uchun

```js
const numbers = [1, 2, 3, 4, 5]
console.log(Array.isArray(numbers)) // true

const number = 100
console.log(Array.isArray(number)) // false
```

#### Massivni satrga aylantirish

toString:Massivni satrga aylantiradi

```js
const numbers = [1, 2, 3, 4, 5]
console.log(numbers.toString()) // 1,2,3,4,5

const names = ['Asabeneh', 'Mathias', 'Elias', 'Brook']
console.log(names.toString()) // Asabeneh,Mathias,Elias,Brook
```

#### Massiv elementlarini birlashtirish

join: U massiv elementlarini birlashtirish uchun ishlatiladi, biz birlashtirish usulida o'tkazgan argument massivga qo'shiladi va satr sifatida qaytariladi. Odatiy bo'lib, u vergul bilan birlashtiriladi, lekin biz elementlar orasiga qo'shilishi mumkin bo'lgan turli qator parametrlarini o'tkazishimiz mumkin.

```js
const numbers = [1, 2, 3, 4, 5]
console.log(numbers.join()) // 1,2,3,4,5

const names = ['Asabeneh', 'Mathias', 'Elias', 'Brook']

console.log(names.join()) // Asabeneh,Mathias,Elias,Brook
console.log(names.join('')) //AsabenehMathiasEliasBrook
console.log(names.join(' ')) //Asabeneh Mathias Elias Brook
console.log(names.join(', ')) //Asabeneh, Mathias, Elias, Brook
console.log(names.join(' # ')) //Asabeneh # Mathias # Elias # Brook

const webTechs = [
  'HTML',
  'CSS',
  'JavaScript',
  'React',
  'Redux',
  'Node',
  'MongoDB'
] // Veb-texnologiyalar 

console.log(webTechs.join())       // "HTML,CSS,JavaScript,React,Redux,Node,MongoDB"
console.log(webTechs.join(' # '))  // "HTML # CSS # JavaScript # React # Redux # Node # MongoDB"
```

#### Massiv elementlarini kesish

Slice: diapazondagi bir nechta elementlarni kesish uchun. Bu ikkita parametrni oladi: boshlang'ich va tugatish pozitsiyasi. U yakuniy pozitsiyani o'z ichiga olmaydi.

```js
  const numbers = [1,2,3,4,5]

  console.log(numbers.slice()) // -> u barcha elementlarni nusxalab ko'chiradi
  console.log(numbers.slice(0)) // -> u barcha elementlarni nusxalab ko'chiradi
  console.log(numbers.slice(0, numbers.length)) // u barcha elementlarni nusxalab ko'chiradi
  console.log(numbers.slice(1,4)) // -> [2,3,4] // u yakuniy pozitsiyani o'z ichiga olmaydi
```

#### Massivni tarkibini o'zgartirish usuli

Splice: Bu uchta parametrni oladi: Boshlang'ich pozitsiyasi, olib tashlanadigan martalar soni va qo'shiladigan elementlar soni.

```js
  const numbers = [1, 2, 3, 4, 5]

  console.log(numbers.splice())                // -> barcha elementlarni olib tashlang

```

```js
  const numbers = [1, 2, 3, 4, 5]
  console.log(numbers.splice(0,1))            // birinchi elementni olib tashlang
```

```js
  const numbers = [1, 2, 3, 4, 5, 6];
  console.log(numbers.splice(3, 3, 7, 8, 9))  // -> [1, 2, 3, 7, 8, 9] // u uchta elementni olib tashlaydi va uchta elementni almashtiradi
```

#### Push yordamida massivga element qo'shish

Push: oxiriga element qo'shish. Mavjud massivning oxiriga element qo'shish uchun biz push usulidan foydalanamiz.

```js
// sintaksis
const arr  = ['item1', 'item2','item3']
arr.push('new item')

console.log(arr)
// ['item1', 'item2','item3','new item']
```

```js
const numbers = [1, 2, 3, 4, 5]
numbers.push(6)

console.log(numbers) // -> [1,2,3,4,5,6]

numbers.pop() // -> oxirdan bitta elementni olib tashlang
console.log(numbers) // -> [1,2,3,4,5]
```

```js
let fruits = ['banana', 'orange', 'mango', 'lemon']
fruits.push('apple')

console.log(fruits)    // ['banana', 'orange', 'mango', 'lemon', 'apple']

fruits.push('lime')
console.log(fruits)   // ['banana', 'orange', 'mango', 'lemon', 'apple', 'lime']
```

#### Pop yordamida oxirgi elementni olib tashlash

pop: Oxirgi elementni olib tashlash.

```js
const numbers = [1, 2, 3, 4, 5]
numbers.pop() // -> oxirgi bitta elementni olib tashlash

console.log(numbers) // -> [1,2,3,4]
```

#### Elementni boshidan olib tashlash

shift: Massiv boshidan bitta massiv elementini olib tashlash.

```js
const numbers = [1, 2, 3, 4, 5]
numbers.shift() // -> boshlang'ich bitta elementni olib tashlang

console.log(numbers) // -> [2,3,4,5]
```

#### Elementni boshidan qo'shish

unshift: Massiv elementini massiv boshiga qo‘shish.

```js
const numbers = [1, 2, 3, 4, 5]
numbers.unshift(0) // -> boshiga bitta element qo'shish

console.log(numbers) // -> [0,1,2,3,4,5]
```

#### Massiv tartibini teskari aylantirish

reverse: massiv tartibini teskari aylantiradi.

```js
const numbers = [1, 2, 3, 4, 5]
numbers.reverse() // -> teskari massiv tartibi 

console.log(numbers) // [5, 4, 3, 2, 1]

numbers.reverse()
console.log(numbers) // [1, 2, 3, 4, 5]
```

#### Massivdagi elementlarni saralash

sort: massiv elementlarini o'sish tartibida joylashtirish. Saralash qayta qo'ng'iroq qilish funksiyasini oladi, biz keyingi bo'limlarda qayta qo'ng'iroq qilish funksiyasi bilan tartiblashdan qanday foydalanishimizni ko'rib chiqamiz.

```js
const webTechs = [
  'HTML',
  'CSS',
  'JavaScript',
  'React',
  'Redux',
  'Node',
  'MongoDB'
]

webTechs.sort()
console.log(webTechs) // ["CSS", "HTML", "JavaScript", "MongoDB", "Node", "React", "Redux"]

webTechs.reverse() // tartiblashdan so'ng
console.log(webTechs) // ["Redux", "React", "Node", "MongoDB", "JavaScript", "HTML", "CSS"]
```

### Massivlar massivi

Massiv turli xil ma'lumotlar turlarini, shu jumladan massivning o'zini ham saqlashi mumkin. Keling, massivlar massivini yarataylik

```js
const firstNums = [1, 2, 3]
const secondNums = [1, 4, 9]

const arrayOfArray =  [[1, 2, 3], [1, 2, 3]]
console.log(arrayOfArray[0]) // [1, 2, 3]

 const frontEnd = ['HTML', 'CSS', 'JS', 'React', 'Redux']
 const backEnd = ['Node','Express', 'MongoDB']
 const fullStack = [frontEnd, backEnd]
 console.log(fullStack)   // [["HTML", "CSS", "JS", "React", "Redux"], ["Node", "Express", "MongoDB"]]
 console.log(fullStack.length)  // 2
 console.log(fullStack[0])  // ["HTML", "CSS", "JS", "React", "Redux"]
 console.log(fullStack[1]) // ["Node", "Express", "MongoDB"]
```

🌕  Siz tirishqoqsiz va siz allaqachon ko'p narsaga erishdingiz. Siz hozirgina 5 kunlik sinovlarni yakunladingiz va siz buyuklik sari 5 qadam oldindasiz. Endi miyangiz va mushaklaringiz uchun bir nechta mashqlarni bajaring.

## 💻 Mashq

### Mashq: Level 1

```js
const countries = [
  'Albania',
  'Bolivia',
  'Canada',
  'Denmark',
  'Ethiopia',
  'Finland',
  'Germany',
  'Hungary',
  'Ireland',
  'Japan',
  'Kenya'
]

const webTechs = [
  'HTML',
  'CSS',
  'JavaScript',
  'React',
  'Redux',
  'Node',
  'MongoDB'
]
```

1. Bo'sh _massivni_ e'lon qilish ;
2. Elementlar soni 5 dan ortiq bo'lgan massivni e'lon qiling
3. Massiv uzunligini toping
4. Massivning birinchi elementini, o'rta elementini va oxirgi elementini oling
5. mixedDataTypes deb nomlangan massivni e'lon qiling, massivga turli ma'lumotlar turlarini qo'ying va massiv uzunligini toping. Massiv hajmi 5 dan katta bo'lishi kerak
6. ItCompanies massiv oʻzgaruvchisi nomini eʼlon qiling va Facebook, Google, Microsoft, Apple, IBM, Oracle va Amazonning boshlangʻich qiymatlarini belgilang
7. _console.log()_ yordamida massivni chop eting
8. Massivdagi kompaniyalar sonini chop eting
9. Birinchi kompaniya, o'rta va oxirgi kompaniyani chop eting
10. Har bir kompaniyani chop eting
11. Har bir kompaniya nomini birma-bir bosh harfga o'zgartiring va ularni chop eting
12. Massivni jumla sifatida chop eting: Facebook, Google, Microsoft, Apple, IBM, Oracle va Amazon yirik IT kompaniyalari.
13. ItCompanies qatorida ma'lum bir kompaniya mavjudligini tekshiring. Agar u mavjud bo'lsa, kompaniyani qaytaring, aks holda kompaniya topilmaydi
14. Bir nechta "o" ga ega kompaniyalarni filtrlash usulisiz filtrlang
15. Sort () usuli yordamida massivni tartiblang
16. Reverse () usuli yordamida massivni teskari aylantiring
17. Massivdan dastlabki 3 ta kompaniyani ajratib oling
18. Massivdan oxirgi 3 ta kompaniyani ajratib oling
19. Massivdan o'rta IT kompaniyasini yoki kompaniyalarni ajratib oling
20. Birinchi IT kompaniyasini massivdan olib tashlang
21. O'rta IT kompaniyasini yoki kompaniyalarni massivdan olib tashlang
22. Massivdan oxirgi IT kompaniyasini olib tashlang
23. Barcha IT kompaniyalarini olib tashlang

### Mashq: Level 2

1. Alohida mamlakatlar.js faylini yarating va mamlakatlar massivini ushbu faylga saqlang, alohida web_techs.js faylini yarating va webTechs massivini ushbu faylga saqlang. main.js faylidagi ikkala faylga ham kiring
2. Avval barcha tinish belgilarini olib tashlang va qatorni massivga o'zgartiring va massivdagi so'zlar sonini hisoblang

    ```js
    let text =
    'I love teaching and empowering people. I teach HTML, CSS, JS, React, Python.'
    console.log(words)
    console.log(words.length)
    ```

    ```sh
    ["I", "love", "teaching", "and", "empowering", "people", "I", "teach", "HTML", "CSS", "JS", "React", "Python"]
  
    13
    ```

3. Quyidagi xarid qilish savatiga narsalarni qo'shing, olib tashlang, tahrirlang

    ```js
    const shoppingCart = ['Milk', 'Coffee', 'Tea', 'Honey']
    ```

   - Agar u hali qo'shilmagan bo'lsa, savatning boshiga "Go'sht" ni qo'shing
   - Savatingizga shakar qo'shing, agar u hali qo'shilmagan bo'lsa
   - Agar asalga allergiyangiz bo'lsa, "Asal" ni olib tashlang
   - Choyni "yashil choy" ga o'zgartiring
4. Mamlakatlarda massivda "Efiopiya" mavjudligini tekshiring, agar u mavjud bo'lsa, "ETHIOPIA" deb chop eting. Agar u mavjud bo'lmasa, mamlakatlar ro'yxatiga qo'shing.
5. WebTechs massivida massivda Sass mavjudligini tekshiring va agar u mavjud bo'lsa, "Sass - CSS-ga tayyorgarlik jarayoni" deb chop eting. Agar u mavjud bo'lmasa, massivga Sass qo'shing va massivni chop eting.
6. Quyidagi ikkita o'zgaruvchini birlashtiring va uni fullStack o'zgaruvchisida saqlang.

    ```js
    const frontEnd = ['HTML', 'CSS', 'JS', 'React', 'Redux']
    const backEnd = ['Node','Express', 'MongoDB']
  
    console.log(fullStack)
    ```

    ```sh
    ["HTML", "CSS", "JS", "React", "Redux", "Node", "Express", "MongoDB"]
    ```

### Mashq: Level 3

1. Quyida 10 nafar talaba yoshidagi massiv berilgan:

    ```js
    const ages = [19, 22, 19, 24, 20, 25, 26, 24, 25, 24]
    ```

    - Massivni tartiblang va minimal va maksimal yoshni toping
    - O'rtacha yoshni toping (bir o'rta element yoki ikkita o'rta element ikkiga bo'lingan)
    - O'rtacha yoshni toping (barcha elementlar elementlar soniga bo'lingan)
    - Yoshlar oralig'ini toping (maksimal minus min)
    - (min - o'rtacha) va (max - o'rtacha) qiymatini solishtiring, abs() usulidan foydalaning

2. [Mamlakatlar massivida](https://github.com/Asabeneh/30DaysOfJavaScript/tree/master/data/countries.js) birinchi o'nta mamlakatni kesib oling
3. [Mamlakatlar massivida](https://github.com/Asabeneh/30DaysOfJavaScript/tree/master/data/countries.js) o'rta davlat(lar)ni toping 
4. Mamlakatlar massivini, agar u juft bo'lsa, ikkita teng massivga ajrating. Agar mamlakatlar qatori juft bo'lmasa, birinchi yarmi uchun yana bir mamlakat.
  
🎉 TABRIKLAYMAN ! 🎉

[<< 4-kun](../04_Day_Conditionals/04_day_Conditionals.md) | [6-kun >>](../06_Day_Loops/06_day_loops.md)
