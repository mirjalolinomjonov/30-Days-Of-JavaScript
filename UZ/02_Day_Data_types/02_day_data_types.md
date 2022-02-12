<div align="center">
  <h1> JavaScript-ning 30 kuni: Ma'lumot turlari</h1>
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

[<< 1-kun](../README.md) | [3-kun >>](../03_Day_Booleans_operators_date/03_booleans_operators_date.md)

![Thirty Days Of JavaScript](../images/banners/day_1_2.png)

- [📔 2-kun](#-2-kun)
  - [Ma'lumot turlari](#malumot-turlari)
    - [Primitiv ma'lumotlar turlari](#primitiv-malumotlar-turlari)
    - [Non-Primitiv ma'lumotlar turlari](#non-primitiv-malumotlar-turlari)
  - [Raqamlar](#raqamlar)
    - [Raqamli ma'lumotlar turlarini e'lon qilish](#raqamli-malumotlar-turlarini-elon-qilish)
    - [Math Obyekti](#math-obyekti)
      - [Tasodifiy raqamlar generatori](#tasodifiy-raqamlar-generatori)
  - [Satrlar](#satrlar)
    - [Satrlarni birlashtirish](#satrlarni-birlashtirish)
      - [Qo'shish operatori yordamida birlashtirish](#qoshish-operatori-yordamida-birlashtirish)
      - [Uzun harfli satrlar](#uzun-harfli-satrlar)
      - [Satrlardagi qochish ketma-ketligi](#satrlardagi-qochish-ketma-ketligi)
      - [Andoza harflari (shablon satrlari)](#andoza-harflari-shablon-satrlari)
    - [Satr funksiyalari](#satr-funksiyalari)
  - [Ma'lumotlar turlarini tekshirish va uzatish](#malumotlar-turlarini-tekshirish-va-uzatish)
    - [Ma'lumotlar turlarini tekshirish](#malumotlar-turlarini-tekshirish)
    - [Ma'lumotlar turini o'zgartirish (casting)](#malumotlar-turini-ozgartirish-casting)
      - [Satr ni Butun songa](#satr-ni-butun-songa)
      - [Satr ni Float(vergulli) songa](#satr-ni-floatvergulli-songa)
      - [Float(vergulli) sonni Butun songa](#floatvergulli-sonni-butun-songa)
  - [💻 2-kun: Mashqlar](#-2-kun-mashqlar)
    - [Mashq: 1-daraja](#mashq-1-daraja)
    - [Mashq: 2-daraja](#mashq-2-daraja)
    - [Mashq: 3-daraja](#mashq-3-daraja)

# 📔 2 Kun

## Ma'lumot turlari

Oldingi bo'limda biz ma'lumotlar turlari haqida bir oz eslatib o'tdik. Ma'lumotlar yoki qiymatlar ma'lumotlar turlariga ega. Ma'lumotlar turlari ma'lumotlarning xususiyatlarini tavsiflaydi. Ma'lumotlar turlarini ikkiga bo'lish mumkin:

1. Primitiv ma'lumotlar turlari
2. Oddiy bo'lmagan ma'lumotlar turlari (ob'ektga havolalar)

### Primitiv ma'lumotlar turlari

JavaScript-dagi primitive ma'lumotlar turlariga quyidagilar kiradi:

 1. Raqamlar - butun sonlar, vergulli(Float)
 2. Satrlar - bitta qo'shtirnoq ostidagi har qanday ma'lumotlar, qo'sh tirnoq yoki teskari tirnoq
 3. Mantiqiy qiymatlar - true yoki false qiymat
 4. Null - bo'sh qiymat yoki qiymat yo'q
 5. Undefined - qiymatsiz e'lon qilingan o'zgaruvchi

JavaScript-dagi Non-primitive(oddiy bo'lmagan) ma'lumotlar turlarini o'z ichiga oladi:

1. Ob'ektlar
2. Funksiyalar
3. Massivlar

Keling, Primitive va Primitive bo'lmagan ma'lumotlar turlari nimani anglatishini ko'rib chiqaylik. _Primitiv_ ma'lumotlar turlari o'zgarmas (o'zgartirilmaydigan) ma'lumotlar turlaridir. Bir Primitive ma'lumotlar turi yaratilgandan keyin biz uni o'zgartira olmaymiz.

**Misol:**

```js
let word = 'JavaScript'
```

Agar biz _word_ o'zgaruvchisida saqlangan satrni o'zgartirishga harakat qilsak, JavaScript xatoga yo'l qo'yishi kerak. Bitta qo'shtirnoq, qo'sh qo'shtirnoq yoki teskari tirnoq ostidagi har qanday ma'lumotlar turi satr ma'lumotlar turidir.

```js
word[0] = 'Y'
```

Bu ifoda _word_ o'zgaruvchisida saqlangan qatorni o'zgartirmaydi. Shunday qilib, biz satrlarni o'zgartirib bo'lmaydigan yoki boshqacha qilib aytganda o'zgarmas deb aytishimiz mumkin. Primitiv ma'lumotlar turlari qiymatlari bo'yicha taqqoslanadi. Keling, turli xil ma'lumotlar qiymatlarini solishtiraylik.
Quyidagi misolga qarang:

```js
let numOne = 3
let numTwo = 3

console.log(numOne == numTwo)      // true

let js = 'JavaScript'
let py = 'Python'

console.log(js == py)             //false 

let lightOn = true
let lightOff = false

console.log(lightOn == lightOff) // false
```

### Non-Primitiv ma'lumotlar turlari

Primitiv bo'lmagan ma'lumotlar turlari o'zgartirilishi yoki o'zgarishi mumkin. Biz primitive bo'lmagan ma'lumotlar turlarining qiymatini yaratilgandan keyin o'zgartirishimiz mumkin. Keling, massiv yaratish orqali ko'raylik. Massiv - kvadrat qavs ichidagi ma'lumotlar qiymatlari ro'yxati.
Massivlar bir xil yoki turli xil ma'lumotlarni o'z ichiga olishi mumkin. Massiv qiymatlariga ularning indeksi orqali havola qilinadi. JavaScript-da massiv indeksi noldan boshlanadi.
Ya'ni, massivning 1-elementi indeks 0 da, 2-element 1-indeksda, 3-element esa 2-indeksda va hokazo.

```js
let nums = [1, 2, 3]
nums[0] = 10

console.log(nums)  // [10, 2, 3]
```

Ko'rib turganingizdek, primitiv bo'lmagan ma'lumotlar turi bo'lgan massiv o'zgaruvchan. Primitiv bo'lmagan ma'lumotlar turlarini qiymat bo'yicha taqqoslab bo'lmaydi. Ikki primitive bo'lmagan ma'lumotlar turi bir xil xususiyat va qiymatlarga ega bo'lsa ham, ular qat'iy teng emas.

```js
let nums = [1, 2, 3]
let numbers = [1, 2, 3]
// 2 ta massivni solishtiramiz va ular qat'iy teng emas!
console.log(nums == numbers)  // false

let userOne = {
name:'Asabeneh',
role:'teaching',
country:'Finland'
}

let userTwo = {
name:'Asabeneh',
role:'teaching',
country:'Finland'
}
// 2 ta obyektni solishtiramiz va ular qat'iy teng emas!
console.log(userOne == userTwo) // false
```

Asosiy qoida, biz primitive bo'lmagan ma'lumotlar turlarini solishtirmaymiz. Massivlarni, funktsiyalarni yoki ob'ektlarni solishtirmang. Primitiv bo'lmagan qiymatlar mos yozuvlar turlari deb ataladi, chunki ular qiymat o'rniga mos yozuvlar bilan taqqoslanadi.
Ikki ob'ekt faqat bir xil asosiy ob'ektga tegishli bo'lsa, qat'iy tengdir.

```js
let nums = [1, 2, 3]
let numbers = nums

console.log(nums == numbers)  // true

let userOne = {
name:'Asabeneh',
role:'teaching',
country:'Finland'
}

let userTwo = userOne

console.log(userOne == userTwo)  // true
```

Agar siz primitive ma'lumotlar turlari va primitive bo'lmagan ma'lumotlar turlari o'rtasidagi farqni tushunishda qiynalayotgan bo'lsangiz, siz yagona emassiz. Tinchlaning va faqat keyingi bo'limga o'ting va biroz vaqt o'tgach qaytib kelishga harakat qiling.
Endi raqamlar turi bo'yicha ma'lumotlar turlarini boshlaylik.

## Raqamlar

Raqamlar barcha arifmetik amallarni bajara oladigan butun va o'nlik qiymatlardir. Keling, raqamlarning ba'zi misollarini ko'rib chiqaylik.


### Raqamli ma'lumotlar turlarini e'lon qilish

```js
let age = 35
const gravity = 9.81  // o'zgarmas qiymatlar uchun const dan foydalanamiz, tortishish doimiysi m/s2
let mass = 72         // Kilogrammdagi massa
const PI = 3.14       // pi geometrik doimiy

// Ko'proq misollar
const boilingPoint = 100 // oC dagi harorat, doimiy bo'lgan suvning qaynash nuqtasi
const bodyTemp = 37      // oC inson tanasining o'rtacha harorati, bu doimiy

console.log(age, gravity, mass, PI, boilingPoint, bodyTemp)
```

### Math Obyekti

JavaScript-da Math ob'ekti raqamlar bilan ishlashning ko'plab usullarini taqdim etadi.

```js
const PI = Math.PI

console.log(PI)                            // 3.141592653589793

// Eng yaqin raqamga yaxlitlash 
// agar yuqori bo'lsa, .5 yuqoriga, agar kamroq bo'lsa, 0,5 pastga yaxlitlash

console.log(Math.round(PI))                // 3 dan qiymatlarni eng yaqin raqamga yaxlitlang

console.log(Math.round(9.81))              // 10

console.log(Math.floor(PI))                // 3 pastga yaxlitlash

console.log(Math.ceil(PI))                 // 4 tepaga yaxlitlash

console.log(Math.min(-5, 3, 20, 4, 5, 10)) // -5, minimal qiymatni qaytaradi

console.log(Math.max(-5, 3, 20, 4, 5, 10)) // 20, maksimal qiymatni qaytaradi

const randNum = Math.random() // 0 dan 0.999999 gacha bo'lgan tasodifiy sonni yaratadi
console.log(randNum)

// 0 dan 10 gacha tasodifiy son yarataylik

const num = Math.floor(Math.random () * 11) // 0 dan 10 gacha bo'lgan tasodifiy sonni yaratadi
console.log(num)

//Mutlaq qiymat
console.log(Math.abs(-10))      // 10

//Kvadrat ildiz
console.log(Math.sqrt(100))     // 10

console.log(Math.sqrt(2))       // 1.4142135623730951

// Daraja
console.log(Math.pow(3, 2))     // 9

console.log(Math.E)             // 2.718

// Logarifm
// X ning E asosi bilan natural logarifmni qaytaradi, Math.log(x)
console.log(Math.log(2))        // 0.6931471805599453
console.log(Math.log(10))       // 2.302585092994046

// Trigonometriya
Math.sin(0)
Math.sin(60)

Math.cos(0)
Math.cos(60)
```

#### Tasodifiy raqamlar generatori

JavaScript Matematik Ob'ektida 0 dan 0.999999999 gacha raqamlarni hosil qiluvchi random() usuli raqamli generator mavjud...

```js
let randomNum = Math.random() // generates 0 to 0.999...
```

Keling, 0 dan 10 gacha tasodifiy sonni yaratish uchun random() usulidan qanday foydalanishimiz mumkinligini ko'rib chiqamiz:

```js
let randomNum = Math.random()         // 0 dan 0.999 gacha hosil qiladi...
let numBtnZeroAndTen = randomNum * 11

console.log(numBtnZeroAndTen)         // bu beradi: min 0 va maksimal 10.99

let randomNumRoundToFloor = Math.floor(numBtnZeroAndTen)
console.log(randomNumRoundToFloor)    // bu 0 dan 10 gacha bo'lgan qiymatlarni beradi
```

## Satrlar

Satrlar - bu **_bitta( ' )_** , _**qo'sh( " )**_, _**orqa( ` ESC ni tagida)**_ belgisi ostidagi matnlar. Satrni e'lon qilish uchun bizga o'zgaruvchi nomi, belgilash operatori, bitta qo'shtirnoq ostidagi qiymat, qo'sh qo'shtirnoq yoki teskari tirnoq kerak.
Keling, qatorlarning ba'zi misollarini ko'rib chiqaylik:

```js
let space = ' '           // bo'sh joy satri
let firstName = 'Asabeneh'
let lastName = 'Yetayeh'
let country = 'Finland'
let city = 'Helsinki'
let language = 'JavaScript'
let job = 'teacher'
let quote = "The saying,'Seeing is Believing' is not correct in 2022."
let quotWithBackTick = `The saying,'Seeing is Believing' is not correct in 2022.`
```

### Satrlarni birlashtirish

Ikki yoki undan ortiq qatorlarni bir-biriga bog'lash birlashma deyiladi. Oldingi String bo'limida e'lon qilingan satrlardan foydalanish:

```js
let fullName = firstName + space + lastName; // birlashtirish, ikki qatorni birlashtirish.
console.log(fullName);
```

```sh
Asabeneh Yetayeh
```

Biz satrlarni turli yo'llar bilan birlashtira olamiz.

#### Qo'shish operatori yordamida birlashtirish

Qo‘shish operatori yordamida birlashtirish eski usul. Birlashtirishning bu usuli zerikarli va xatolarga moyil. Shu tarzda birlashtirishni bilish yaxshi, lekin men ES6 shablon satrlaridan foydalanishni tavsiya qilaman (keyinroq tushuntiriladi).

```js
// Har xil turdagi ma'lumotlarning turli o'zgaruvchilarini e'lon qilish
let space = ' '
let firstName = 'Asabeneh'
let lastName = 'Yetayeh'
let country = 'Finland'
let city = 'Helsinki'
let language = 'JavaScript'
let job = 'teacher'
let age = 250


let fullName =firstName + space + lastName
let personInfoOne = fullName + '. I am ' + age + '. I live in ' + country; // ES5 satrlarni birlashtirish

console.log(personInfoOne)
```

```sh
Natija:
Asabeneh Yetayeh. I am 250. I live in Finland
```

#### Uzun harfli satrlar

Satr bitta belgi yoki paragraf yoki sahifa bo'lishi mumkin. Agar satrning uzunligi juda katta bo'lsa, u bir qatorga to'g'ri kelmaydi. Satrning keyingi satrda davom etishini bildirish uchun har bir satr oxiridagi teskari chiziq belgisidan (\) foydalanishimiz mumkin.
**Misol:**

```js
const paragraph = "My name is Asabeneh Yetayeh. I live in Finland, Helsinki.\
I am a teacher and I love teaching. I teach HTML, CSS, JavaScript, React, Redux, \
Node.js, Python, Data Analysis and D3.js for anyone who is interested to learn. \
In the end of 2019, I was thinking to expand my teaching and to reach \
to global audience and I started a Python challenge from November 20 - December 19.\
It was one of the most rewarding and inspiring experience.\
Now, we are in 2022. I am enjoying preparing the 30DaysOfJavaScript challenge and \
I hope you are enjoying too."

console.log(paragraph)
```

#### Satrlardagi qochish ketma-ketligi

JavaScript va boshqa dasturlash tillarida \ va undan keyin ba'zi belgilar qochib ketish ketma-ketligidir. Keling, eng keng tarqalgan qochish belgilarini ko'rib chiqaylik:

- \n: yangi qator
- \t: Tab, odatda 4 bo'shliqni bildiradi
- \\: Teskari chiziq
- \': Bitta tirnoq (')
- \": Qo'sh tirnoq (")
  
```js
console.log('Umid qilamanki, barchaga JavaScript-ning 30 kuni tanlovi yoqadi.\nSizgachi ?') // qator uzilishi(yangi qatorga o'tish)
console.log('Kunlar\tMavzular\tMashqlar')
console.log('Kun 1\t3\t5')
console.log('Kun 2\t3\t5')
console.log('Kun 3\t3\t5')
console.log('Kun 4\t3\t5')
console.log('Bu teskari chiziq belgisi (\\)') // Teskari chiziq yozish uchun
console.log('Har bir dasturlash tilida u bilan boshlanadi \"Hello, World!\"')
console.log("Har bir dasturlash tilida u bilan boshlanadi \'Hello, World!\'")
console.log('The saying \'Seeing is Believing\' isn\'t correct in 2022')
```

Konsolda chiqish:

```sh
Umid qilamanki, barchaga JavaScript-ning 30 kuni tanlovi yoqadi.
Sizgachi ?
Kunlar	Mavzular	Mashqlar
Kun 1 3 5
Kun 2 3 5
Kun 3 3 5
Kun 4 3 5
Bu teskari chiziq belgisi (\)
Har bir dasturlash tilida u bilan boshlanadi "Hello, World!"
Har bir dasturlash tilida u bilan boshlanadi 'Hello, World!'
The saying 'Seeing is Believing' isn't correct in 2022
```

#### Andoza harflari (shablon satrlari)

Shablon satrlarini yaratish uchun biz ikkita orqa belgidan foydalanamiz. Biz ma'lumotlarni shablon qatoriga ifoda sifatida kiritishimiz mumkin. Ma'lumotni kiritish uchun biz iborani $ belgisidan oldin jingalak qavs ({}) bilan o'rab olamiz. Quyidagi sintaksisga qarang.

```js
//Sintaksis
`String literal matn`
`String literal matn ${ifoda}`
```

**Misol: 1**

```js
console.log(`The sum of 2 and 3 is 5`)              // ma'lumotlarni statik ravishda yozish
let a = 2
let b = 3
console.log(`The sum of ${a} and ${b} is ${a + b}`) // ma'lumotlarni dinamik ravishda satr ichiga kiritish 
```

**Misol:2**

```js
let firstName = 'Asabeneh'
let lastName = 'Yetayeh'
let country = 'Finland'
let city = 'Helsinki'
let language = 'JavaScript'
let job = 'teacher'
let age = 250
let fullName = firstName + ' ' + lastName

let personInfoTwo = `I am ${fullName}. I am ${age}. I live in ${country}.` //ES6 - String interpolyatsiya usuli
let personInfoThree = `I am ${fullName}. I live in ${city}, ${country}. I am a ${job}. I teach ${language}.`
console.log(personInfoTwo)
console.log(personInfoThree)
```

```sh
I am Asabeneh Yetayeh. I am 250. I live in Finland.
I am Asabeneh Yetayeh. I live in Helsinki, Finland. I am a teacher. I teach JavaScript.
```

Satr shablonidan yoki satr interpolyatsiyasi usulidan foydalanib, biz qiymat bo'lishi mumkin bo'lgan ifodalarni yoki ba'zi operatsiyalarni (taqqoslash, arifmetik amallar, uchlik operatsiya) qo'shishimiz mumkin.

```js
let a = 2
let b = 3
console.log(`${a} is greater than ${b}: ${a > b}`)
```

```sh
2 is greater than 3: false
```

### Satr funksiyalari

JavaScript-dagi hamma narsa ob'ektdir. Satr - bu primitive ma'lumotlar turi bo'lib, biz uni yaratilgandan keyin o'zgartira olmaymiz. String ob'ektida ko'plab string methodlari mavjud. Satrlar bilan ishlashda bizga yordam beradigan turli xil string methodlari mavjud.

1. *length*: Satrning *length* usuli bo'sh joy kiritilgan qatordagi belgilar sonini qaytaradi.

**Misol:**

```js
let js = 'JavaScript'
console.log(js.length)         // 10
let firstName = 'Asabeneh'
console.log(firstName.length)  // 8
```

2. Satrdagi belgilarga kirish: Biz uning indeksidan foydalanib, satrdagi har bir belgiga kirishimiz mumkin. Dasturlashda sanash 0 dan boshlanadi. Satrning 1-indeksi 0 ga teng, oxirgi indeks esa satr uzunligi -1 ga teng.

  ![Accessing sting by index](../images/string_indexes.png)

Keling, "JavaScript" qatoridagi turli belgilarga kirishga ruxsat bering.

```js
let string = 'JavaScript'
let firstLetter = string[0]

console.log(firstLetter)           // J

let secondLetter = string[1]       // a
let thirdLetter = string[2]
let lastLetter = string[9]

console.log(lastLetter)            // t

let lastIndex = string.length - 1

console.log(lastIndex)  // 9
console.log(string[lastIndex])    // t
```

3. *toUpperCase()*: bu method satrni katta harflarga o'zgartiradi.

```js
let string = 'JavaScript'

console.log(string.toUpperCase())     // JAVASCRIPT

let firstName = 'Asabeneh'

console.log(firstName.toUpperCase())  // ASABENEH

let country = 'Finland'

console.log(country.toUpperCase())    // FINLAND
```

4. *toLowerCase()*: bu method satrni kichik harflarga o'zgartiradi.

```js
let string = 'JavasCript'

console.log(string.toLowerCase())     // javascript

let firstName = 'Asabeneh'

console.log(firstName.toLowerCase())  // asabeneh

let country = 'Finland'

console.log(country.toLowerCase())   // finland
```

5. *substr()*: Ikkita argument, boshlang'ich indeks va bo'laklarga bo'linadigan belgilar soni kerak bo'ladi.

```js
let string = 'JavaScript'
console.log(string.substr(4,6))    // Script

let country = 'Finland'
console.log(country.substr(3, 4))   // land
```

6. *substring()*: Bu ikkita argumentni oladi, boshlang'ich indeks va to'xtash indeksi, lekin u to'xtash indeksidagi belgini o'z ichiga olmaydi.

```js
let string = 'JavaScript'

console.log(string.substring(0,4))     // Java
console.log(string.substring(4,10))    // Script
console.log(string.substring(4))       // Script

let country = 'Finland'

console.log(country.substring(0, 3))   // Fin
console.log(country.substring(3, 7))   // land
console.log(country.substring(3))      // land
```

7. *split()*: Split methodi qatorni belgilangan joydan ajratadi.

```js
let string = '30 Days Of JavaScript'

console.log(string.split())     // Massivga o'zgartirish -> ["30 Days Of JavaScript"]
console.log(string.split(' '))  // Bo'sh joy orqali massivni bo'laklarga bo'lish -> ["30", "Days", "Of", "JavaScript"]

let firstName = 'Asabeneh'

console.log(firstName.split())    // Massivga o'zgartirish - > ["Asabeneh"]
console.log(firstName.split(''))  // Har bir harfda massivga bo'linadi ->  ["A", "s", "a", "b", "e", "n", "e", "h"]

let countries = 'Finland, Sweden, Norway, Denmark, and Iceland'

console.log(countries.split(','))  // vergul orqali satrni massivga bo'lib tashlash-> ["Finland", " Sweden", " Norway", " Denmark", " and Iceland"]
console.log(countries.split(', ')) //  ["Finland", "Sweden", "Norway", "Denmark", "and Iceland"]
```

8. *trim()*: Satrning boshida yoki oxiridagi bo'sh joyni olib tashlaydi.

```js
let string = '   30 Days Of JavaScript   '

console.log(string)
console.log(string.trim(' '))

let firstName = ' Asabeneh '

console.log(firstName)
console.log(firstName.trim())  // hali ham satrning boshida va oxiridagi bo'shliqlarni olib tashlaydi
```

```sh
   30 Days Of JavasCript   
30 Days Of JavasCript
  Asabeneh 
Asabeneh
```

9. *includes()*: U pastki qator argumentini oladi va u satrda pastki qator argumenti mavjudligini tekshiradi. include() mantiqiy qiymatni qaytaradi. Agar satrda pastki satr mavjud bo'lsa, u rostni qaytaradi, aks holda u yolg'onni qaytaradi.

```js
let string = '30 Days Of JavaScript'

console.log(string.includes('Days'))     // true
console.log(string.includes('days'))     // false - u katta harfga sezgir! Ya'ni katta va kichik harf bir hil emas deb qabul qiladi
console.log(string.includes('Script'))   // true
console.log(string.includes('script'))   // false
console.log(string.includes('java'))     // false
console.log(string.includes('Java'))     // true

let country = 'Finland'

console.log(country.includes('fin'))     // false
console.log(country.includes('Fin'))     // true
console.log(country.includes('land'))    // true
console.log(country.includes('Land'))    // false
```

10. *replace()*: parametr sifatida eski va yangi pastki qatorni oladi. Almashtiradi eskini yangiga

```js
string.replace(oldsubstring, newsubstring)
```

```js
let string = '30 Days Of JavaScript'
console.log(string.replace('JavaScript', 'Python')) // 30 Days Of Python

let country = 'Finland'
console.log(country.replace('Fin', 'Noman'))       // Nomanland
```

11. *charAt()*: Indeksni oladi va u satrdan indeksdagi qiymatni qaytaradi

```js
string.charAt(index)
```

```js
let string = '30 Days Of JavaScript'
console.log(string.charAt(0))        // 3

let lastIndex = string.length - 1
console.log(string.charAt(lastIndex)) // t
```

12. *charCodeAt()*: Indeksni oladi va u satrning indeksdagi qiymatning char kodini (ASCII raqami) qaytaradi

```js
string.charCodeAt(index)
```

```js
let string = '30 Days Of JavaScript'
console.log(string.charCodeAt(3))        // D ASCII da 68-belgi

let lastIndex = string.length - 1
console.log(string.charCodeAt(lastIndex)) // t ASCII da 116-belgi

```

13.  *indexOf()*: Pastki satrni oladi va agar pastki satr satrda mavjud bo'lsa, u pastki satrning 1-pozitsiyasini qaytaradi, agar mavjud bo'lmasa, u -1 ni qaytaradi

```js
string.indexOf(substring)
```

```js
let string = '30 Days Of JavaScript'

console.log(string.indexOf('D'))          // 3
console.log(string.indexOf('Days'))       // 3
console.log(string.indexOf('days'))       // -1
console.log(string.indexOf('a'))          // 4
console.log(string.indexOf('JavaScript')) // 11
console.log(string.indexOf('Script'))     //15
console.log(string.indexOf('script'))     // -1
```

14.  *lastIndexOf()*: Pastki satrni oladi va agar pastki satr satrda mavjud bo'lsa, u pastki satrning oxirgi pozitsiyasini qaytaradi, agar u mavjud bo'lmasa, u -1 ni qaytaradi.

```js
//syntax
string.lastIndexOf(substring)
```

```js
let string = 'I love JavaScript. If you do not love JavaScript what else can you love.'

console.log(string.lastIndexOf('love'))       // 67
console.log(string.lastIndexOf('you'))        // 63
console.log(string.lastIndexOf('JavaScript')) // 38
```

15. *concat()*: u ko'plab pastki qatorlarni oladi va ularni birlashtiradi.

```js
string.concat(substring, substring, substring)
```

```js
let string = '30'
console.log(string.concat("Days", "Of", "JavaScript")) // 30DaysOfJavaScript

let country = 'Fin'
console.log(country.concat("land")) // Finland
```

16. *startsWith*: u argument sifatida pastki qatorni oladi va satr o'sha ko'rsatilgan pastki qatordan boshlanishini tekshiradi. Bu mantiqiy (true yoki false) qaytaradi.

```js
//syntax
string.startsWith(substring)
```

```js
let string = 'Love is the best to in this world'

console.log(string.startsWith('Love'))   // true
console.log(string.startsWith('love'))   // false
console.log(string.startsWith('world'))  // false

let country = 'Finland'

console.log(country.startsWith('Fin'))   // true
console.log(country.startsWith('fin'))   // false
console.log(country.startsWith('land'))  //  false
```

17. *endsWith*: u argument sifatida pastki qatorni oladi va satr o'sha ko'rsatilgan pastki qator bilan tugashini tekshiradi. Bu mantiqiy (true yoki false) qaytaradi.

```js
string.endsWith(substring)
```

```js
let string = 'Love is the most powerful feeling in the world'

console.log(string.endsWith('world'))         // true
console.log(string.endsWith('love'))          // false
console.log(string.endsWith('in the world')) // true

let country = 'Finland'

console.log(country.endsWith('land'))         // true
console.log(country.endsWith('fin'))          // false
console.log(country.endsWith('Fin'))          //  false
```

18. *search*: u argument sifatida pastki qatorni oladi va u birinchi moslik indeksini qaytaradi. Qidiruv qiymati satr yoki oddiy ifoda namunasi bo'lishi mumkin.

```js
string.search(substring)
```

```js
let string = 'I love JavaScript. If you do not love JavaScript what else can you love.'
console.log(string.search('love'))          // 2
console.log(string.search(/javascript/gi))  // 7
```

19. *match*: u argument sifatida pastki satr yoki oddiy ifoda naqshini oladi va agar mos kelsa, massivni qaytaradi, agar bo'lmasa, u nullni qaytaradi. Keling, oddiy ifoda namunasi qanday ko'rinishini ko'rib chiqaylik. U / belgisi bilan boshlanadi va / belgisi bilan tugaydi.

```js
let string = 'love'
let patternOne = /love/     // har qanday bayroqsiz
let patternTwo = /love/gi   // g-butun matn bo‘ylab qidirishni bildiradi, i - katta-kichik harf sezmaydi(2 sini ham bir hil deb qabul qiladi)
```

Match sintaksisi

```js
// syntax
string.match(substring)
```

```js
let string = 'I love JavaScript. If you do not love JavaScript what else can you love.'
console.log(string.match('love'))
```

```sh
["love", index: 2, input: "I love JavaScript. If you do not love JavaScript what else can you love.", groups: undefined]
```

```js
let pattern = /love/gi
console.log(string.match(pattern))   // ["love", "love", "love"]
```

Muntazam ibora yordamida matndan raqamlarni ajratib olaylik. Bu Muntazam ifoda bo'limi emas, vahima qilmang! Muntazam iboralar haqida keyinroq toʻxtalamiz.

```js
let txt = 'In 2019, I ran 30 Days of Python. Now, in 2022 I am super exited to start this challenge'
let regEx = /\d+/

// d escape belgisi bilan d oddiy emas, d o'rniga raqam ishlaydi
// + bir yoki bir nechta raqamli sonlarni bildiradi,
// agar undan keyin g bo'lsa, bu global degan ma'noni anglatadi, hamma joyda qidiring.

console.log(txt.match(regEx))  // ["2", "0", "1", "9", "3", "0", "2", "0", "2", "0"]
console.log(txt.match(/\d+/g)) // ["2019", "30", "2022"]
```

20. *repeat()*: u argument sifatida raqamni oladi va satrning takroriy versiyasini qaytaradi.

```js
string.repeat(n)
```

```js
let string = 'love'
console.log(string.repeat(10)) // lovelovelovelovelovelovelovelovelovelove
```

## Ma'lumotlar turlarini tekshirish va uzatish

### Ma'lumotlar turlarini tekshirish

Muayyan o'zgaruvchining ma'lumotlar turini tekshirish uchun biz _typeof_ methodidan foydalanamiz.

**Misol:**

```js
// Turli xil javascript ma'lumotlar turlari
// Keling, turli xil ma'lumotlar turlarini e'lon qilaylik

let firstName = 'Asabeneh'      // string
let lastName = 'Yetayeh'        // string
let country = 'Finland'         // string
let city = 'Helsinki'           // string
let age = 250                   // number, bu mening haqiqiy yoshim emas, bu haqda tashvishlanmang ;)
let job                         // undefined, chunki qiymat belgilanmagan

console.log(typeof 'Asabeneh')  // string
console.log(typeof firstName)   // string
console.log(typeof 10)          // number
console.log(typeof 3.14)        // number
console.log(typeof true)        // boolean
console.log(typeof false)       // boolean
console.log(typeof NaN)         // number
console.log(typeof job)         // undefined
console.log(typeof undefined)   // undefined
console.log(typeof null)        // object
```

### Ma'lumotlar turini o'zgartirish (casting)

- Casting: Bir ma'lumot turini boshqa ma'lumotlar turiga aylantirish. Biz ishlatamiz _parseInt()_, _parseFloat()_, _Number()_, _+ sign_, _str()_
  Biz arifmetik amallarni bajarganimizda, satr raqamlari birinchi navbatda butun songa yoki floatga aylantirilishi kerak, agar u xato qaytarsa.

#### Satr ni Butun songa

Biz satr sonini raqamga aylantirishimiz mumkin. Qo'shtirnoq ichidagi har qanday raqam qator raqamidir. Satr raqamiga misol: '10', '5' va boshqalar.
Biz quyidagi usullardan foydalanib satrni raqamga aylantirishimiz mumkin:

- parseInt()
- Number()
- Plus belgisi(+)

```js
let num = '10'
let numInt = parseInt(num)
console.log(numInt) // 10
```

```js
let num = '10'
let numInt = Number(num)

console.log(numInt) // 10
```

```js
let num = '10'
let numInt = +num

console.log(numInt) // 10
```

#### Satr ni Float(vergulli) songa

Biz satr float raqamini float raqamiga o'zgartirishimiz mumkin. Qo'shtirnoq ichidagi har qanday suzuvchi raqam qatorli float raqamidir. Satr float raqamiga misol: '9.81', '3.14', '1.44' va boshqalar.
Biz quyidagi usullar yordamida string floatni raqamga aylantirishimiz mumkin:

- parseFloat()
- Number()
- Plus belgisi(+)

```js
let num = '9.81'
let numFloat = parseFloat(num)

console.log(numFloat) // 9.81
```

```js
let num = '9.81'
let numFloat = Number(num)

console.log(numFloat) // 9.81
```

```js
let num = '9.81'
let numFloat = +num

console.log(numInt) // 9.81
```

#### Float(vergulli) sonni Butun songa

Biz float sonlarni butun sonlarga o'zgartira olamiz.
floatni int ga aylantirish uchun quyidagi usuldan foydalanamiz:

- parseInt()
  
```js
let num = 9.81
let numInt = parseInt(num)

console.log(numInt) // 9
```

🌕  Siz ajoyibsiz. Siz hozirgina 2-kun sinovlarini yakunladingiz va siz buyuklik sari ikki qadam oldindasiz. Endi miyangiz va mushaklaringiz uchun bir nechta mashqlarni bajaring.

## 💻 2-kun: Mashqlar

### Mashq: 1-daraja

1. O'zgaruvchini e'lon qiling va uni **'JavaScript-ning 30 kuni'** boshlang'ich qiymatiga belgilang.
2. __console.log()__ yordamida brauzer konsolida qatorni chop eting. 
3. __console.log()__ yordamida brauzer konsolida satr uzunligini(__length__) chop eting.
4. __toUpperCase()__ methodidan foydalanib, barcha satr belgilarini bosh harflarga o'zgartiring
5. __toLowerCase()__ methodi yordamida barcha qator belgilarni kichik harflarga o'zgartiring
6. __substr()__ yoki __substring()__ methodidan foydalanib, satrning birinchi so'zini kesib oling (bo'laklang).
7. *Days Of JavaScript* iborasini *30 Days Of JavaScript* -dan ajratib oling.
8. __includes()__ usuli yordamida satrda __Script__ so‘zi borligini tekshiring
9. __split()__ usuli yordamida satrni massivga ajrating
10. Split the string 30 Days Of JavaScript at the space using __split()__ method
11. 'Facebook, Google, Microsoft, Apple, IBM, Oracle, Amazon' __split__ satrni vergul orqali massivga ajrating.
12. _30 Days Of JavaScript_ ni _30 Days Of Python_ ga  __replace()__ methodi  yordamida o'zgartiring.
13. 15-index dagi belgi qanday '30 Days Of JavaScript'? __charAt()__ dan foydalaning.
14. '30 Days Of JavaScript' dagi J harfi kodi qanday? __charCodeAt()__ dan foydalaning.
15. __indexOf__ dan foydalanib 1-uchragan __a__ belgisining indexini toping? _30 Days Of JavaScript_
16. __lastIndexOf__ dan foydalanib oxirgi uchragan __a__ belgisining indexini toping? _30 Days Of JavaScript_.
17. Quyidagi gapda __because__ so‘zining birinchi kelgan o‘rnini topish uchun __indexOf__  dan foydalaning :__'You cannot end a sentence with because because because is a conjunction'__
18. Quyidagi gapda __because__ so‘zining oxirgi kelgan o‘rnini topish uchun __lastIndexOf__ dan foydalaning:__'You cannot end a sentence with because because because is a conjunction'__
19. Quyidagi gapda __because__ so‘zining birinchi kelgan o‘rnini topish uchun  __search__ dan foydalaning:__'You cannot end a sentence with because because because is a conjunction'__
20. Qator boshida va oxiridagi har qanday boʻshliqni olib tashlash uchun __trim()__ dan foydalaning. Masalan, “JavaScript 30 kuni”.
21. 30 Days Of JavaScript qatori bilan __startsWith()__ usulidan foydalaning va natijani haqiqatga aylantiring
22. 30 Days Of JavaScript qatori bilan __endsWith()__  usulidan foydalaning va natijani haqiqatga aylantiring
23. JavaScript-ning 30 kunidagi barcha __a__ larni topish uchun __match()__ usulidan foydalaning
24. __concat()__ dan foydalaning va "30 Days of" va "JavaScript" ni bitta "30 Days Of JavaScript" qatoriga birlashtiring.
25. JavaScript-ning 30 kuni-ni 2 marta chop etish uchun __repeat()__ usulidan foydalaning

### Mashq: 2-daraja

1. console.log() yordamida quyidagi bayonotni chop eting:

    ```sh
    The quote 'There is no exercise better for the heart than reaching down and lifting people up.' by John Holmes teaches us to help one another.
    ```

2. console.log() dan foydalanib, Tereza onaning quyidagi iqtibosini chop eting:

    ```sh
    "Love is not patronizing and charity isn't about pity, it is about love. Charity and love are the same -- with charity you give love, so don't just give money but reach out your hand instead."
    ```

3. '10' turi 10 ga to'liq teng yoki yo'qligini tekshiring. Agar bo'lmasa, uni aynan teng qiling.
4. parseFloat('9.8') 10 ga teng yoki yo'qligini tekshiring, agar bo'lmasa, uni 10 ga tenglashtiring.
5. Piton va jargonda "on" mavjudligini tekshiring
6. _I hope this course is not full of jargon_. Jumlada _jargon_ borligini tekshiring.
7. 0 dan 100 gacha bo'lgan tasodifiy sonni yarating.
8. 50 dan 255 gacha bo'lgan tasodifiy sonni yarating.
9. Tasodifiy raqam yordamida "JavaScript" qator belgilariga kiring.
10. Quyidagi naqshni chop etish uchun console.log() va qochish belgilaridan foydalaning.

    ```js
    1 1 1 1 1
    2 1 2 4 8
    3 1 3 9 27
    4 1 4 16 64
    5 1 5 25 125
    ```

11. Jumlani qismlarga ajratish uchun **substr** dan foydalaning, **because because because** quyidagi jumladan: **_'You cannot end a sentence with because because because is a conjunction'_**

### Mashq: 3-daraja

1. _'Love is the best thing in this world. Some found their love and some are still looking for their love.'_ Ushbu jumladagi __love__ so'zlari sonini hisoblang.
2. Hammasi sonini hisoblash uchun __match()__ dan foydalaning, __because__ quyidagi jumlada:__'You cannot end a sentence with because because because is a conjunction'__
3. Quyidagi matnni tozalang va eng tez-tez uchraydigan so'zni toping (maslahat, almashtirish va muntazam iboralardan foydalaning).

    ```js
        const sentence = '%I $am@% a %tea@cher%, &and& I lo%#ve %te@a@ching%;. The@re $is no@th@ing; &as& mo@re rewarding as educa@ting &and& @emp%o@weri@ng peo@ple. ;I found tea@ching m%o@re interesting tha@n any ot#her %jo@bs. %Do@es thi%s mo@tiv#ate yo@u to be a tea@cher!? %Th#is 30#Days&OfJavaScript &is al@so $the $resu@lt of &love& of tea&ching'
    ```

4. Quyidagi matndan raqamlarni chiqarib, shaxsning umumiy yillik daromadini hisoblang. _"U oyiga maoshdan 5000 yevro oladi, yillik 10000 evro bonus, oyiga 15000 evro onlayn kurslar."_

🎉 TABRIKLAYMAN ! 🎉

[<< 1-kun](../README.md) | [3-kun >>](../03_Day_Booleans_operators_date/03_booleans_operators_date.md)
