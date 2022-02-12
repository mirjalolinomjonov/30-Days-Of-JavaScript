<div align="center">
  <h1> JavaScript-ning 30 kuni: Tsikllar</h1>
  <a class="header-badge" target="_blank" href="https://www.linkedin.com/in/asabeneh/">
  <img src="https://img.shields.io/badge/style--5eba00.svg?label=LinkedIn&logo=linkedin&style=social">
  </a>


  <sub>Author:
  <a href="https://www.linkedin.com/in/asabeneh/" target="_blank">Asabeneh Yetayeh</a><br>
  <small> January, 2022</small>
  </sub>
</div>

[<< 5-kun](../05_Day_Arrays/05_day_arrays.md) | [7-kun >>](../07_Day_Functions/07_day_functions.md)

![6-kun](../images/banners/day_1_6.png)

- [📔 6-kun](#-6-kun)
  - [Tsikllar](#tsikllar)
    - [for tsikli](#for-tsikli)
    - [while tsikli](#while-tsikli)
    - [do while tsikli](#do-while-tsikli)
    - [for of tsikli](#for-of-tsikli)
    - [break](#break)
    - [continue](#continue)
  - [💻 Mashqlar:6-kun](#-mashqlar6-kun)
    - [Mashqlar: Level 1](#mashqlar-level-1)
    - [Mashqlar: Level 2](#mashqlar-level-2)
    - [Mashqlar: Level 3](#mashqlar-level-3)

# 📔 6-kun

## Tsikllar

Hayotda qiladigan ko'p harakatlarimiz takrorlash bilan to'la. Tasavvur qiling-a, agar sizdan console.log() yordamida 0 dan 100 gacha chop etishingizni so'rasam. Ushbu oddiy vazifani bajarish uchun sizga 2 dan 5 minutgacha vaqt ketishi mumkin, bunday zerikarli va takroriy vazifani tsikl yordamida bajarish mumkin. Agar siz videolarni tomosha qilishni afzal ko'rsangiz, [video darsliklarni ko'rishingiz mumkin](https://www.youtube.com/channel/UCM4xOopkYiPwJqyKsSqL9mw)

Dasturlash tillarida takrorlanuvchi topshiriqlarni bajarish uchun biz har xil turdagi sikllardan foydalanamiz. Quyidagi misollar JavaScript va boshqa dasturlash tillarida tez-tez ishlatiladigan sikllardir.

### for tsikli

```js
// For tsikli tuzilishi 
for(initialization, condition, increment/decrement){
  // kod shu yerda 
}
```

```js
for(let i = 0; i <= 5; i++){
  console.log(i)
}

// 0 1 2 3 4 5
```

```js
for(let i = 5; i >= 0; i--){
  console.log(i)
}

// 5 4 3 2 1 0
```

```js
for(let i = 0; i <= 5; i++){
  console.log(`${i} * ${i} = ${i * i}`)
}
```

```sh
0 * 0 = 0
1 * 1 = 1
2 * 2 = 4
3 * 3 = 9
4 * 4 = 16
5 * 5 = 25
```

```js
const countries = ['Finland', 'Sweden', 'Denmark', 'Norway', 'Iceland']
const newArr = []
for(let i = 0; i < countries.length; i++){
  newArr.push(countries[i].toUpperCase())
}

// ["FINLAND", "SWEDEN", "DENMARK", "NORWAY", "ICELAND"]
```

Massivdagi barcha elementlarni qo'shish

```js
const numbers = [1, 2, 3, 4, 5]
let sum = 0
for(let i = 0; i < numbers.length; i++){
  sum  = sum + numbers[i]  // qisqartirilishi mumkin, sum += numbers[i]

}

console.log(sum)  // 15
```

Mavjud massiv asosida yangi massiv yaratish

```js
const numbers = [1, 2, 3, 4, 5]
const newArr = []
let sum = 0
for(let i = 0; i < numbers.length; i++){
  newArr.push( numbers[i] ** 2)

}

console.log(newArr)  // [1, 4, 9, 16, 25]
```

```js
const countries = ['Finland', 'Sweden', 'Norway', 'Denmark', 'Iceland']
const newArr = []
for(let i = 0; i < countries.length; i++){
  newArr.push(countries[i].toUpperCase())
}

console.log(newArr)  // ["FINLAND", "SWEDEN", "NORWAY", "DENMARK", "ICELAND"]
```

### while tsikli

```js
let i = 0
while (i <= 5) {
  console.log(i)
  i++
}

// 0 1 2 3 4 5
```

### do while tsikli

```js
let i = 0
do {
  console.log(i)
  i++
} while (i <= 5)

// 0 1 2 3 4 5
```

### for of tsikli

Biz massivlar uchun _for of_ loop dan foydalanamiz. Agar biz massivdagi har bir elementning indeksiga qiziqmasangiz, bu massivni takrorlashning juda qulay usuli.

```js
for (const element of arr) {
  // kod shu yerda 
}
```

```js

const numbers = [1, 2, 3, 4, 5]

for (const num of numbers) {
  console.log(num)
}

// 1 2 3 4 5

for (const num of numbers) {
  console.log(num * num)
}

// 1 4 9 16 25

// massivdagi barcha raqamlarni qo'shsak 
let sum = 0
for (const num of numbers) {
  sum = sum + num  // shu tarzda ham qisqartirilishi mumkin, sum += num
}
console.log(sum) // 15

const webTechs = [
  'HTML',
  'CSS',
  'JavaScript',
  'React',
  'Redux',
  'Node',
  'MongoDB'
]

for (const tech of webTechs) {
  console.log(tech.toUpperCase())
}

// HTML CSS JAVASCRIPT REACT NODE MONGODB

for (const tech of webTechs) {
  console.log(tech[0]) // har bir elementning faqat birinchi harfini olish,  H C J R N M
}

```

```js
const countries = ['Finland', 'Sweden', 'Norway', 'Denmark', 'Iceland']
const newArr = []
for(const country of countries){
  newArr.push(country.toUpperCase())
}

console.log(newArr)  // ["FINLAND", "SWEDEN", "NORWAY", "DENMARK", "ICELAND"]
```

### break

Break tsiklni buzish(to'xtatish) uchun ishlatiladi.

```js
for(let i = 0; i <= 5; i++){
  if(i == 3){
    break
  }
  console.log(i)
}

// 0 1 2
```

Yuqoridagi kod, agar takrorlash jarayonida 3 topilsa, to'xtaydi.

### continue

Biz ma'lum bir takrorlashni o'tkazib yuborish uchun *continue*  kalit so'zidan foydalanamiz .

```js
for(let i = 0; i <= 5; i++){
  if(i == 3){
    continue
  }
  console.log(i)
}

// 0 1 2 4 5
```

🌕 Siz juda jasursiz, siz shu paytgacha erishdingiz. Endi siz takrorlanadigan va zerikarli vazifalarni avtomatlashtirish qudratiga ega bo'ldingiz. Siz hozirgina 6 kunlik sinovlarni yakunladingiz va siz buyuklik sari 6 qadam oldindasiz. Endi miyangiz va mushaklaringiz uchun bir nechta mashqlarni bajaring.

## 💻 Mashqlar:6-kun

### Mashqlar: Level 1

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

  const mernStack = ['MongoDB', 'Express', 'React', 'Node']
  ```

1. For tsikli yordamida 0 dan 10 gacha takrorlang, while va do while yordamida xuddi shunday qiling
2. For tsikli yordamida 10 dan 0 gacha takrorlang, while va do while yordamida xuddi shunday qiling
3. For tsikli yordamida 0 dan n gacha takrorlang
4. console.log() dan foydalanib quyidagi naqsh hosil qiluvchi tsiklni yozing:

   ```js
       #
       ##
       ###
       ####
       #####
       ######
       #######
   ```

5. Quyidagi naqshni chop etish uchun Tsikldan foydalaning:

   ```sh
   0 x 0 = 0
   1 x 1 = 1
   2 x 2 = 4
   3 x 3 = 9
   4 x 4 = 16
   5 x 5 = 25
   6 x 6 = 36
   7 x 7 = 49
   8 x 8 = 64
   9 x 9 = 81
   10 x 10 = 100
   ```

6. Tsikl yordamida quyidagi naqshni chop eting

   ```sh
    i    i^2   i^3
    0    0     0
    1    1     1
    2    4     8
    3    9     27
    4    16    64
    5    25    125
    6    36    216
    7    49    343
    8    64    512
    9    81    729
    10   100   1000
   ```

7. 0 dan 100 gacha takrorlash va faqat juft raqamlarni chop etish uchun for tsiklidan foydalaning
8. 0 dan 100 gacha takrorlash va faqat toq raqamlarni chop etish uchun for tsikli dan foydalaning
9. 0 dan 100 gacha takrorlash va faqat tub sonlarni chop etish uchun for tsikli dan foydalaning
10. 0 dan 100 gacha takrorlash va barcha raqamlarning yig'indisini chop etish uchun for tsikli dan foydalaning.

    ```sh
    0 dan 100 gacha bo'lgan barcha raqamlar yig'indisi 5050 ga teng.
    ```

11. 0 dan 100 gacha takrorlash va barcha juftliklar yig'indisini va barcha koeffitsientlar yig'indisini chop etish uchun for tsiklidan foydalaning.

    ```sh
    0 dan 100 gacha bo'lgan barcha juftliklar yig'indisi 2550 ga teng. 0 dan 100 gacha bo'lgan barcha koeffitsientlar yig'indisi esa 2500 ga teng.
    ```

12. 0 dan 100 gacha takrorlash va barcha juftliklar yig'indisini va barcha koeffitsientlar yig'indisini chop etish uchun for tsiklidan foydalaning. Juftliklar yig‘indisi va koeffitsientlar yig‘indisini massiv sifatida chop eting

    ```sh
      [2550, 2500]
    ```

13. 5 ta tasodifiy sonlar qatorini yaratadigan kichik skriptni ishlab chiqing
14. 5 ta tasodifiy sonlar massivini yaratadigan kichik skriptni ishlab chiqing va raqamlar noyob bo'lishi kerak
15. Olti belgidan iborat tasodifiy identifikatorni yaratadigan kichik skriptni ishlab chiqing:

    ```sh
    5j2khz
    ```

### Mashqlar: Level 2

1. Tasodifiy identifikatorning istalgan sonini yaratadigan kichik skriptni ishlab chiqing:

    ```sh
      fe3jo1gl124g
    ```

    ```sh
      xkqci4utda1lmbelpkm03rba
    ```

2. Tasodifiy o'n oltilik sonni yaratadigan skriptni yozing.

    ```sh
    '#ee33df'
    ```

3. Tasodifiy rgb rang raqamini yaratadigan skriptni yozing.

    ```sh
    rgb(240,180,80)
    ```

4. Yuqoridagi mamlakatlar massividan foydalanib, quyidagi yangi massivni yarating.

    ```sh
    ["ALBANIA", "BOLIVIA", "CANADA", "DENMARK", "ETHIOPIA", "FINLAND", "GERMANY", "HUNGARY", "IRELAND", "JAPAN", "KENYA"]
    ```

5. Yuqoridagi mamlakatlar massividan foydalanib, mamlakatlar uzunligi uchun massiv yarating'.

    ```sh
    [7, 7, 6, 7, 8, 7, 7, 7, 7, 5, 5]
    ```

6. Quyidagi massivlarni yaratish uchun mamlakatlar massividan foydalaning:

    ```sh
      [
      ['Albania', 'ALB', 7],
      ['Bolivia', 'BOL', 7],
      ['Canada', 'CAN', 6],
      ['Denmark', 'DEN', 7],
      ['Ethiopia', 'ETH', 8],
      ['Finland', 'FIN', 7],
      ['Germany', 'GER', 7],
      ['Hungary', 'HUN', 7],
      ['Ireland', 'IRE', 7],
      ['Iceland', 'ICE', 7],
      ['Japan', 'JAP', 5],
      ['Kenya', 'KEN', 5]
    ]
    ```

7. Yuqoridagi mamlakatlar qatorida “er” soʻzini oʻz ichiga olgan mamlakat yoki mamlakatlar mavjudligini tekshiring. Agar "er" ni o'z ichiga olgan mamlakatlar mavjud bo'lsa, uni massiv sifatida chop eting. Agar "er" so'zini o'z ichiga olgan mamlakat bo'lmasa, "Bu mamlakatlarning barchasi yersiz" deb chop eting.

    ```sh
    ['Finland','Ireland', 'Iceland']
    ```

8. Yuqoridagi mamlakatlar qatorida “ia” pastki qatori bilan tugaydigan mamlakat yoki mamlakatlar mavjudligini tekshiring. Agar bilan tugaydigan mamlakatlar boʻlsa, uni massiv sifatida chop eting. Agar "ai" so'zini o'z ichiga olgan mamlakat bo'lmasa, "Bu mamlakatlar iasiz tugaydi" deb chop eting.

    ```sh
    ['Albania', 'Bolivia','Ethiopia']
    ```

9. Yuqoridagi mamlakatlar qatoridan foydalanib, eng koʻp belgilar soniga ega mamlakatni toping.

      ```sh
      Ethiopia
      ```

10. Yuqoridagi mamlakatlar qatoridan foydalanib, faqat 5 ta belgidan iborat mamlakatni toping.

     ```sh
     ['Japan', 'Kenya']
     ```

11. webTechs massividagi eng uzun so'zni toping
12. Quyidagi massivlarni yaratish uchun webTechs massividan foydalaning:

     ```sh
     [["HTML", 4], ["CSS", 3],["JavaScript", 10],["React", 5],["Redux", 5],["Node", 4],["MongoDB", 7]]
     ```

13. AMongoDB, Express, React va Node yordamida yaratilgan ilova MERN stek ilovasi deb ataladi. mernStack massividan foydalanib, MERN qisqartmasini yarating
14. ["HTML", "CSS", "JS", "React", "Redux", "Node", "Express", "MongoDB"] massiv bo'ylab for yoki for tsiklidan foydalanib iteratsiya qiling va uni chop eting. buyumlar.
15. Bu meva massivi , ['banana', 'apelsin', 'mango', 'limon'] teskari usuldan foydalanmasdan loop yordamida tartibni o'zgartiradi.
16. Quyida ko'rsatilgandek massivning barcha elementlarini chop eting.

    ```js
      const fullStack = [
        ['HTML', 'CSS', 'JS', 'React'],
        ['Node', 'Express', 'MongoDB']
      ]
    ````

    ```sh
      HTML
      CSS
      JS
      REACT
      NODE
      EXPRESS
      MONGODB
    ```

### Mashqlar: Level 3

1. Mamlakatlar qatorini nusxalash (mutatsiyadan saqlaning)
2. Massivlar o'zgaruvchan. Asl nusxani o'zgartirmaydigan massiv nusxasini yarating.Nusxalangan massivni tartiblang va sortedCountries oʻzgaruvchisida saqlang
3. webTechs massivi va mernStack massivini tartiblang
4. [Mamlakatlar massividan](https://github.com/Asabeneh/30DaysOfJavaScript/tree/master/data/countries.js) “er” so‘zini o‘z ichiga olgan barcha mamlakatlarni ajratib oling va uni massiv sifatida chop eting
5. [Mamlakatlar massividan](https://github.com/Asabeneh/30DaysOfJavaScript/tree/master/data/countries.js) Yilda belgilar sifatli raqamini o'z ichiga olgan mamlakatni topish
6. [Mamlakatlar massividan](https://github.com/Asabeneh/30DaysOfJavaScript/tree/master/data/countries.js) "r" so‘zini o‘z ichiga olgan barcha mamlakatlarni ajratib oling va uni massiv sifatida chop eting
7. [Mamlakatlar massividan](https://github.com/Asabeneh/30DaysOfJavaScript/tree/master/data/countries.js)  faqat to'rtta belgidan iborat barcha mamlakatlarni chiqarib oling va uni massiv sifatida chop eting
8. [Mamlakatlar massividan](https://github.com/Asabeneh/30DaysOfJavaScript/tree/master/data/countries.js) ikki yoki undan ortiq so'zni o'z ichiga olgan barcha mamlakatlarni ajratib oling va uni massiv sifatida chop eting
9. [Mamlakatlar massividan](https://github.com/Asabeneh/30DaysOfJavaScript/tree/master/data/countries.js) teskari aylantiring va har bir mamlakatni bosh harf bilan yozing va uni massiv sifatida saqlang

🎉 TABRIKLAYMAN ! 🎉

[<< 5-kun](../05_Day_Arrays/05_day_arrays.md) | [7-kun >>](../07_Day_Functions/07_day_functions.md)
