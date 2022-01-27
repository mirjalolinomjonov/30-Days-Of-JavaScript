<div align="center">
  <h1> 30 kunlik JavaScript:Yuqori tartibli funktsiyalar</h1>
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

[<< 8-kun](../08_Day_Objects/08_day_objects.md) | [10-kun >>](../10_Day_Sets_and_Maps/10_day_Sets_and_Maps.md)

![9-Kun](../images/banners/day_1_9.png)

- [9-Kun](#9-kun)
  - [Yuqori tartibli funktsiya](#yuqori-tartibli-funktsiya)
    - [Callback (Chaqiruv)](#callback-chaqiruv)
    - [Qaytish funktsiyasi](#qaytish-funktsiyasi)
    - [vaqtni sozlash](#vaqtni-sozlash)
      - [setInterval](#setinterval)
      - [setTimeout](#settimeout)
  - [Funktsional dasturlash](#funktsional-dasturlash)
    - [forEach](#foreach)
    - [map](#map)
    - [filter](#filter)
    - [reduce](#reduce)
    - [every](#every)
    - [find](#find)
    - [findIndex](#findindex)
    - [some](#some)
    - [sort](#sort)
      - [Satr qiymatlarini saralash](#satr-qiymatlarini-saralash)
      - [Raqamli qiymatlarni saralash](#raqamli-qiymatlarni-saralash)
      - [Obyektli massivlarni saralash](#obyektli-massivlarni-saralash)
  - [💻 Mashqlar](#-mashqlar)
    - [Mashqlar: Level 1](#mashqlar-level-1)
    - [Mashqlar: Level 2](#mashqlar-level-2)
    - [Mashqlar: Level 3](#mashqlar-level-3)

# 9-Kun

## Yuqori tartibli funktsiya

Yuqori tartibli funksiyalar(Higher order functions - `HOF` deb aytiladi) boshqa funksiyani parametr sifatida qabul qiladigan yoki funktsiyani qiymat sifatida qaytaradigan funksiyalardir. Parametr sifatida berilgan funksiya qayta qo'ng'iroq deb ataladi.

### Callback (Chaqiruv)

Callback (Chaqiruv) ya'ni `callback` - bu boshqa funktsiyaga parametr sifatida o'tkazilishi mumkin bo'lgan funksiya. Quyidagi misolga qarang.

```js
// a callback function, funksiya ixtiyoriy nomlanishi mumkin
const callback = (n) => {
  return n ** 2
}
​
// funksiya bu yerda callback sifatida boshqa bir funksiyani parametr sifatida qabul qilib turibdi
function cube(callback, n) {
  return callback(n) * n
}
​
console.log(cube(callback, 3))
```

### Qaytish funktsiyasi

Higher order funksiyalarari qiymat sifatida funksiya qaytaradi
​

```js
// Higher order funksiyasi boshqa bir funksiyani qaytarayapti
const higherOrder = n => {
  const doSomething = m => {
    const doWhatEver = t => {
      return 2 * n + 3 * m + t
    }
    return doWhatEver
  }
  return doSomething
}
console.log(higherOrder(2)(3)(10))
```

Callback funksiyalaridan foydalanganimizni ko'rib chiqaylik. Masalan, _**forEach**_ methodi qayta `callback`dan foydalanadi.

```js
const numbers = [1, 2, 3, 4]
​
const sumArray = arr => {
  let sum = 0
  const callback = function(element) {
    sum += element
  }
  arr.forEach(callback)
  return sum

}
console.log(sumArray(numbers))
```

```sh
15
```

Yuqoridagi misolni quyidagicha soddalashtirish mumkin:

```js
const numbers = [1, 2, 3, 4]
​
const sumArray = arr => {
  let sum = 0
  arr.forEach(function(element) {
    sum += element
  })
  return sum

}
console.log(sumArray(numbers))
```

```sh
15
```

### Vaqtni sozlash

JavaScript-da biz ba'zi harakatlarni ma'lum vaqt oralig'ida bajarishimiz yoki ba'zi harakatlarni bajarish uchun biroz vaqt rejalashtirishimiz (kutishimiz) mumkin.

- setInterval
- setTimeout

#### SetInterval funksiyasi yordamida Interavalni o'rnatish

JavaScript-da biz ma'lum vaqt oralig'ida doimiy ravishda ba'zi harakatlarni bajarish uchun setInterval yuqori tartibli funksiyasidan foydalanamiz. setInterval global usuli parametr sifatida qayta qo'ng'iroq qilish funktsiyasi va davomiylikni oladi. Davomiylik millisekundlarda va qayta qo'ng'iroq har doim shu vaqt oralig'ida chaqiriladi.

```js
// syntax
function callback() {
  // code goes here
}
setInterval(callback, duration)
```

```js
function sayHello() {
  console.log('Hello')
}
setInterval(sayHello, 1000) // u har soniyada 'Hello' chop etadi, 1000ms = 1sekund
```

#### SetTimeout yordamida vaqtni belgilash

JavaScript-da biz kelajakda biron bir amalni bajarish uchun setTimeout yuqori tartibli funksiyasidan foydalanamiz. setTimeout global usuli parametr sifatida `callback` funktsiyasi va davomiylikni oladi. Davomiylik millisekundlarda va `callback` shu vaqtni kutadi.

```js
// syntax
function callback() {
  // code goes here
}
setTimeout(callback, duration) // duration(davomiyligi) millisekundlarda
```

```js
function sayHello() {
  console.log('Hello')
}
setTimeout(sayHello, 2000) // u 2 soniya kutgandan so'ng 'Hello' chop etadi.
```

## Funktsional dasturlash

Oddiy tsiklni yozish o'rniga, JavaScript-ning so'nggi versiyasi bizga murakkab muammolarni hal qilishda yordam beradigan ko'plab o'rnatilgan usullarni taqdim etdi. Barcha o'rnatilgan usullar qayta qo'ng'iroq qilish funktsiyasini oladi. Ushbu bo'limda biz _forEach_ , _map_ , _filter_ , _kamaytirish_ , _find_ , _every_ , _some_ , va _sort_ ni ko'rib chiqamiz .

### forEach

_forEach_: massiv elementlarini takrorlash. Biz forEach dan faqat massivlar bilan foydalanamiz. U elementlar, indeks parametri va massivning o'zi bilan qayta qo'ng'iroq qilish funktsiyasini oladi. Indeks va massiv ixtiyoriy.

```js
arr.forEach(function (element, index, arr) {
  console.log(index, element, arr)
})
// Yuqoridagi kodni o'q funktsiyasi yordamida yozish mumkin
arr.forEach((element, index, arr) => {
  console.log(index, element, arr)
})
// Yuqoridagi kod o'q funktsiyasi va aniq qaytish yordamida yozilishi mumkin
arr.forEach((element, index, arr) => console.log(index, element, arr))
```

```js
let sum = 0;
const numbers = [1, 2, 3, 4, 5];
numbers.forEach(num => console.log(num))
console.log(sum)
```

```sh
1
2
3
4
5
```

```js
let sum = 0;
const numbers = [1, 2, 3, 4, 5];
numbers.forEach(num => sum += num)

console.log(sum)
```

```sh
15
```

```js
const countries = ['Finland', 'Denmark', 'Sweden', 'Norway', 'Iceland']
countries.forEach((element) => console.log(element.toUpperCase()))
```

```sh
FINLAND
DENMARK
SWEDEN
NORWAY
ICELAND
```

### map

_map_: massiv elementlarini takrorlash va massiv elementlarini o‘zgartirish. U elementlar, indeks, massiv parametrlari bilan qayta qo'ng'iroq qilish funktsiyasini oladi va yangi massivni qaytaradi.

```js
const modifiedArray = arr.map(function (element, index, arr) {
  return element
})
```

```js
/* Strelkali funksiya return yozmagan holda
const modifiedArray = arr.map((element,index) => element);
*/
//Misol
const numbers = [1, 2, 3, 4, 5]
const numbersSquare = numbers.map((num) => num * num)

console.log(numbersSquare)
```

```sh
[1, 4, 9, 16, 25]
```

```js
const names = ['Asabeneh', 'Mathias', 'Elias', 'Brook']
const namesToUpperCase = names.map((name) => name.toUpperCase())
console.log(namesToUpperCase)
```

```sh
['ASABENEH', 'MATHIAS', 'ELIAS', 'BROOK']
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
  'Kenya',
]
const countriesToUpperCase = countries.map((country) => country.toUpperCase())
console.log(countriesToUpperCase)

/*
// Strelkali funksiya
const countriesToUpperCase = countries.map((country) => {
  return country.toUpperCase();
})
// Strelkali funksiya return yozmagan holda
const countriesToUpperCase = countries.map(country => country.toUpperCase());
*/
```

```sh
['ALBANIA', 'BOLIVIA', 'CANADA', 'DENMARK', 'ETHIOPIA', 'FINLAND', 'GERMANY', 'HUNGARY', 'IRELAND', 'JAPAN', 'KENYA']
```

```js
const countriesFirstThreeLetters = countries.map((country) =>
  country.toUpperCase().slice(0, 3)
)
```

```sh
 ["ALB", "BOL", "CAN", "DEN", "ETH", "FIN", "GER", "HUN", "IRE", "JAP", "KEN"]
```

### filter

_Filter_: Filtrlash shartlarini to'liq to'ldiradigan elementlarni filtrlang va yangi massivni qaytaring.

```js
//Filter countries containing land
const countriesContainingLand = countries.filter((country) =>
  country.includes('land')
)
console.log(countriesContainingLand)
```

```sh
['Finland', 'Ireland']
```

```js
const countriesEndsByia = countries.filter((country) => country.endsWith('ia'))
console.log(countriesEndsByia)
```

```sh
['Albania', 'Bolivia','Ethiopia']
```

```js
const countriesHaveFiveLetters = countries.filter(
  (country) => country.length === 5
)
console.log(countriesHaveFiveLetters)
```

```sh
['Japan', 'Kenya']
```

```js
const scores = [
  { name: 'Asabeneh', score: 95 },
   { name: 'Lidiya', score: 98 },
  { name: 'Mathias', score: 80 },
  { name: 'Elias', score: 50 },
  { name: 'Martha', score: 85 },
  { name: 'John', score: 100 },
]

const scoresGreaterEight = scores.filter((score) => score.score > 80)
console.log(scoresGreaterEight)
```

```sh
[{name: 'Asabeneh', score: 95}, { name: 'Lidiya', score: 98 },{name: 'Martha', score: 85},{name: 'John', score: 100}]
```

### reduce

_reduce_: Reduction qayta qo'ng'iroq qilish funksiyasini oladi. Qayta qo'ng'iroq qilish funksiyasi parametr sifatida akkumulyator, joriy va ixtiyoriy boshlang'ich qiymatni oladi va bitta qiymatni qaytaradi. Akkumulyator qiymatining dastlabki qiymatini aniqlash yaxshi amaliyotdir. Agar biz ushbu parametrni aniqlamasak, sukut bo'yicha akkumulyator massivni oladi `first value`. Agar bizning massivimiz _bo'sh massiv_ bo'lsa, u `Javascript`holda xatoga yo'l qo'yadi.

```js
arr.reduce((acc, cur) => {
  // qiymatni qaytarishdan oldin ba'zi operatsiyalar shu yerda amalga oshiriladi
 return 
}, initialValue)
```

```js
const numbers = [1, 2, 3, 4, 5]
const sum = numbers.reduce((acc, cur) => acc + cur, 0)

console.log(sum)
```

```js
15
```

### every

_every_: Barcha elementlarning bir jihatda oʻxshashligini tekshiring. Bu booleanni qaytaradi

```js
const names = ['Asabeneh', 'Mathias', 'Elias', 'Brook']
const areAllStr = names.every((name) => typeof name === 'string') // Are all strings?

console.log(arrAllStr)
```

```sh
true
```

```js
const bools = [true, true, true, true]
const areAllTrue = bools.every((b) => b === true) // Hammasi rostmi?

console.log(areAllTrue) // rost
```

```sh
true

```

### find

_find_: Shartni qondiradigan birinchi elementni qaytaring

```js
const ages = [24, 22, 25, 32, 35, 18]
const age = ages.find((age) => age < 20)

console.log(age)
```

```js
18
```

```js
const names = ['Asabeneh', 'Mathias', 'Elias', 'Brook']
const result = names.find((name) => name.length > 7)
console.log(result)
```

```sh
Asabeneh
```

```js
const scores = [
  { name: 'Asabeneh', score: 95 },
  { name: 'Mathias', score: 80 },
  { name: 'Elias', score: 50 },
  { name: 'Martha', score: 85 },
  { name: 'John', score: 100 },
]

const score = scores.find((user) => user.score > 80)
console.log(score)
```

```sh
{ name: "Asabeneh", score: 95 }
```

### findIndex

_findIndex_: Shartni qondiradigan birinchi elementning o'rnini qaytaring

```js
const names = ['Asabeneh', 'Mathias', 'Elias', 'Brook']
const ages = [24, 22, 25, 32, 35, 18]

const result = names.findIndex((name) => name.length > 7)
console.log(result) // 0

const age = ages.findIndex((age) => age < 20)
console.log(age) // 5
```

### some

_some_: Ba'zi elementlarning bir jihati bilan o'xshashligini tekshiring. Bu booleanni qaytaradi

```js
const names = ['Asabeneh', 'Mathias', 'Elias', 'Brook']
const bools = [true, true, true, true]

const areSomeTrue = bools.some((b) =>  b === true)

console.log(areSomeTrue) //true
```

```js
const areAllStr = names.some((name) => typeof name === 'number') // Are all strings ?
console.log(areAllStr) // false
```

### sort

_sort_: Saralash usullari massiv elementlarini o'sish yoki kamayish tartibida tartibga soladi. Odatiy bo'lib, sort() usuli qiymatlarni strings sifatida saralaydi. Bu qatorlar uchun yaxshi ishlaydi, lekin raqamlar uchun emas. Agar raqam qiymatlari satrlar sifatida tartiblangan bo'lsa va bu bizga noto'g'ri natija bersa. Saralash usuli asl massivni o'zgartiradi. Saralash usulidan foydalanishni boshlashdan oldin asl ma'lumotlarni nusxalash tavsiya etiladi .

#### Satr qiymatlarini saralash

```js
const products = ['Milk', 'Coffee', 'Sugar', 'Honey', 'Apple', 'Carrot']
console.log(products.sort()) // ['Apple', 'Carrot', 'Coffee', 'Honey', 'Milk', 'Sugar']
//Endi asl mahsulotlar qatori ham tartiblangan
```

#### Raqamli qiymatlarni saralash

Quyidagi misolda ko'rib turganingizdek, o'sish tartibida tartiblangandan keyin 100 birinchi bo'ldi. Saralash elementni string ga o'zgartiradi, chunki '100' va boshqa raqamlar taqqoslangan, '100' qatorining boshi eng kichik bo'lgan 1. Bunga yo'l qo'ymaslik uchun biz tartiblash usuli ichida manfiy, nol yoki musbat qaytaruvchi solishtirma qo'ng'iroq funksiyasidan foydalanamiz.

```js
const numbers = [9.81, 3.14, 100, 37]
// Raqamli elementlarni tartiblash uchun sort usulidan foydalanish noto'g'ri natija beradi. pastga qarang
console.log(numbers.sort()) //[100, 3.14, 37, 9.81]
numbers.sort(function (a, b) {
  return a - b
})

console.log(numbers) // [3.14, 9.81, 37, 100]

numbers.sort(function (a, b) {
  return b - a
})
console.log(numbers) //[100, 37, 9.81, 3.14]
```

#### Obyektli massivlarni saralash

Biz ob'ektlarni massivda saralaganimizda. Taqqoslash uchun obyekt tugmasidan foydalanamiz. Quyidagi misolni ko'rib chiqaylik.

```js
objArr.sort(function (a, b) {
  if (a.key < b.key) return -1
  if (a.key > b.key) return 1
  return 0
})

// or

objArr.sort(function (a, b) {
  if (a['key'] < b['key']) return -1
  if (a['key'] > b['key']) return 1
  return 0
})

const users = [
  { name: 'Asabeneh', age: 150 },
  { name: 'Brook', age: 50 },
  { name: 'Eyo', age: 100 },
  { name: 'Elias', age: 22 },
]
users.sort((a, b) => {
  if (a.age < b.age) return -1
  if (a.age > b.age) return 1
  return 0
})
console.log(users) // ortib borishda tartiblangan
// [{…}, {…}, {…}, {…}]
```

🌕 Siz ajoyib ish qilyapsiz. Hech qachon taslim bo'lmang, chunki buyuk ishlar vaqt talab etadi. Siz hozirgina 9-kun sinovlarini yakunladingiz va siz buyuklik sari 9 qadam oldindasiz. Endi miyangiz va mushaklaringiz uchun bir nechta mashqlarni bajaring.

## 💻 Mashqlar

### Mashqlar: Level 1

```js
const countries = ['Finland', 'Sweden', 'Denmark', 'Norway', 'IceLand']
const names = ['Asabeneh', 'Mathias', 'Elias', 'Brook']
const numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
const products = [
  { product: 'banana', price: 3 },
  { product: 'mango', price: 6 },
  { product: 'potato', price: ' ' },
  { product: 'avocado', price: 8 },
  { product: 'coffee', price: 10 },
  { product: 'tea', price: '' },
]
```

1. **_forEach, map, filter, va reduce_** o'rtasidagi farqni tushuntiring .
2. **_forEach_** ilovasida `call` funksiyasini aniqlang, map, filter yoki reduce.
3. Use **_forEach_** to console.log each country in the countries array.
4. Use **_forEach_** to console.log each name in the names array.
5. Use **_forEach_** to console.log each number in the numbers array.
6. Use **_map_** to create a new array by changing each country to uppercase in the countries array.
7. Use **_map_** to create an array of countries length from countries array.
8. Use **_map_** to create a new array by changing each number to square in the numbers array
9. Use **_map_** to change to each name to uppercase in the names array
10. Use **_map_** to map the products array to its corresponding prices.
11. Use **_filter_** to filter out countries containing **_land_**.
12. Use **_filter_** to filter out countries having six character.
13. Use **_filter_** to filter out countries containing six letters and more in the country array.
14. Use **_filter_** to filter out country start with 'E';
15. Use **_filter_** to filter out only prices with values.
16. Declare a function called getStringLists which takes an array as a parameter and then returns an array only with string items.
17. Use **_reduce_** to sum all the numbers in the numbers array.
18. Use **_reduce_** to concatenate all the countries and to produce this sentence: **_Estonia, Finland, Sweden, Denmark, Norway, and IceLand are north European countries_**
19. Explain the difference between **_some_** and **_every_**
20. Use **_some_** to check if some names' length greater than seven in names array
21. Use **_every_** to check if all the countries contain the word land
22. Explain the difference between **_find_** and **_findIndex_**.
23. Use **_find_** to find the first country containing only six letters in the countries array
24. Use **_findIndex_** to find the position of the first country containing only six letters in the countries array
25. Use **_findIndex_** to find the position of **_Norway_** if it doesn't exist in the array you will get -1.
26. Use **_findIndex_** to find the position of **_Russia_** if it doesn't exist in the array you will get -1.

### Mashqlar: Level 2

1. Find the total price of products by chaining two or more array iterators(eg. arr.map(callback).filter(callback).reduce(callback))
1. Find the sum of price of products using only reduce reduce(callback))
1. Declare a function called **_categorizeCountries_** which returns an array of countries which have some common pattern(you find the countries array in this repository as countries.js(eg 'land', 'ia', 'island','stan')).
1. Create a function which return an array of objects, which is the letter and the number of times the letter use to start with a name of a country.
1. Declare a **_getFirstTenCountries_** function and return an array of ten countries. Use different functional programming to work on the countries.js array
1. Declare a **_getLastTenCountries_** function which which returns the last ten countries in the countries array.
1. Find out which _letter_ is used many _times_ as initial for a country name from the countries array (eg. Finland, Fiji, France etc)

### Mashqlar: Level 3

1. Maʼlumotlar papkasida mamlakatlar maʼlumotlaridan foydalaning. Mamlakatlarni nomi, kapitali, aholisi bo‘yicha tartiblang
1. \*\*\* Eng ko'p gapiriladigan 10 ta tilni toping:

   ````js
   // Your output should look like this
   console.log(mostSpokenLanguages(countries, 10))
   [
   {country: 'English',count:91},
   {country: 'French',count:45},
   {country: 'Arabic',count:25},
   {country: 'Spanish',count:24},
   {country:'Russian',count:9},
   {country:'Portuguese', count:9},
   {country:'Dutch',count:8},
   {country:'German',count:7},
   {country:'Chinese',count:5},
   {country:'Swahili',count:4}
   ]

   // Your output should look like this
   console.log(mostSpokenLanguages(countries, 3))
   [
   {country: 'English',count: 91},
   {country: 'French',count: 45},
   {country: 'Arabic',count: 25},
   ]```

   ````

2. \*\*\* countries_data.js faylidan foydalanib, aholi eng ko'p o'nta mamlakatni yaratuvchi funksiya yarating

   ````js
   console.log(mostPopulatedCountries(countries, 10))

   [
   {country: 'China', population: 1377422166},
   {country: 'India', population: 1295210000},
   {country: 'United States of America', population: 323947000},
   {country: 'Indonesia', population: 258705000},
   {country: 'Brazil', population: 206135893},
   {country: 'Pakistan', population: 194125062},
   {country: 'Nigeria', population: 186988000},
   {country: 'Bangladesh', population: 161006790},
   {country: 'Russian Federation', population: 146599183},
   {country: 'Japan', population: 126960000}
   ]

   console.log(mostPopulatedCountries(countries, 3))
   [
   {country: 'China', population: 1377422166},
   {country: 'India', population: 1295210000},
   {country: 'United States of America', population: 323947000}
   ]
   ```

   ````

3. \*\*\* Namunaning markaziy tendentsiyasini (o'rtacha, median, rejim) va o'zgaruvchanlik o'lchovini (diapazon, dispersiya, standart og'ish) hisoblaydigan dasturni ishlab chiqishga harakat qiling. Ushbu o'lchovlarga qo'shimcha ravishda namunaning min, maks, son, foiz va chastota taqsimotini toping. Statistika deb nomlangan ob'ektni yaratishingiz va statistika ob'ekti uchun usul sifatida statistik hisob-kitoblarni amalga oshiradigan barcha funktsiyalarni yaratishingiz mumkin. Quyidagi chiqishni tekshiring.

   ```js
   const ages = [31, 26, 34, 37, 27, 26, 32, 32, 26, 27, 27, 24, 32, 33, 27, 25, 26, 38, 37, 31, 34, 24, 33, 29, 26]

   console.log('Count:', statistics.count()) // 25
   console.log('Sum: ', statistics.sum()) // 744
   console.log('Min: ', statistics.min()) // 24
   console.log('Max: ', statistics.max()) // 38
   console.log('Range: ', statistics.range() // 14
   console.log('Mean: ', statistics.mean()) // 30
   console.log('Median: ',statistics.median()) // 29
   console.log('Mode: ', statistics.mode()) // {'mode': 26, 'count': 5}
   console.log('Variance: ',statistics.var()) // 17.5
   console.log('Standard Deviation: ', statistics.std()) // 4.2
   console.log('Variance: ',statistics.var()) // 17.5
   console.log('Frequency Distribution: ',statistics.freqDist()) # [(20.0, 26), (16.0, 27), (12.0, 32), (8.0, 37), (8.0, 34), (8.0, 33), (8.0, 31), (8.0, 24), (4.0, 38), (4.0, 29), (4.0, 25)]
   ```

   ```sh
   console.log(statistics.describe())
   Count: 25
   Sum:  744
   Min:  24
   Max:  38
   Range:  14
   Mean:  30
   Median:  29
   Mode:  (26, 5)
   Variance:  17.5
   Standard Deviation:  4.2
   Frequency Distribution: [(20.0, 26), (16.0, 27), (12.0, 32), (8.0, 37), (8.0, 34), (8.0, 33), (8.0, 31), (8.0, 24), (4.0, 38), (4.0, 29), (4.0, 25)]
   ```

🎉 TABRIKLAYMAN ! 🎉

[<< 8-kun](../08_Day_Objects/08_day_objects.md) | [10-kun >>](../10_Day_Sets_and_Maps/10_day_Sets_and_Maps.md)
