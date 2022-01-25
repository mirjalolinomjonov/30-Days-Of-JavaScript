<div align="center">
  <h1> 30 kunlik JavaScript: Funksiyalar</h1>
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

[<< 6-kun](../06_Day_Loops/06_day_loops.md) | [8-kun >>](../08_Day_Objects/08_day_objects.md)

![Thirty Days Of JavaScript](../images/banners/day_1_7.png)

- [📔 7-Kun](#-7-kun)
  - [Funksiyalar](#funksiyalar)
    - [Declaration funksiya](#declaration-funksiya)
    - [Parametrsiz funksiya](#parametrsiz-funksiya)
    - [Qiymat qaytaruvchi funksiya](#qiymat-qaytaruvchi-funksiya)
    - [Parametrli funksiya](#parametrli-funksiya)
    - [Ikkita parametrli funksiya](#ikkita-parametrli-funksiya)
    - [Ko'p parametrli funksiya](#kop-parametrli-funksiya)
    - [Cheksiz parametrli funksiya](#cheksiz-parametrli-funksiya)
      - [Cheksiz parametrli oddiy funksiya](#cheksiz-parametrli-oddiy-funksiya)
      - [Cheksiz parametrli strelkali funksiya](#cheksiz-parametrli-strelkali-funksiya)
    - [Anonim funksiya](#anonim-funksiya)
    - [Expression funksiya](#expression-funksiya)
    - [Self Invoking Funksiyalar](#self-invoking-funksiyalar)
    - [Strelkali funksiya](#strelkali-funksiya)
    - [Standart parametrli funksiya](#standart-parametrli-funksiya)
    - [Declaration funksiya vs Strelkali funksiya](#declaration-funksiya-vs-strelkali-funksiya)
  - [💻 Mashqlar](#-mashqlar)
    - [Mashqlar: Level 1](#mashqlar-level-1)
    - [Mashqlar: Level 2](#mashqlar-level-2)
    - [Mashqlar: Level 3](#mashqlar-level-3)

# 📔 7-Kun

## Funksiyalar

Hozirgacha biz ko'plab o'rnatilgan JavaScript funktsiyalarini ko'rdik. Ushbu bo'limda biz maxsus funktsiyalarga e'tibor qaratamiz. Funktsiya nima? Funksiyalarni yaratishni boshlashdan oldin, keling, funksiya nima ekanligini va nima uchun bizga funktsiya kerakligini tushunamiz?

Funktsiya - bu ma'lum bir vazifani bajarish uchun mo'ljallangan kod yoki dasturlash bayonotlarining qayta ishlatilishi mumkin bo'lgan blokidir. Funktsiya funktsiya kalit so'zidan keyin nom va keyin qavs () bilan e'lon qilinadi. Qavslar parametr olishi mumkin.
Agar funktsiya parametr qabul qilsa, u argument bilan chaqiriladi. Funktsiya standart parametrni ham qabul qilishi mumkin. Funktsiyaga ma'lumotni saqlash uchun funktsiya ma'lum ma'lumotlar turlarini qaytarishi kerak. Qiymatni olish uchun biz funktsiyani chaqiramiz yoki chaqiramiz.

Funktsiya kodni quyidagi ko'rinishga keltirishga xizmat qiladi:

- toza and o'qishga qulay
- qayta foydalanish mumkin
- testlashga oson 

Funktsiya bir necha usulda e'lon qilinishi yoki yaratilishi mumkin:

- _Declaration funksiya_
- _Expression funksiya_
- _Anonymous funksiya_
- _Arrow funksiya_

### Declaration funksiya

Keling, funktsiyani qanday e'lon qilishni va funktsiyani qanday chaqirishni ko'rib chiqaylik.

```js
//funksiyani parametrsiz e'lon qilish
function functionName() {
  // kod shu yerda 
}
functionName() // funksiyani nomi va qavslar bilan chaqirish
```

### Parametrsiz funksiya

Funktsiyani parametrsiz e'lon qilish mumkin.

**Misol:**

```js
//  parametrsiz funksiya, sonni kvadratga tiklash
function square() {
  let num = 2
  let sq = num * num
  console.log(sq)
}

square() // 4

// funktsiya parametrsiz
function addTwoNumbers() {
  let numOne = 10
  let numTwo = 20
  let sum = numOne + numTwo

  console.log(sum)
}

addTwoNumbers() // funktsiyani bajarish uchun uning nomi bilan chaqirish kerak
```

```js
  function printFullName (){
      let firstName = 'Asabeneh'
      let lastName = 'Yetayeh'
      let space = ' '
      let fullName = firstName + space + lastName
      console.log(fullName)
}

printFullName() // funktsiyani chaqirish
```

### Qiymat qaytaruvchi funksiya


Funktsiya qiymatlarni ham qaytarishi mumkin, agar funktsiya qiymatlarni qaytarmasa, funktsiyaning qiymati aniqlanmagan. Yuqoridagi funksiyalarni return bilan yozamiz. Bundan buyon biz qiymatni funksiyaga chop etish o‘rniga qaytaramiz.

```js
function printFullName (){
      let firstName = 'Asabeneh'
      let lastName = 'Yetayeh'
      let space = ' '
      let fullName = firstName + space + lastName
      return fullName
}
console.log(printFullName())
```

```js

  function addTwoNumbers() {
      let numOne = 2
      let numTwo = 3
      let total = numOne + numTwo
      return total

  }

console.log(addTwoNumbers())
```

### Parametrli funksiya


Funktsiyada biz turli xil ma'lumotlar turlarini (raqam, satr, mantiqiy, ob'ekt, funktsiya) parametr sifatida o'tkazishimiz mumkin.

```js
// bitta parametrli 
function functionName(parm1) {
  //kod shu yerda 
}
functionName(parm1) // funksiyani chaqirish paytida bir argument berish kerak 

function areaOfCircle(r) {
  let area = Math.PI * r * r
  return area
}

console.log(areaOfCircle(10)) // funktsiyasi bitta argument bilan chaqirilishi kerak

function square(number) {
  return number * number
}

console.log(square(10))
```

### Ikkita parametrli funksiya


```js
// ikkita parametrli funksiya
function functionName(parm1, parm2) {
  //kod shu yerda 
}
functionName(parm1, parm2) // funksiyani chaqirish paytida ikkita argument berish kerak
// Parametrsiz funktsiya kiritilmaydi, shuning uchun ruxsat beramiz parametrlari bilan
function sumTwoNumbers(numOne, numTwo) {
  let sum = numOne + numTwo
  console.log(sum)
}
sumTwoNumbers(10, 20) // funksiyalarni chaqirish

// Agar funktsiyadan hech nima qaytmasa, u ma'lumotlarni saqlamaydi, shuning uchun unda return bo'lishi kerak
function sumTwoNumbers(numOne, numTwo) {
  let sum = numOne + numTwo
  return sum
}

console.log(sumTwoNumbers(10, 20))
function printFullName(firstName, lastName) {
  return `${firstName} ${lastName}`
}
console.log(printFullName('Asabeneh', 'Yetayeh'))
```

### Ko'p parametrli funksiya


```js
// bir nechta parametrli funksiya
function functionName(parm1, parm2, parm3,...){
  //kod shu yerda 
}
functionName(parm1,parm2,parm3,...) // funksiyani chaqirish paytida 3 ta argument berish kerak


// bu funksiya massivni parametr sifatida qabul qiladi va massiv funksiyasidagi raqamlar yig'indisini qaytaradi
function sumArrayValues(arr) {
  let sum = 0;
  for (let i = 0; i < arr.length; i++) {
    sum = sum + arr[i];
  }
  return sum;
}
const numbers = [1, 2, 3, 4, 5];
    //funktsiyani chaqirish
console.log(sumArrayValues(numbers));


    const areaOfCircle = (radius) => {
      let area = Math.PI * radius * radius;
      return area;
    }
console.log(areaOfCircle(10))

```

### Cheksiz parametrli funksiya


Ba'zan biz foydalanuvchi qancha argumentlar o'tkazishini bilmaymiz. Shuning uchun biz cheksiz miqdordagi argumentlarni qabul qila oladigan funktsiyani qanday yozishni bilishimiz kerak. Buni amalga oshirish usuli funktsiya deklaratsiyasi (muntazam funktsiya) va strelkali funktsiyasi o'rtasida sezilarli farqga ega. Keling, misollarni funktsiya deklaratsiyasida ham, strelkali funktsiyasida ham ko'rib chiqaylik.

#### Cheksiz parametrli oddiy funksiya


Funktsiya deklaratsiyasi ob'ektga o'xshash funksiya ko'lamli argumentlar qatorini taqdim etadi. Funktsiyada argument sifatida berilgan har qanday narsaga funksiyalar ichidagi argumentlar ob'ektidan kirish mumkin. Keling, bir misolni ko'rib chiqaylik

 ```js
//  Keling funksiyaning Argumentlar obyektini titkilaymiz)

function sumAllNums() {
  console.log(arguments)
}

sumAllNums(1, 2, 3, 4) 
// Arguments(4) [1, 2, 3, 4, callee: ƒ, Symbol(Symbol.iterator): ƒ]

```

```js
// funksiyaning ifodalanishi

function sumAllNums() {
  let sum = 0
  for (let i = 0; i < arguments.length; i++) {
    sum += arguments[i]
  }
  return sum
}

console.log(sumAllNums(1, 2, 3, 4)) // 10
console.log(sumAllNums(10, 20, 13, 40, 10))  // 93
console.log(sumAllNums(15, 20, 30, 25, 10, 33, 40))  // 173
```

#### Cheksiz parametrli strelkali funksiya


Strelkali funksiyasi funksiya ko'p argumentlar obyektiga ega emas. Strelkali funksiyasida cheksiz miqdordagi argumentlarni qabul qiladigan funktsiyani amalga oshirish uchun biz har qanday parametr nomidan keyin `spread`  operatori`(...)`dan foydalanamiz. Funktsiyada argument sifatida berilgan har qanday narsaga strelkali funksiyasida massiv sifatida kirish mumkin.
Keling, bir misolni ko'rib chiqaylik

 ```js
// Argumentlar obyektiga kirishga ruxsat bering

const sumAllNums = (...args) => {
  // console.log(arguments), arguments ob'ekti strelkali funktsiyasida topilmadi
    // buning o'rniga biz a parametridan keyin `spread` operatoridan foydalanamiz
  console.log(args)
}

sumAllNums(1, 2, 3, 4)
// [1, 2, 3, 4]

```

```js
// funksiyaning ifodalanishi

const sumAllNums = (...args) => {
  let sum = 0
  for (const element of args) {
    sum += element
  }
  return sum
}

console.log(sumAllNums(1, 2, 3, 4)) // 10
console.log(sumAllNums(10, 20, 13, 40, 10))  // 93
console.log(sumAllNums(15, 20, 30, 25, 10, 33, 40))  // 173
```

### Anonim funksiya

Anonim funksiya yoki nomsiz funksiya

```js
const anonymousFun = function() {
  console.log(
    'I am an anonymous function and my value is stored in anonymousFun'
  )
}
```

### Expression funksiya

Ifoda funksiyalari anonim funksiyalardir. Biz nomsiz funksiya yaratganimizdan so'ng va uni o'zgaruvchiga tayinlaymiz. Funktsiyadan qiymat qaytarish uchun biz o'zgaruvchini chaqirishimiz kerak.
Quyidagi misolga qarang.

```js

// Function expression(ifodali funksiya) -> bu o'zgaruvchiga tayinlangan funksiyadir!
const square = function(n) {
  return n * n
}

console.log(square(2)) // -> 4
```

### Self Invoking Funksiyalar

O'z-o'zidan chaqiriladigan funktsiyalar - bu qiymatni qaytarish uchun chaqirilishi shart bo'lmagan anonim funktsiyalar.

```js
(function(n) {
  console.log(n * n)
})(2) // 4, lekin biz ma'lumotlarni qaytarish va saqlashni istasak, faqat chop etish o'rniga, biz quyida ko'rsatilgandek qilamiz

let squaredNum = (function(n) {
  return n * n
})(10)

console.log(squaredNum)
```

### Strelkali funksiya

Strelkali funksiya yozishga muqobildir, ammo oddiy funksiya va strelkali funksiyasi kichik farqlarga ega.

Strelkali funktsiyani e'lon qilish uchun _function_ kalit so'zi o'rniga o'q(strelkadan)dan foydalanadi . Keling, ikkala funktsiya oddiy funksiyani ham, o'q funksiyasini ham ko'rib chiqaylik.

```js
// Oddiy yoki deklaratsiya funksiyasini shunday yozamiz 
// Bu deklaratsiya funksiyasini strelkali funktsiyaga o'zgartiramiz
function square(n) {
  return n * n
}

console.log(square(2)) // 4

const square = n => {
  return n * n
}

console.log(square(2))  // -> 4

// agar kod blokida faqat bitta satr bo'lsa, uni quyidagicha yozish mumkin, ixchamgina :)
const square = n => n * n  // -> 4
```

```js
const changeToUpperCase = arr => {
  const newArr = []
  for (const element of arr) {
    newArr.push(element.toUpperCase())
  }
  return newArr
}

const countries = ['Finland', 'Sweden', 'Norway', 'Denmark', 'Iceland']
console.log(changeToUpperCase(countries))

// ["FINLAND", "SWEDEN", "NORWAY", "DENMARK", "ICELAND"]
```

```js
const printFullName = (firstName, lastName) => {
  return `${firstName} ${lastName}`
}

console.log(printFullName('Asabeneh', 'Yetayeh'))
```

Yuqoridagi funktsiya faqat return iborasiga ega, shuning uchun biz uni quyidagicha qaytarishimiz mumkin.

```js
const printFullName = (firstName, lastName) => `${firstName} ${lastName}`

console.log(printFullName('Asabeneh', 'Yetayeh'))
```

### Standart parametrli funksiya


Ba'zan biz parametrlarga standart qiymatlarni o'tkazamiz, agar biz argumentni o'tkazmasak, funktsiyani chaqirganimizda standart qiymat ishlatiladi. Funktsiya deklaratsiyasi ham, o'q funksiyasi ham standart qiymat yoki qiymatlarga ega bo'lishi mumkin.

```js
// syntax
// Funktsiyani e'lon qilish
function functionName(param = value) {
  //codes
}

// funksiyani chaqirish
functionName()
functionName(arg)
```

**Misol:**

```js
function greetings(name = 'Peter') {
  let message = `${name}, welcome to 30 Days Of JavaScript!`
  return message
}

console.log(greetings())
console.log(greetings('Asabeneh'))
```

```js
function generateFullName(firstName = 'Asabeneh', lastName = 'Yetayeh') {
  let space = ' '
  let fullName = firstName + space + lastName
  return fullName
}

console.log(generateFullName())
console.log(generateFullName('David', 'Smith'))
```

```js
function calculateAge(birthYear, currentYear = 2019) {
  let age = currentYear - birthYear
  return age
}

console.log('Age: ', calculateAge(1819))
```

```js
function weightOfObject(mass, gravity = 9.81) {
  let weight = mass * gravity + ' N' // qiymat avval satrga o'zgartirilishi kerak
    return weight
}

console.log('Weight of an object in Newton: ', weightOfObject(100)) // 9.81 gravity at the surface of Earth
console.log('Weight of an object in Newton: ', weightOfObject(100, 1.62)) // gravity at surface of Moon
```

Keling, yuqoridagi funktsiyalarni o'q funktsiyalari bilan qanday yozishimizni ko'rib chiqaylik

```js
// syntax
// funksiyaning ifodalanishi
const functionName = (param = value) => {
  //codes
}

// funksiyani chaqirish
functionName()
functionName(arg)
```

**Misol:**

```js
const greetings = (name = 'Peter') => {
  let message = name + ', welcome to 30 Days Of JavaScript!'
  return message
}

console.log(greetings())
console.log(greetings('Asabeneh'))
```

```js
const generateFullName = (firstName = 'Asabeneh', lastName = 'Yetayeh') => {
  let space = ' '
  let fullName = firstName + space + lastName
  return fullName
}

console.log(generateFullName())
console.log(generateFullName('David', 'Smith'))
```

```js

const calculateAge = (birthYear, currentYear = 2019) => currentYear - birthYear
console.log('Age: ', calculateAge(1819))
```

```js
const weightOfObject = (mass, gravity = 9.81) => mass * gravity + ' N'
  
console.log('Weight of an object in Newton: ', weightOfObject(100)) // 9.81 gravity at the surface of Earth
console.log('Weight of an object in Newton: ', weightOfObject(100, 1.62)) // gravity at surface of Moon
```

### Declaration funksiya vs Strelkali funksiya

Bu boshqa bo'limda yoritiladi

🌕 Siz ko'tarilayotgan yulduzsiz, endi siz funktsiyani bildingiz. Endi siz funktsiyalarning kuchi bilan to'lasiz. Siz hozirgina 7 kunlik sinovlarni yakunladingiz va siz buyuklik sari 7 qadam oldindasiz. Endi miyangiz va mushaklaringiz uchun bir nechta mashqlarni bajaring.

## Guvohlik
Endi Muallif va 30DaysOfJavaScript haqidagi fikrlaringizni bildirish vaqti keldi. Siz o'z fikringizni [ushbu havolada](https://testimonify.herokuapp.com/) qoldirishingiz mumkin

## 💻 Mashqlar

### Mashqlar: Level 1

1. _FullName_ funksiyasini e'lon qiling va u sizning to'liq ismingizni chop etadi.
2. FullName funksiyasini e'lon qiling va endi u parametr sifatida firstName, LastNameni oladi va u sizning to'liq ismingizni qaytaradi .
3. _addNumbers_ funksiyasini e'lon qiling va u ikkita ikkita parametr oladi va u summani qaytaradi.
4. To'rtburchakning maydoni quyidagicha hisoblanadi: _maydon_ = _uzunlik_ x _kenglik_ . _areaOfRectangle_ ni hisoblaydigan funktsiyani yozing .
5. To'rtburchakning perimetri quyidagicha hisoblanadi: _perimetri = 2x(uzunlik + kenglik)_ . _perimeterOfRectangle_ ni hisoblaydigan funktsiyani yozing .
6. To'rtburchak prizmaning hajmi quyidagicha hisoblanadi: _hajm = uzunlik x kenglik x balandlik_ . _volumeOfRectPrism_ ni hisoblaydigan funktsiyani yozing .
7. Doira maydoni quyidagicha hisoblanadi: _maydon = p x r x r_ . _AreaOfCircle_ ni hisoblaydigan funktsiyani yozing
8. Circumference of a circle is calculated as follows: _circumference = 2πr_. Write a function which calculates _circumOfCircle_
9. Density of a substance is calculated as follows:_density= mass/volume_. Write a function which calculates _density_.
10. Speed is calculated by dividing the total distance covered by a moving object divided by the total amount of time taken. Write a function which calculates a speed of a moving object, _speed_.
11. Weight of a substance is calculated as follows: _weight = mass x gravity_. Write a function which calculates _weight_.
12. Temperature in oC can be converted to oF using this formula: _oF = (oC x 9/5) + 32_. Write a function which convert oC to oF _convertCelciusToFahrenheit_.
13. Body mass index(BMI) is calculated as follows: _bmi = weight in Kg / (height x height) in m2_. Write a function which calculates _bmi_. BMI is used to broadly define different weight groups in adults 20 years old or older.Check if a person is _underweight, normal, overweight_ or _obese_ based the information given below.

    - The same groups apply to both men and women.
    - _Underweight_: BMI is less than 18.5
    - _Normal weight_: BMI is 18.5 to 24.9
    - _Overweight_: BMI is 25 to 29.9
    - _Obese_: BMI is 30 or more

14. Write a function called _checkSeason_, it takes a month parameter and returns the season:Autumn, Winter, Spring or Summer.
15. Math.max returns its largest argument. Write a function findMax that takes three arguments and returns their maximum with out using Math.max method.

    ```js
    console.log(findMax(0, 10, 5))
    10
    console.log(findMax(0, -10, -2))
    0
    ```
  
### Mashqlar: Level 2

1. Chiziqli tenglama quyidagicha hisoblanadi: _ax + by + c = 0_ . Chiziqli tenglamaning qiymatini hisoblaydigan funktsiyani yozing, _LinEquation_ ni hal qiling .
2. Kvadrat tenglama quyidagicha hisoblanadi: _ax2 + bx + c = 0_ . Kvadrat tenglamaning qiymatini yoki qiymatlarini hisoblaydigan funktsiyani yozing, _QuadEquation_ ni hal qiling .

    ```js
    console.log(solveQuadratic()) // {0}
    console.log(solveQuadratic(1, 4, 4)) // {-2}
    console.log(solveQuadratic(1, -1, -2)) // {2, -1}
    console.log(solveQuadratic(1, 7, 12)) // {-3, -4}
    console.log(solveQuadratic(1, 0, -4)) //{2, -2}
    console.log(solveQuadratic(1, -1, 0)) //{1, 0}
    ```

3. _PrintArray_ funksiya nomini e'lon qiling . U massivni parametr sifatida oladi va massivning har bir qiymatini chop etadi.
4. Bu formatda vaqtni ko'rsatadigan _showDateTime_ funksiya nomini yozing : _Date_ obyekti yordamida 08/01/2022 04:08.

    ```sh
    showDateTime()
    08/01/2022 04:08
    ```

5. Funktsiya nomini e'lon qiling _swapValues_ . Bu funksiya _x_ qiymatini _y_ ga almashtiradi.

    ```js
    swapValues(3, 4) // x => 4, y=>3
    swapValues(4, 5) // x = 5, y = 4
    ```

6. _ReverseArray_ funksiya nomini e'lon qiling . U massivni parametr sifatida oladi va massivning teskarisini qaytaradi (methoddan foydalanmang).

    ```js
    console.log(reverseArray([1, 2, 3, 4, 5]))
    //[5, 4, 3, 2, 1]
    console.log(reverseArray(['A', 'B', 'C']))
    //['C', 'B', 'A']
    ```

7. Funktsiya nomini _kapitalizeArray_ e'lon qiling . U massivni parametr sifatida oladi va - kapitallashtirilgan qatorni qaytaradi.
8. _addItem_ funksiya nomini e'lon qiling . U element parametrini oladi va elementni qo'shgandan keyin massivni qaytaradi
9. Funktsiya nomini e'lon qiling _removeItem_ . U indeks parametrini oladi va elementni olib tashlaganidan keyin massivni qaytaradi
10. _sumOfNumbers_ funksiya nomini e'lon qiling . Bu raqam parametrini oladi va u ushbu diapazondagi barcha raqamlarni qo'shadi.
11. _sumOfOdds_ funksiya nomini e'lon qiling . Bu raqam parametrini oladi va u diapazondagi barcha toq raqamlarni qo'shadi.
12. _sumOfEven_ funksiya nomini e'lon qiling . Bu raqam parametrini oladi va bu diapazondagi barcha juft raqamlarni qo'shadi.
13. funktsiya nomini e'lon qiling _evensAndOdds_ . Parametr sifatida u musbat butun sonni oladi va sondagi juft va koeffitsientlar sonini hisoblaydi.

     ```sh
     evensAndOdds(100);
     The number of odds are 50.
     The number of evens are 51.
     ```

14. Istalgan sonli argumentlarni oladigan funksiya yozing va argumentlar yig‘indisini qaytaring

     ```js
     sum(1, 2, 3) // -> 6
     sum(1, 2, 3, 4) // -> 10
     ```

15. _RandomUserIp_ ni yaratuvchi funktsiyani yozing .
16. _RandomMacAddress_ hosil qiluvchi funksiyani yozing
17. Funktsiya nomini _randomHexaNumberGenerator_ e'lon qiling . Ushbu funktsiya chaqirilganda, u tasodifiy o'n oltilik sonni hosil qiladi. Funktsiya o'n oltilik sonni qaytaradi.

     ```sh
     console.log(randomHexaNumberGenerator());
     '#ee33df'
     ```

18. _userIdGenerator_ funksiya nomini e'lon qiling . Ushbu funktsiya chaqirilganda u ettita belgi identifikatorini hosil qiladi. Funktsiya identifikatorni qaytaradi.

     ```sh
     console.log(userIdGenerator());
     41XTDbE
     ```

### Mashqlar: Level 3

1. _userIdGenerator_ funksiyasini o'zgartiring . Funktsiya nomini e'lon qiling _userIdGeneratedByUser_ . U hech qanday parametrni olmaydi, lekin _prompt()_ yordamida ikkita kirishni oladi. Kirishlardan biri belgilar soni, ikkinchisi esa yaratilishi kerak bo'lgan identifikatorlar soni.

    ```sh
    userIdGeneratedByUser()
    'kcsy2
    SMFYb
    bWmeq
    ZXOYh
    2Rgxf
    '
    userIdGeneratedByUser()
    '1GCSgPLMaBAVQZ26
    YD7eFwNQKNs7qXaT
    ycArC5yrRupyG00S
    UbGxOFI7UXSWAyKN
    dIV0SSUTgAdKwStr
    '
    ```

2. _RgbColorGenerator_ funksiya nomini yozing va u rgb ranglarini hosil qiladi.

    ```sh
    rgbColorGenerator()
    rgb(125,244,255)
    ```

3. Massivdagi istalgan sonli o‘n oltilik ranglarni qaytaradigan **_arrayOfHexaColors_** funksiyasini yozing .
4. Massivdagi istalgan sonli RGB ranglarini qaytaruvchi **_arrayOfRgbColors_** funksiyasini yozing .
5. Hexa rangini rgb ga aylantiruvchi **_convertHexaToRgb_** funksiyasini yozing va u rgb rangini qaytaradi.
6. Write a function **_convertRgbToHexa_** which converts rgb to hexa color and it returns an hexa color.
7. Write a function **_generateColors_** which can generate any number of hexa or rgb colors.

    ```js
    console.log(generateColors('hexa', 3)) // ['#a3e12f', '#03ed55', '#eb3d2b']
    console.log(generateColors('hexa', 1)) // '#b334ef'
    console.log(generateColors('rgb', 3)) // ['rgb(5, 55, 175)', 'rgb(50, 105, 100)', 'rgb(15, 26, 80)']
    console.log(generateColors('rgb', 1)) // 'rgb(33,79, 176)'
    ```

8. Call your function _shuffleArray_, it takes an array as a parameter and it returns a shuffled array
9. Call your function _factorial_, it takes a whole number as a parameter and it return a factorial of the number
10. Call your function _isEmpty_, it takes a parameter and it checks if it is empty or not
11. Call your function _sum_, it takes any number of arguments and it returns the sum.
12. Write a function called _sumOfArrayItems_, it takes an array parameter and return the sum of all the items. Check if all the array items are number types. If not give return reasonable feedback.
13. Write a function called _average_, it takes an array parameter and returns the average of the items. Check if all the array items are number types. If not give return reasonable feedback.
14. _ModifyArray_ deb nomlangan funktsiyani yozing, massivni parametr sifatida qabul qiladi va massivning beshinchi elementini o'zgartiradi va massivni qaytaradi. Agar massiv uzunligi beshdan kam bo'lsa, u "element topilmadi" ni qaytaradi.

     ```js
     console.log(modifyArray(['Avocado', 'Tomato', 'Potato','Mango', 'Lemon','Carrot']);
     ```

     ```sh
     ['Avocado', 'Tomato', 'Potato','Mango', 'LEMON', 'Carrot']
     ```

     ```js
     console.log(modifyArray(['Google', 'Facebook','Apple', 'Amazon','Microsoft',  'IBM']);
     ```

     ```sh
     ['Google', 'Facebook','Apple', 'Amazon','MICROSOFT',  'IBM']
     ```

     ```js
     console.log(modifyArray(['Google', 'Facebook','Apple', 'Amazon']);
     ```

     ```sh
       'Not Found'
     ```

15. Raqam tub son ekanligini tekshiradigan _isPrime_ funksiyasini yozing .
16. Write a functions which checks if all items are unique in the array.
17. Write a function which checks if all the items of the array are the same data type.
18. JavaScript oʻzgaruvchi nomi $ yoki _ dan tashqari maxsus belgilar yoki belgilarni qoʻllab-quvvatlamaydi. O'zgaruvchining haqiqiy yoki noto'g'ri ekanligini tekshiradigan **_isValidVariable_** funksiyasini yozing .
19. 0-9 oralig'ida ettita tasodifiy sonlar massivini qaytaradigan funksiya yozing. Barcha raqamlar noyob bo'lishi kerak.

     ```js
     sevenRandomNumbers()
     [(1, 4, 5, 7, 9, 8, 0)]
     ```

20. ReverseCountries funksiyasini yozing, u mamlakatlar massivini oladi va avval massivdan nusxa oladi va asl massivning teskarisini qaytaradi.

🎉 TABRIKLAYMAN ! 🎉

[<< 6-kun](../06_Day_Loops/06_day_loops.md) | [8-kun >>](../08_Day_Objects/08_day_objects.md)