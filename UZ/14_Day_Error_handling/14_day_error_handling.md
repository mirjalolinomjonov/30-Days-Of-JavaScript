<div align="center">
  <h1> 30 kunlik JavaScript: Xatolar bilan ishlash</h1>
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

[<< 13-kun](../13_Day_Console_object_methods/13_day_console_object_methods.md) | [15-kun>>](../15_Day_Classes/15_day_classes.md)

![Thirty Days Of JavaScript](../images/banners/day_1_14.png)

- [14-Kun](#14-kun)
  - [Xato bilan ishlash](#xato-bilan-ishlash)
    - [Error Types](#error-types)
  - [Mashqlar](#mashqlar)
    - [Mashqlar:Level 1](#mashqlarlevel-1)
    - [Mashqlar: Level 2](#mashqlar-level-2)
    - [Mashqlar:Level](#mashqlarlevel)

# 14-Kun

## Xato bilan ishlash

JavaScript erkin yozilgan tildir. Ba'zida siz aniqlanmagan o'zgaruvchiga kirishga harakat qilganingizda yoki aniqlanmagan funktsiyaga qo'ng'iroq qilganingizda ish vaqti xatosi paydo bo'ladi.

Python yoki Java-ga o'xshash JavaScript try-catch-finally bloki yordamida ish vaqtidagi xatolarni aniqlash uchun xatolarni qayta ishlash mexanizmini taqdim etadi.

```js
try {
  // xato berishi mumkin bo'lgan kod 
} catch (err) {
  // xatolik yuz berganda bajariladigan kod 
} finally {
  // xatolik yuz bergan yoki bo'lmasligidan qat'iy nazar bajariladigan kod 
}
```

**try**: try blokida xatolikka olib kelishi mumkin bo'lgan shubhali kodni o'rab oling. try iborasi bizga bajarilayotgan vaqtda xatolar uchun tekshiriladigan kod blokini aniqlash imkonini beradi.

**catch**: xatolik yuz berganda catch blokida biror narsa qilish uchun kod yozing. Catch blokida xatolik haqida ma'lumot beradigan parametrlar bo'lishi mumkin. Catch bloki xatoni qayd qilish yoki foydalanuvchiga ma'lum xabarlarni ko'rsatish uchun ishlatiladi.

**finally**: finally blok har doim xatolik yuzaga kelishidan qat'iy nazar bajariladi. Finally bloki qolgan vazifani bajarish yoki sinab ko'rish blokida xatolik yuz berishidan oldin o'zgargan o'zgaruvchilarni tiklash uchun ishlatilishi mumkin.

**Misol:**

```js
try {
  let lastName = 'Yetayeh'
  let fullName = fistName + ' ' + lastName
} catch (err) {
  console.log(err)
}
```

```sh
ReferenceError: fistName is not defined
    at <anonymous>:4:20
```

```js
try {
  let lastName = 'Yetayeh'
  let fullName = fistName + ' ' + lastName
} catch (err) {
  console.error(err) // biz console.log() yoki console.error() 
} finally {
  console.log('In any case I will be executed')
}
```

```sh
ReferenceError: fistName is not defined
    at <anonymous>:4:20
In any case it  will be executed
```

Catch bloki parametrni oladi. Catch blokiga parametr sifatida e, err yoki xatoni o'tkazish odatiy holdir. Bu parametr ob'ekt bo'lib, unda nom va xabar kalitlari mavjud. Ism va xabardan foydalanaylik.

```js
try {
  let lastName = 'Yetayeh'
  let fullName = fistName + ' ' + lastName
} catch (err) {
  console.log('Name of the error', err.name)
  console.log('Error message', err.message)
} finally {
  console.log('In any case I will be executed')
}
```

```sh
Name of the error ReferenceError
Error message fistName is not defined
In any case I will be executed
```

throw: throw bayonoti bizga maxsus xato yaratish imkonini beradi. Biz satr, raqam, mantiqiy yoki ob'ekt orqali mumkin. Istisnoni tashlash uchun throw iborasidan foydalaning. Istisno qo'yganingizda, ifoda istisnoning qiymatini belgilaydi. Quyidagilarning har biri istisno qiladi:

```js
throw 'Error2' // string qiymati bilan istisno hosil qiladi 
throw 42 // qiymati bilan istisno hosil qiladi 
throw true // qiymati bilan istisno hosil qiladi true 
throw new Error('Required') // xato ob'ektini yaratadi. Majburiy xabar
```

```js
const throwErroMisolFun = () => {
  let message
  let x = prompt('Enter a number: ')
  try {
    if (x == '') throw 'empty'
    if (isNaN(x)) throw 'not a number'
    x = Number(x)
    if (x < 5) throw 'too low'
    if (x > 10) throw 'too high'
  } catch (err) {
    console.log(err)
  }
}
throwErroMisolFun()
```

### Error Types

- ReferenceError: Noqonuniy havola yuz berdi. Agar biz e'lon qilinmagan o'zgaruvchidan foydalansak, ReferenceError tashlanadi.

```js
let firstName = 'Asabeneh'
let fullName = firstName + ' ' + lastName

console.log(fullName)
```

```sh
Uncaught ReferenceError: lastName is not defined
    at <anonymous>:2:35
```

- SyntaxError: Sintaksis xatosi yuz berdi

```js
let square = 2 x 2
console.log(square)

console.log('Hello, world")
```

```sh
Uncaught SyntaxError: Unexpected identifier
```

- TypeError: Tur xatosi yuz berdi

```js
let num = 10
console.log(num.toLowerCase())
```

```sh
Uncaught TypeError: num.toLowerCase is not a function
    at <anonymous>:2:17
```

Bular kod yozishda duch kelishi mumkin bo'lgan keng tarqalgan xatolardir. Xatolarni tushunish sizga qanday xatolarga yo'l qo'yganingizni bilishingizga yordam beradi va kodingizni tezda disk raskadrovka qilishga yordam beradi.

🌕 Siz beg'uborsiz. Endi siz xatolarni qanday hal qilishni bilar edingiz va kutilmagan foydalanuvchi kiritishlarini boshqaradigan mustahkam dastur yozishingiz mumkin. Siz hozirgina 14-kun sinovlarini yakunladingiz va siz buyuklik sari 14 qadam oldindasiz. Endi miyangiz va mushaklaringiz uchun bir nechta mashqlarni bajaring.

## Mashqlar

### Mashqlar:Level 1

Amaliyot

### Mashqlar: Level 2

Amaliyot

### Mashqlar:Level

Amaliyot

🎉 TABRIKLAYMAN ! 🎉

[<< 13-kun](../13_Day_Console_object_methods/13_day_console_object_methods.md) | [15-kun>>](../15_Day_Classes/15_day_classes.md)
