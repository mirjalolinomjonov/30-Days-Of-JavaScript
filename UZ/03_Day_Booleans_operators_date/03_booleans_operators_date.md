<div align="center">
  <h1> JavaScript-ning 30 kuni: Boolean tiplari, Operatorlar, Date(Sana)</h1>
  <a class="header-badge" target="_blank" href="https://www.linkedin.com/in/asabeneh/">
  <img src="https://img.shields.io/badge/style--5eba00.svg?label=LinkedIn&logo=linkedin&style=social">
  </a>


  <sub>Author:
  <a href="https://www.linkedin.com/in/asabeneh/" target="_blank">Asabeneh Yetayeh</a><br>
  <small> January, 2022</small>
  </sub>
</div>

[<< 2-kun](../02_Day_Data_types/02_day_data_types.md) | [4-kun >>](../04_Day_Conditionals/04_day_conditionals.md)

![Thirty Days Of JavaScript](../images/banners/day_1_3.png)

- [📔 3-Kun](#-3-kun)
  - [Boolean tiplari](#boolean-tiplari)
    - [Haqiqiy qiymatlar](#haqiqiy-qiymatlar)
    - [Yolg'on qiymatlar](#yolgon-qiymatlar)
  - [Undefined](#undefined)
  - [Null](#null)
  - [Operatorlar](#operatorlar)
    - [Belgilash operatorlari](#belgilash-operatorlari)
    - [Arifmetik operatorlar](#arifmetik-operatorlar)
    - [Taqqoslash operatorlari](#taqqoslash-operatorlari)
    - [Mantiqiy operatorlar](#mantiqiy-operatorlar)
    - [O'sish operatori](#osish-operatori)
    - [Kamaytirish operatori](#kamaytirish-operatori)
    - [Uchlik(Ternar) operatorlari](#uchlikternar-operatorlari)
    - [Operator ustunligi](#operator-ustunligi)
  - [Window methodlari](#window-methodlari)
    - [Window alert() method](#window-alert-method)
    - [Window prompt() method](#window-prompt-method)
    - [Window confirm() method](#window-confirm-method)
  - [Date Obyekti](#date-obyekti)
    - [Vaqt ob'ektini yaratish](#vaqt-obektini-yaratish)
    - [To'liq yilni olish](#toliq-yilni-olish)
    - [Oyni olish](#oyni-olish)
    - [Sanani olish](#sanani-olish)
    - [Kunni olish](#kunni-olish)
    - [Soatlarni olish](#soatlarni-olish)
    - [Daqiqalarni olish](#daqiqalarni-olish)
    - [Soniyalarni olish](#soniyalarni-olish)
    - [Vaqtni olish](#vaqtni-olish)
  - [💻 3-Kun: Mashqlar](#-day-3-exercises)
    - [Mashqlar: Level 1](#mashqlar-level-1)
    - [Mashqlar: Level 2](#mashqlar-level-2)
    - [Mashqlar: Level 3](#mashqlar-level-3)

# 📔 3-Kun

## Boolean tiplari

Boolean ma'lumotlar turi ikkita qiymatdan birini ifodalaydi: _true_ yoki _false_. Mantiqiy qiymat haqiqiy yoki noto'g'ri. Taqqoslash operatorini ishga tushirganingizda ushbu ma'lumotlar turlaridan foydalanish aniq bo'ladi.Har qanday taqqoslash haqiqiy yoki noto'g'ri bo'lgan mantiqiy qiymatni qaytaradi.

**Misol: Boolean Qiymatlari**

```js
let isLightOn = true
let isRaining = false
let isHungry = false
let isMarried = true
let truValue = 4 > 3    // true
let falseValue = 4 < 3  // false
```

Biz mantiqiy qiymatlar to'g'ri yoki noto'g'ri ekanligiga kelishib oldik.

### Haqiqiy qiymatlar

- Noldan tashqari barcha raqamlar (musbat va salbiy) haqiqiydir
- Bo'sh satr('')dan tashqari barcha satrlar haqiqiydir
- Boolean true

### Yolg'on qiymatlar

- 0
- 0n
- null
- undefined
- NaN
- Boolean false
- '', "", ``, bo'sh satr

It is good to remember those truthy values and falsy values. In later section, we will use them with conditions to make decisions.

## Undefined

O'sha haqiqat qiymatlarini va yolg'on qiymatlarini eslash yaxshidir. Keyingi bo'limda biz ularni qaror qabul qilish uchun shartlar bilan ishlatamiz.

```js
let firstName
console.log(firstName) //aniqlanmagan, chunki u hali qiymatga tayinlanmagan
```

## Null

```js
let empty = null
console.log(empty) // -> null , qiymat yo'q degan ma'noni anglatadi
```

## Operatorlar

### Belgilash operatorlari

JavaScript-dagi tenglik belgisi tayinlash operatoridir. U o'zgaruvchini tayinlash uchun foydalanadi.

```js
let firstName = 'Asabeneh'
let country = 'Finland'
```

Belgilash operatorlari

![Assignment operators](../images/assignment_operators.png)

### Arifmetik operatorlar

Arifmetik operatorlar matematik operatorlardir.

- Qo'sish(+): a + b
- Ayirish(-): a - b
- Ko'paytirish (*): a * b
- Bo'lish(/): a / b
- Modul(%): a % b
- Eksponensial(Daraja)(**): a ** b

```js
let numOne = 4
let numTwo = 3
let sum = numOne + numTwo
let diff = numOne - numTwo
let mult = numOne * numTwo
let div = numOne / numTwo
let remainder = numOne % numTwo
let powerOf = numOne ** numTwo

console.log(sum, diff, mult, div, remainder, powerOf) // 7,1,12,1.33,1, 64

```

```js
const PI = 3.14
let radius = 100          // metrda

//Doira maydonini hisoblaymiz 
const areaOfCircle = PI * radius * radius
console.log(areaOfCircle)  //  314 m


const gravity = 9.81      // in m/s2
let mass = 72             // Kilogrammda

// Ob'ektning og'irligini hisoblaymiz 
const weight = mass * gravity
console.log(weight)        // 706.32 N(Nyuton)

const boilingPoint = 100  // harorat oC, suvning qaynash nuqtasi 
const bodyTemp = 37       // tana harorati oC


// Satr interpolyatsiyasi yordamida raqamlar bilan qatorni birlashtirish
/*
 The boiling point of water is 100 oC.
 Human body temperature is 37 oC.
 The gravity of earth is 9.81 m/s2.
 */
console.log(
  `The boiling point of water is ${boilingPoint} oC.\nHuman body temperature is ${bodyTemp} oC.\nThe gravity of earth is ${gravity} m / s2.`
)
```

### Taqqoslash operatorlari

Dasturlashda biz qiymatlarni solishtiramiz, ikkita qiymatni solishtirish uchun taqqoslash operatorlaridan foydalanamiz. Biz qiymatning boshqa qiymatdan katta yoki kichik yoki teng ekanligini tekshiramiz.

![Comparison Operators](../images/comparison_operators.png)
**Misol: Taqqoslash operatorlari**

```js
console.log(3 > 2)              // true,  chunki 3 katta 2 dan 
console.log(3 >= 2)             // true,  chunki 3 katta 2 dan
console.log(3 < 2)              // false, chunki 3 katta 2 dan
console.log(2 < 3)              // true,  chunki 2 kichik 3 dan
console.log(2 <= 3)             // true,  chunki 2 kichik 3 dan
console.log(3 == 2)             // false, chunki 3 2 ga teng emas
console.log(3 != 2)             // true,  chunki 3 2 ga teng emas
console.log(3 == '3')           // true,  chunki faqat qiymatlar solishtirildi
console.log(3 === '3')          // false, chunki qiymatlar va ma'lumot turi solishtirildi
console.log(3 !== '3')          // true,  chunki qiymatlar va ma'lumot turi solishtirildi
console.log(3 != 3)             // false, chunki faqat qiymatlar solishtirildi
console.log(3 !== 3)            // false, chunki qiymatlar va ma'lumot turi solishtirildi
console.log(0 == false)         // true,  ekvivalent
console.log(0 === false)        // false, aynan bir xil emas
console.log(0 == '')            // true,  ekvivalent
console.log(0 == ' ')           // true,  ekvivalent
console.log(0 === '')           // false, aynan bir xil emas
console.log(1 == true)          // true,  ekvivalent
console.log(1 === true)         // false, aynan bir xil emas
console.log(undefined == null)  // true
console.log(undefined === null) // false
console.log(NaN == NaN)         // false, teng emas
console.log(NaN === NaN)        // false
console.log(typeof NaN)         // number

console.log('mango'.length == 'avocado'.length)  // false
console.log('mango'.length != 'avocado'.length)  // true
console.log('mango'.length < 'avocado'.length)   // true
console.log('milk'.length == 'meat'.length)      // true
console.log('milk'.length != 'meat'.length)      // false
console.log('tomato'.length == 'potato'.length)  // true
console.log('python'.length > 'dragon'.length)   // false
```

Yuqoridagi taqqoslashlarni qandaydir mantiq bilan tushunishga harakat qiling. Hech qanday mantiqsiz eslab qolish qiyin bo'lishi mumkin. JavaScript - bu qandaydir simli dasturlash tili. JavaScript kodi ishlaydi va sizga natija beradi, lekin agar siz buni yaxshi bilmasangiz, kerakli natija bo'lmasligi mumkin.

Umumiy qoida sifatida, agar qiymat == bilan to'g'ri bo'lmasa, u === bilan teng bo'lmaydi. === dan foydalanish == dan ko'ra xavfsizroqdir. Quyidagi havolada ma'lumotlar turlarini taqqoslashning to'liq ro'yxati mavjud.

### Mantiqiy operatorlar

Quyidagi belgilar umumiy mantiqiy operatorlardir:
&&(ampersand) , ||(quvur) and !(inkor).
_&&_ operatori faqat ikkita operand rost bo'lsa rost bo'ladi.
_||_ operator to'g'ri bo'ladi, agar operandlardan biri rost bo'ladi.
_!_ operator rostdan noto'g'riga va noto'g'ridan rostga rad etadi.

```js
// && ampersand operatoriga misol

const check = 4 > 3 && 10 > 5         // true && true -> true
const check = 4 > 3 && 10 < 5         // true && false -> false
const check = 4 < 3 && 10 < 5         // false && false -> false

// || quvur yoki operator, misol

const check = 4 > 3 || 10 > 5         // true  || true -> true
const check = 4 > 3 || 10 < 5         // true  || false -> true
const check = 4 < 3 || 10 < 5         // false || false -> false

// ! Inkor qilish misollari

let check = 4 > 3                     // true
let check = !(4 > 3)                  //  false
let isLightOn = true
let isLightOff = !isLightOn           // false
let isMarried = !false                // true
```

### O'sish operatori

JavaScrip-da biz o'zgaruvchida saqlangan qiymatni oshirish uchun oshirish operatoridan foydalanamiz. O'sish oldingi yoki keyingi o'sish bo'lishi mumkin. Keling, ularning har birini ko'rib chiqaylik:

1. Pre-increment (Oldindan oshirish)

```js
let count = 0
console.log(++count)        // 1
console.log(count)          // 1
```

1. Post-increment (Keyin oshirish)

```js
let count = 0
console.log(count++)        // 0
console.log(count)          // 1
```

Biz ko'pincha o'sishdan keyin foydalanamiz. Hech bo'lmaganda post-increment operatoridan qanday foydalanishni eslab qolishingiz kerak.

### Kamaytirish operatori

JavaScrip-da biz o'zgaruvchida saqlangan qiymatni kamaytirish uchun kamaytirish operatoridan foydalanamiz. Kamaytirish dekretsiyadan oldin yoki keyin bo'lishi mumkin. Keling, ularning har birini ko'rib chiqaylik:

1. Pre-decrement (Oldindan kamaytirish)

```js
let count = 0
console.log(--count) // -1
console.log(count)  // -1
```

2. Post-decrement (Keyin kamaytirish)

```js
let count = 0
console.log(count--) // 0
console.log(count)   // -1
```

### Uchlik(Ternar) operatorlari

Uchlik operator shart yozishga imkon beradi. Shartlarni yozishning yana bir usuli - uchlik operatorlardan foydalanish. Quyidagi misollarni ko'rib chiqing:

```js
let isRaining = true
isRaining
  ? console.log('You need a rain coat.')
  : console.log('No need for a rain coat.')
isRaining = false

isRaining
  ? console.log('You need a rain coat.')
  : console.log('No need for a rain coat.')
```

```sh
You need a rain coat.
No need for a rain coat.
```

```js
let number = 5
number > 0
  ? console.log(`${number} is a positive number`)
  : console.log(`${number} is a negative number`)
number = -5

number > 0
  ? console.log(`${number} is a positive number`)
  : console.log(`${number} is a negative number`)
```

```sh
5 is a positive number
-5 is a negative number
```

### Operator ustunligi

[Men sizga ushbu havoladan](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Operator_Precedence)
operator ustunligi haqida o'qishni tavsiya qilmoqchiman 

## Window methodlari

### Window alert() method

Eng boshida ko'rganingizdek, alert() usuli ma'lum bir xabar va OK tugmasi bilan ogohlantirish oynasini ko'rsatadi. Bu o'rnatilgan usul va u argumentni oladi.

```js
alert(message)
```

```js
alert('Welcome to 30DaysOfJavaScript')
```

Juda ko'p ogohlantirishdan foydalanmang, chunki u buzadi va bezovta qiladi, uni faqat sinab ko'rish uchun foydalaning.

### Window prompt() method

Oynaning so'rov usullari kirish qiymatlarini olish uchun brauzeringizda kirish bilan so'rov oynasini ko'rsatadi va kiritilgan ma'lumotlar o'zgaruvchida saqlanishi mumkin. prompt() usuli ikkita argumentni oladi. Ikkinchi dalil ixtiyoriydir.

```js
prompt('required text', 'optional text')
```

```js
let number = prompt('Enter number', 'number goes here')
console.log(number)
```

### Window confirm() method

confirm() usuli OK va Bekor qilish tugmasi bilan birga belgilangan xabarga ega dialog oynasini ko'rsatadi. Tasdiqlash oynasi ko'pincha foydalanuvchidan biror narsani bajarish uchun ruxsat so'rash uchun ishlatiladi. Window confirm() argument sifatida qatorni oladi. OK tugmasini bosish haqiqiy qiymatni beradi, Bekor qilish tugmasini bosish esa noto'g'ri qiymatni beradi.

```js
const agree = confirm('Are you sure you like to delete? ')
console.log(agree) // dialog oynasida bosgan narsangizga qarab natija rost yoki noto'g'ri bo'ladi
```

Bu barcha oyna usullari emas, biz oyna usullariga chuqur kirish uchun alohida bo'limga ega bo'lamiz.

## Date Obyekti

Vaqt muhim narsa. Biz muayyan faoliyat yoki hodisaning vaqtini bilishni yaxshi ko'ramiz. JavaScript-da joriy vaqt va sana JavaScript Date Object yordamida yaratilgan. Date obyekti yordamida biz yaratgan ob'ekt sana va vaqt bilan ishlashning ko'plab usullarini taqdim etadi.
Sana ob'ekti qiymatlaridan sana va vaqt ma'lumotlarini olish uchun foydalanadigan usullar get so'zi bilan boshlanadi , chunki u ma'lumot beradi.
_getFullYear(), getMonth(), getDate(), getDay(), getHours(), getMinutes, getSeconds(), getMilliseconds(), getTime(), getDay()_

![Date time Object](../images/date_time_object.png)

### Vaqt ob'ektini yaratish

Vaqt ob'ektini yaratganimizdan so'ng. Vaqt ob'ekti vaqt haqida ma'lumot beradi. Keling, vaqt ob'ektini yarataylik

```js
const now = new Date()
console.log(now) // 2022-yil, 04-yanvar, 00:56:41 GMT+0200 (Sharqiy Yevropa standart vaqti)
```

Biz vaqt ob'ektini yaratdik va biz jadvalda aytib o'tgan get usullari yordamida ob'ektdan istalgan sana-vaqt ma'lumotlariga kirishimiz mumkin.

### To'liq yilni olish

Keling, vaqt ob'ektidan to'liq yilni chiqaramiz yoki olamiz.

```js
const now = new Date()
console.log(now.getFullYear()) // 2022
```

### Oyni olish

Vaqt ob'ektidan oyni chiqaramiz yoki olamiz.

```js
const now = new Date()
console.log(now.getMonth()) // 0, chunki oy yanvar, oy(0-11)
```

### Sanani olish

Vaqt ob'ektidan oyning sanasini chiqaramiz yoki olamiz.

```js
const now = new Date()
console.log(now.getDate()) // 4, chunki oyning kuni 4-kun, kun(1-31)
```

### Kunni olish

Vaqt ob'ektidan haftaning kunini chiqaramiz yoki olamiz.

```js
const now = new Date()
console.log(now.getDay()) //  6, chunki kun shanba, ya'ni 7-kun 
//  yakshanba 0, dushanba 1 va shanba 6 
// ish kunini raqam sifatida olish (0-6)
```

### Soatlarni olish

Vaqt ob'ektidan soatlarni chiqaramiz yoki olamiz.

```js
const now = new Date()
console.log(now.getHours()) // 0, chunki vaqt 00:56:41
```

### Daqiqalarni olish

Vaqt obyektidan daqiqalarni chiqaramiz yoki olamiz.

```js
const now = new Date()
console.log(now.getMinutes()) // 56, chunki vaqt 00:56:41
```

### Soniyalarni olish

Vaqt ob'ektidan soniyalarni chiqaramiz yoki olamiz.


```js
const now = new Date()
console.log(now.getSeconds()) // 41, chunki vaqt 00:56:41
```

### Vaqtni olish

Bu usul 1970-yil 1-yanvardan boshlab millisekundlarda vaqtni beradi. Unix vaqti deb ham ataladi. Unix vaqtini ikki yo'l bilan olishimiz mumkin:

1. _getTime()_ dan foydalanish

```js
const now = new Date() //
console.log(now.getTime()) // 1578092201341,bu 1970-yil 1-yanvardan 2022-yil 4-yanvargacha oʻtgan soniyalar soni 00:56:41
```

1. _Date.now()_ dan foydalanish

```js
const allSeconds = Date.now() //
console.log(allSeconds) // 1578092201341, bu 1970-yil 1-yanvardan 2022-yil 4-yanvargacha oʻtgan soniyalar soni 00:56:41

const timeInSeconds = new Date().getTime()
console.log(allSeconds == timeInSeconds) // true
```

Keling, ushbu qiymatlarni inson o'qiy oladigan vaqt formatiga formatlaylik. Misol:
**Misol:**

```js
const now = new Date()
const year = now.getFullYear() // yil ni qaytaradi
const month = now.getMonth() + 1 // oy(0 - 11) ni qaytaradi
const date = now.getDate() // kun (1 - 31) ni qaytaradi
const hours = now.getHours() // soat (0 - 23) ni qaytaradi
const minutes = now.getMinutes() // daqiqa (0 -59) ni qaytaradi

console.log(`Natija: ${date}/${month}/${year} ${hours}:${minutes}`) // Natija: 4/1/2022 0:56
```

🌕  Sizda cheksiz energiya bor. Siz hozirgina 3-kun sinovlarini yakunladingiz va siz buyuklik sari uch qadam oldindasiz. Endi miyangiz va mushaklaringiz uchun bir nechta mashqlarni bajaring.

## 💻 3-Kun: Mashqlar

### Mashqlar: Level 1

1. FirstName, familiya, mamlakat, shahar, yosh, isMarried, year o'zgaruvchisini e'lon qiling va unga qiymat bering va har xil ma'lumotlar turlarini tekshirish uchun typeof operatoridan foydalaning.
2. "10" turi 10 ga teng ekanligini tekshiring
3. parseInt('9.8') 10 ga teng ekanligini tekshiring
4. Mantiqiy qiymat haqiqiy yoki noto'g'ri.
   1. Haqiqiy qiymatni ta'minlaydigan uchta JavaScript bayonotini yozing.
   2. Noto'g'ri qiymat beruvchi uchta JavaScript bayonotini yozing.

5. Console.log() dan foydalanmasdan avval quyidagi taqqoslash ifodasi natijasini aniqlang. Natijani aniqlaganingizdan so'ng, uni console.log() yordamida tasdiqlang.
   1. 4 > 3
   2. 4 >= 3
   3. 4 < 3
   4. 4 <= 3
   5. 4 == 4
   6. 4 === 4
   7. 4 != 4
   8. 4 !== 4
   9. 4 != '4'
   10. 4 == '4'
   11. 4 === '4'
   12. Python va jargon uzunligini toping va noto'g'ri taqqoslash bayonotini yarating.

6. Console.log() dan foydalanmasdan avval quyidagi ifodalarning natijasini aniqlang. Natijani aniqlaganingizdan so'ng, uni console.log() yordamida tasdiqlang.
   1. 4 > 3 && 10 < 12
   2. 4 > 3 && 10 > 12
   3. 4 > 3 || 10 < 12
   4. 4 > 3 || 10 > 12
   5. !(4 > 3)
   6. !(4 < 3)
   7. !(false)
   8. !(4 > 3 && 10 < 12)
   9. !(4 > 3 && 10 > 12)
   10. !(4 === '4')
   11. Ajdaho va pitonda ham "on" yo'q

7. Quyidagi amallarni bajarish uchun Date obyektidan foydalaning
   1. Bugun qaysi yil?
   2. Raqam sifatida bugungi oy qaysi?
   3. Bugun qaysi sana?
   4. Raqam sifatida bugun qaysi kun?
   5. Hozir soat necha?
   6. Hozir daqiqalar qancha?
   7. 1970-yil 1-yanvardan hozirgacha oʻtgan soniyalar sonini aniqlang.

### Mashqlar: Level 2

1. Foydalanuvchiga uchburchakning asosi va balandligini kiritish va uchburchakning maydonini hisoblashni taklif qiladigan skriptni yozing (maydon = 0,5 x b x h).

   ```sh
   Enter base: 20
   Enter height: 10
   The area of the triangle is 100
   ```

2. Foydalanuvchiga uchburchakning a, b tomoni va c tomonini kiritish va uchburchak perimetrini hisoblashni taklif qiladigan skript yozing (perimetri = a + b + c)

   ```sh
   Enter side a: 5
   Enter side b: 4
   Enter side c: 3
   The perimeter of the triangle is 12
   ```

3. So'rov yordamida uzunlik va kenglikni oling va to'rtburchaklar maydonini hisoblang (maydon = uzunlik x kenglik va to'rtburchak perimetri (perimetri = 2 x (uzunlik + kenglik)))
4. Tezkor yordamida radiusni oling va aylananing maydonini (maydon = pi xrxr) va aylana atrofini (c = 2 x pi xr) hisoblang, bunda pi = 3.14.
5. y = 2x -2 ning qiyaligini, x-kesishmasini va y-kesishmasini hisoblang
6. Nishab (m = y2-y1/x2-x1). (2, 2) nuqta va (6,10) nuqta orasidagi qiyalikni toping.
7. Yuqoridagi ikkita savolning qiyaligini solishtiring.
8. y qiymatini hisoblang (y = x^2 + 6x + 9). Turli xil x qiymatlaridan foydalanishga harakat qiling va qaysi x qiymatida y 0 ekanligini aniqlang.
9. Foydalanuvchiga soat va soatiga baho kiritishni taklif qiladigan skript yozing. Shaxsning ish haqini hisoblang?

    ```sh
    Enter hours: 40
    Enter rate per hour: 28
    Your weekly earning is 1120
    ```

10. Agar ismingiz uzunligi 7 dan katta bo'lsa, ismingiz uzun, yoki ismingiz qisqa deb ayting.
11. Ismingiz uzunligi va familiyangiz uzunligini solishtiring va siz ushbu natijani olishingiz kerak.

     ```js
     let firstName = 'Asabeneh'
     let lastName = 'Yetayeh'
     ```

     ```sh
     Your first name, Asabeneh is longer than your family name, Yetayeh
     ```

12. Ikkita _myAge_ va _yourAge_ oʻzgaruvchilarini eʼlon qiling va ularga boshlangʻich qiymatlarni hamda myAge va yourAge ni belgilang.

    ```js
    let myAge = 250
    let yourAge = 25
    ```

    ```sh
    I am 225 years older than you.
    ```

13. Tezkor foydalanuvchi tug'ilgan yilini oling va agar foydalanuvchi 18 yoki undan katta bo'lsa, foydalanuvchiga ma'lum bir yil kutishni aytmasa, unga haydashga ruxsat bering.

     ```sh

     Enter birth year: 1995
     You are 25. You are old enough to drive

     Enter birth year: 2005
     You are 15. You will be allowed to drive after 3 years.
     ```

14. Foydalanuvchiga yillar sonini kiritishni taklif qiladigan skript yozing. Inson qancha soniya yashashi mumkinligini hisoblang. Aytaylik, kimdir bor-yo'g'i yuz yil yashaydi

    ```sh
    Enter number of years you live: 100
    You lived 3153600000 seconds.
    ```

15. Sana vaqti ob'ektidan foydalanib, odam o'qiy oladigan vaqt formatini yarating
    1. YYYY-MM-DD HH:mm
    2. DD-MM-YYYY HH:mm
    3. DD/MM/YYYY HH:mm

### Mashqlar: Level 3

1. Sana vaqti ob'ektidan foydalanib, odam o'qiy oladigan vaqt formatini yarating. Soat va daqiqa har doim ikki raqamdan iborat bo'lishi kerak (7 soat 07 va 5 daqiqa 05 bo'lishi kerak)
   1. YYY-MM-DD HH:mm Masalan. 2012-01-02 07:05

[<< 2-kun](../02_Day_Data_types/02_day_data_types.md) | [4-kun >>](../04_Day_Conditionals/04_day_conditionals.md)
