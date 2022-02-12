<div align="center">
  <h1> JavaScript-ning 30 kuni: Setlar va Maplar</h1>
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

[<< 9-kun](../09_Day_Higher_order_functions/09_day_higher_order_functions.md) | [11-kun>>](../11_Day_Destructuring_and_spreading/11_day_destructuring_and_spreading.md)

![10-Kun](../images/banners/day_1_10.png)

- [10-Kun](#10-kun)
  - [Set](#set)
    - [Bo'sh Set yaratish](#bosh-set-yaratish)
    - [Massivdan Set yaratish](#massivdan-set-yaratish)
    - [Setga element qo'shish](#setga-element-qoshish)
    - [Set elementini o'chirish](#set-elementini-ochirish)
    - [Setdagi elementni tekshirish](#setdagi-elementni-tekshirish)
    - [Setni tozalash](#setni-tozalash)
    - [Setlarni birlashtirish](#setlarni-birlashtirish)
    - [Setlarning kesisishi](#setlarning-kesisishi)
    - [Setlarning farqi](#setlarning-farqi)
  - [Map](#map)
    - [Bo'sh Map yaratish](#bosh-map-yaratish)
    - [Massivdan Map yaratish](#massivdan-map-yaratish)
    - [Mapga qiymatlar qo'shish](#mapga-qiymatlar-qoshish)
    - [Mapdan qiymat olish](#mapdan-qiymat-olish)
    - [Mapdagi kalitni tekshirish](#mapdagi-kalitni-tekshirish)
  - [Mashqlar](#mashqlar)
    - [Mashqlar:Level 1](#mashqlarlevel-1)
    - [Mashqlar:Level 2](#mashqlarlevel-2)
    - [Mashqlar:Level 3](#mashqlarlevel-3)

# 10-Kun

## Set

Set(To'plam) elementlar toʻplamidir. Set faqat noyob elementlarni o'z ichiga olishi mumkin.
Keling, to'plamni qanday yaratishni ko'rib chiqaylik

### Bo'sh Set yaratish

```js
const companies = new Set()
console.log(companies)
```

```sh
{}
```

### Massivdan Set yaratish

```js
const languages = [
  'English',
  'Finnish',
  'English',
  'French',
  'Spanish',
  'English',
  'French',
]

const setOfLangauges = new Set(languages)
console.log(setOfLangauges)
```

```sh
Set(4) {"English", "Finnish", "French", "Spanish"}
```

Set - bu iteratsiyalanadigan ob'ekt va biz har bir elementni iteratsiyalashimiz mumkin.

```js
const languages = [
  'English',
  'Finnish',
  'English',
  'French',
  'Spanish',
  'English',
  'French',
]

const setOfLangauges = new Set(languages)

for (const language of setOfLangauges) {
  console.log(language)
}
```

```sh
  English
  Finnish
  French
  Spanish
```

### Setga element qo'shish

```js
const companies = new Set() // bo'sh to'plam 
console.log(companies.size) // 0

companies.add('Google') // setga element qo'shish
companies.add('Facebook')
companies.add('Amazon')
companies.add('Oracle')
companies.add('Microsoft')

console.log(companies.size) // setda 5 element
console.log(companies)
```

```sh
Set(5) {"Google", "Facebook", "Amazon", "Oracle", "Microsoft"}
```

To'plamga element qo'shish uchun tsikldan ham foydalanishimiz mumkin.

```js
const companies = ['Google', 'Facebook', 'Amazon', 'Oracle', 'Microsoft']
setOfCompanies = new Set()
for (const company of companies) {
  setOfCompanies.add(company)
}
```

```sh
Set(5) {"Google", "Facebook", "Amazon", "Oracle", "Microsoft"}

```

### Set elementini o'chirish

Biz delete usuli yordamida to'plamdan elementni o'chirib tashlashimiz mumkin.

```js
console.log(companies.delete('Google'))
console.log(companies.size) // setda 4 element qoldi
```

### Setdagi elementni tekshirish

Has usuli ma'lum bir element to'plamda mavjudligini bilishga yordam beradi.

```js
console.log(companies.has('Apple')) // false
console.log(companies.has('Facebook')) // true
```

### Setni tozalash

U to'plamdan barcha elementlarni olib tashlaydi.

```js
companies.clear()

console.log(companies)
```

```sh
{}

```

To'plamdan qanday foydalanishni o'rganish uchun quyidagi misolga qarang.

```js
const languages = [
  'English',
  'Finnish',
  'English',
  'French',
  'Spanish',
  'English',
  'French',
]
const langSet = new Set(languages)
console.log(langSet) // Set(4) {"English", "Finnish", "French", "Spanish"}
console.log(langSet.size) // 4

const counts = []
const count = {}

for (const l of langSet) {
  const filteredLang = languages.filter((lng) => lng === l)
  console.log(filteredLang) // ["English", "English", "English"]
  counts.push({ lang: l, count: filteredLang.length })
}
console.log(counts)
```

```js
;[
  { lang: 'English', count: 3 },
  { lang: 'Finnish', count: 1 },
  { lang: 'French', count: 2 },
  { lang: 'Spanish', count: 1 },
]
```

To'plamdan foydalanishning boshqa holatlari. Masalan, massivdagi noyob elementni hisoblash uchun.

```js
const numbers = [5, 3, 2, 5, 5, 9, 4, 5]
const setOfNumbers = new Set(numbers)

console.log(setOfNumbers)
```

```sh
Set(5) {5, 3, 2, 9, 4}
```

### Setlarni birlashtirish

Ikki to'plamga birlashmani topish uchun tarqalish operatori yordamida erishish mumkin. A to'plam va B to'plamning birlashuvini topamiz (AUB)

```js
let a = [1, 2, 3, 4, 5]
let b = [3, 4, 5, 6]
let c = [...a, ...b]

let A = new Set(a)
let B = new Set(b)
let C = new Set(c)

console.log(C)
```

```sh
Set(6) {1, 2, 3, 4, 5,6}
```

### Setlarning kesisishi

Ikki to'plamning kesishishini topish uchun filtr yordamida erishish mumkin. A to‘plam va B to‘plamning kesishuvini topamiz (A ∩ B)

```js
let a = [1, 2, 3, 4, 5]
let b = [3, 4, 5, 6]

let A = new Set(a)
let B = new Set(b)

let c = a.filter((num) => B.has(num))
let C = new Set(c)

console.log(C)
```

```sh
Set(3) {3, 4, 5}
```

### Setlarning farqi

Ikki to'plam orasidagi farqni topish uchun filtr yordamida erishish mumkin. A to'plam va B to'plamning farqini topamiz (A \ B)

```js
let a = [1, 2, 3, 4, 5]
let b = [3, 4, 5, 6]

let A = new Set(a)
let B = new Set(b)

let c = a.filter((num) => !B.has(num))
let C = new Set(c)

console.log(C)
```

```sh
Set(2) {1, 2}
```

## Map

### Bo'sh Map yaratish

```js
const map = new Map()
console.log(map)
```

```sh
Map(0) {}
```

### Massivdan Map yaratish

```js
countries = [
  ['Finland', 'Helsinki'],
  ['Sweden', 'Stockholm'],
  ['Norway', 'Oslo'],
]
const map = new Map(countries)
console.log(map)
console.log(map.size)
```

```sh
Map(3) {"Finland" => "Helsinki", "Sweden" => "Stockholm", "Norway" => "Oslo"}
3
```

### Mapga qiymatlar qo'shish

```js
const countriesMap = new Map()
console.log(countriesMap.size) // 0
countriesMap.set('Finland', 'Helsinki')
countriesMap.set('Sweden', 'Stockholm')
countriesMap.set('Norway', 'Oslo')
console.log(countriesMap)
console.log(countriesMap.size)
```

```sh
Map(3) {"Finland" => "Helsinki", "Sweden" => "Stockholm", "Norway" => "Oslo"}
3
```

### Mapdan qiymat olish

```js
console.log(countriesMap.get('Finland'))
```

```sh
Helsinki
```

### Mapdagi kalitni tekshirish

Has usuli yordamida xaritada kalit mavjudligini tekshiring . Bu _true_ yoki _false_ qaytaradi .

```js
console.log(countriesMap.has('Finland'))
```

```sh
true
```

Loop yordamida xaritadan barcha qiymatlarni olish

```js
for (const country of countriesMap) {
  console.log(country)
}
```

```sh
(2) ["Finland", "Helsinki"]
(2) ["Sweden", "Stockholm"]
(2) ["Norway", "Oslo"]
```

```js
for (const [country, city] of countriesMap){
console.log(country, city)
}
```

```sh
Finland Helsinki
Sweden Stockholm
Norway Oslo
```

🌕 Siz katta marraga erishdingiz, sizni to'xtatib bo'lmaydi. Davom eting! Siz hozirgina 10 kunlik sinovlarni yakunladingiz va siz buyuklik sari 10 qadam oldindasiz. Endi miyangiz va mushaklaringiz uchun bir nechta mashqlarni bajaring.

## Mashqlar

### Mashqlar:Level 1

```js
const a = [4, 5, 8, 9]
const b = [3, 4, 5, 7]
const countries = ['Finland', 'Sweden', 'Norway']
```

1. bo'sh to'plam yarating
2. Loop yordamida 0 dan 10 gacha bo'lgan to'plam yarating
3. To'plamdan elementni olib tashlang
4. To'plamni tozalash
5. Massivdan 5 ta satr elementlari toʻplamini yarating
6. Mamlakatlar xaritasini va mamlakat belgilarini yarating

### Mashqlar:Level 2

1. Birlashmani toping b
2. Kesishmani toping b
3. b bilan a toping

### Mashqlar:Level 3

1. Mamlakatlar obyekt faylida nechta til mavjud.

1. \*\*\* Eng koʻp gapiriladigan 10 ta tilni topish uchun mamlakatlar maʼlumotlaridan foydalaning:

```js
   // Sizning natijangiz shunga o'xshash bo'lishi kerak
   console.log(mostSpokenLanguages(countries, 10))
   [
     { English: 91 },
     { French: 45 },
     { Arabic: 25 },
     { Spanish: 24 },
     { Russian: 9 },
     { Portuguese: 9 },
     { Dutch: 8 },
     { German: 7 },
     { Chinese: 5 },
     { Swahili: 4 },
     { Serbian: 4 }
   ]

  // Sizning natijangiz shunga o'xshash bo'lishi kerak
  console.log(mostSpokenLanguages(countries, 3))
  [
  {English:91},
  {French:45},
  {Arabic:25}
  ]
```


🎉 TABRIKLAYMAN ! 🎉


[<< 9-kun](../09_Day_Higher_order_functions/09_day_higher_order_functions.md) | [11-kun >>](../11_Day_Destructuring_and_spreading/11_day_destructuring_and_spreading.md)
