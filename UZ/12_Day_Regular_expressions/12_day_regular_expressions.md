<div align="center">
  <h1> JavaScript-ning 30 kuni: Muntazam Ifodalar</h1>
  <a class="header-badge" target="_blank" href="https://www.linkedin.com/in/asabeneh/">
  <img src="https://img.shields.io/badge/style--5eba00.svg?label=LinkedIn&logo=linkedin&style=social">
  </a>


  <sub>Author:
  <a href="https://www.linkedin.com/in/asabeneh/" target="_blank">Asabeneh Yetayeh</a><br>
  <small> January, 2022</small>
  </sub>
</div>

[<< 11-kun](../11_Day_Destructuring_and_spreading/11_day_destructuring_and_spreading.md) | [13-kun>>](../13_Day_Console_object_methods/13_day_console_object_methods.md)

![Thirty Days Of JavaScript](../images/banners/day_1_12.png)

- [📘 12-Kun](#-12-kun)
  - [Muntazam Ifodalar](#muntazam-ifodalar)
    - [RegExp parametrlari](#regexp-parametrlari)
      - [Pattern](#pattern)
      - [Bayroqlar](#bayroqlar)
    - [RegExp Constructor yordamida pattern yaratish](#regexp-constructor-yordamida-pattern-yaratish)
    - [RegExp Konstruktorisiz pattern yaratish](#regexp-konstruktorisiz-pattern-yaratish)
    - [RegExpp ob'ekt usullari](#regexpp-obekt-usullari)
      - [Moslikka tekshirish](#moslikka-tekshirish)
      - [Barcha moslikni o'z ichiga olgan massiv](#barcha-moslikni-oz-ichiga-olgan-massiv)
      - [Berilgan satrni almashtirish](#berilgan-satrni-almashtirish)
    - [Kvadrat qavs](#kvadrat-qavs)
    - [RegExp dagi Escape belgisi(\)](#regexp-dagi-escape-belgisi)
    - [Bir yoki bir necha marta (+)](#bir-yoki-bir-necha-marta-)
    - [Davr(.)](#davr)
    - [Nol yoki ko'p marta (*)](#nol-yoki-kop-marta-)
    - [Nol yoki bir marta(?)](#nol-yoki-bir-marta)
    - [RegExp-dagi kvant](#regexp-dagi-kvant)
    - [Cart ^](#cart-)
    - [Aniq moslik](#aniq-moslik)
  - [💻 Mashqlar](#-mashqlar)
    - [Mashqlar: Level 1](#mashqlar-level-1)
    - [Mashqlar: Level 2](#mashqlar-level-2)
    - [Mashqlar: Level 3](#mashqlar-level-3)

# 📘 12-Kun

## Muntazam Ifodalar

Muntazam ifoda yoki RegExp kichik dasturlash tili bo'lib, u ma'lumotlarda naqsh topishga yordam beradi. RegExp-dan boshqa ma'lumotlar turlarida qandaydir naqsh mavjudligini tekshirish uchun foydalanish mumkin. JavaScript-da RegExp-dan foydalanish uchun biz RegExp konstruktoridan foydalanamiz yoki ikkita oldinga qiyshiq chiziqdan keyin bayroq yordamida RegExp naqshini e'lon qilishimiz mumkin. Biz ikkita usulda naqsh yaratishimiz mumkin.

Satrni e'lon qilish uchun biz bitta qo'shtirnoqdan foydalanamiz, oddiy iborani e'lon qilish uchun ikkita qo'shtirnoq qo'yamiz va ixtiyoriy bayroqdan foydalanamiz. Bayroq g, i, m, s, u yoki y bo'lishi mumkin.

### RegExp parametrlari

Muntazam ifoda ikkita parametrni oladi. Bitta talab qilinadigan qidiruv namunasi va ixtiyoriy bayroq.

#### Pattern

Naqsh matn yoki qandaydir o'xshashlik bo'lgan naqshning har qanday shakli bo'lishi mumkin. Misol uchun, elektron pochtadagi spam so'zi biz e-pochtada qidirmoqchi bo'lgan namuna bo'lishi mumkin yoki telefon raqami formatidagi raqam bizning qiziqishimiz bo'lishi mumkin.

#### Bayroqlar

Bayroqlar muntazam ifodadagi ixtiyoriy parametrlar bo'lib, qidiruv turini aniqlaydi. Keling, ba'zi bayroqlarni ko'rib chiqaylik:

- g: bu global bayroq bo'lib, butun matnda naqsh izlashni anglatadi
- i: katta-kichik harflarni sezmaydigan bayroq (u kichik va katta harflarni qidiradi)
- m: ko'p qatorli

### RegExp Constructor yordamida pattern yaratish

Muntazam ifodani global bayroqsiz va katta-kichik harflarga sezgir bo'lmagan bayroqsiz e'lon qilish.

```js
// bayroqsiz 
let pattern = 'love'
let regEx = new RegExp(pattern)
```

Global bayroq va katta-kichik harflarga sezgir bo'lmagan bayroq bilan muntazam ifodani e'lon qilish.

```js
let pattern = 'love'
let flag = 'gi'
let regEx = new RegExp(pattern, flag)
```

RegExp obyekti yordamida regex naqshini e'lon qilish. RegExp konstruktori ichida naqsh va bayroqni yozish

```js
let regEx = new RegExp('love','gi')
```

### RegExp Konstruktorisiz pattern yaratish

Global bayroq va katta-kichik harflarga sezgir bo'lmagan bayroq bilan muntazam ifodani e'lon qilish.

```js
let regEx= /love/gi
```

Yuqoridagi oddiy ibora biz RegExp konstruktori bilan yaratganimiz bilan bir xil

```js
let regEx= new RegExp('love','gi')
```

### RegExpp ob'ekt usullari

Keling, RegExp usullarini ko'rib chiqaylik

#### Moslikka tekshirish

*test()*: Satrdagi moslik uchun testlar. Bu rost yoki yolg'onni qaytaradi.

```js
const str = 'I love JavaScript'
const pattern = /love/
const result = pattern.test(str)
console.log(result)
```

```sh
true
```

#### Barcha moslikni o'z ichiga olgan massiv

*match()*:Barcha mosliklarni, jumladan qoʻlga olish guruhlarini oʻz ichiga olgan massivni qaytaradi yoki moslik topilmasa null. Agar biz global bayroqdan foydalanmasak, match() naqsh, indeks, kiritish va guruhni o'z ichiga olgan massivni qaytaradi.

```js
const str = 'I love JavaScript'
const pattern = /love/
const result = str.match(pattern)
console.log(result)
```

```sh
["love", index: 2, input: "I love JavaScript", groups: undefined]
```

```js
const str = 'I love JavaScript'
const pattern = /love/g
const result = str.match(pattern)
console.log(result)
```

```sh
["love"]
```

*search()*: Satrdagi moslikni tekshiradi. U moslik indeksini qaytaradi yoki agar qidiruv muvaffaqiyatsiz bo'lsa -1.

```js
const str = 'I love JavaScript'
const pattern = /love/g
const result = str.search(pattern)
console.log(result)
```

```sh
2
```

#### Berilgan satrni almashtirish

*replace()*: satrdagi moslikni qidirishni amalga oshiradi va mos keladigan pastki qatorni almashtiriladigan pastki qator bilan almashtiradi.

Ya'ni bu misolda `Python` yoki `python` so'zi mavjud bo'lsa uni `JavaScript` ga almashtiradi. 

```js
const txt = 'Python is the most beautiful language that a human begin has ever created.\
I recommend python for a first programming language'

matchReplaced = txt.replace(/Python|python/, 'JavaScript')
console.log(matchReplaced)
```

```sh
JavaScript is the most beautiful language that a human begin has ever created.I recommend python for a first programming language
```

```js
const txt = 'Python is the most beautiful language that a human begin has ever created.\
I recommend python for a first programming language'

matchReplaced = txt.replace(/Python|python/g, 'JavaScript')
console.log(matchReplaced)
```

```sh
JavaScript is the most beautiful language that a human begin has ever created.I recommend JavaScript for a first programming language
```

```js
const txt = 'Python is the most beautiful language that a human begin has ever created.\
I recommend python for a first programming language'

matchReplaced = txt.replace(/Python/gi, 'JavaScript')
console.log(matchReplaced)
```

```sh
JavaScript is the most beautiful language that a human begin has ever created.I recommend JavaScript for a first programming language
```

```js

const txt = '%I a%m te%%a%%che%r% a%n%d %% I l%o%ve te%ach%ing.\
T%he%re i%s n%o%th%ing as m%ore r%ewarding a%s e%duc%at%i%ng a%n%d e%m%p%ow%er%ing \
p%e%o%ple.\
I fo%und te%a%ching m%ore i%n%t%er%%es%ting t%h%an any other %jobs.\
D%o%es thi%s m%ot%iv%a%te %y%o%u to b%e a t%e%a%cher.'

matches = txt.replace(/%/g, '')
console.log(matches)  
```

```sh
I am teacher and  I love teaching.There is nothing as more rewarding as educating and empowering people.I found teaching more interesting than any other jobs.Does this motivate you to be a teacher.
```

* []:  Belgilar toʻplami
  * [a-c] a yoki b yoki c degan ma'noni anglatadi
  * [a-z] a dan z gacha boʻlgan har qanday harfni bildiradi
  * [A-Z] A dan Z gacha boʻlgan har qanday belgini bildiradi
  * [0-3] 0 yoki 1 yoki 2 yoki 3 degan maʼnoni anglatadi
  * [0-9] 0 dan 9 gacha bo'lgan istalgan sonni bildiradi
  * [A-Za-z0-9] a dan z gacha, A dan Z gacha, 0 dan 9 gacha bo'lgan har qanday belgi
* \\:  maxsus belgilardan qochish uchun foydalanadi
  * \d anglatadi: satrda raqamlar mavjud bo'lgan joyga mos keladi (0-9 gacha raqamlar)
  * \D anglatadi: satrda raqamlar bo'lmagan joyda mos keladi
* . : yangi satr belgisidan tashqari har qanday belgi (\n)
* ^: bilan boshlanadi
  * r'^substring' masalan, r'^love', love so'zi bilan boshlangan gap
  * r'[^abc] anglatadi: a emas, b emas, c emas.
* $: bilan tugaydi
  * r'substring$'  masalan, r'love$', gap love so'zi bilan tugaydi
* *: nol yoki undan ortiq marta
  * r'[a]*' ixtiyoriy degan ma'noni anglatadi yoki u ko'p marta sodir bo'lishi mumkin.
* +: bir yoki bir necha marta
  * r'[a]+' kamida bir yoki bir necha marta ma'noni anglatadi
* ?: nol yoki bir marta
  *  r'[a]?' nol marta yoki bir marta degani
* {3}: Aynan 3 ta belgi
* {3,}: kamida 3 ta belgi
* {3,8}: 3 dan 8 gacha belgilar
* |: yoki
  * r'apple|banana' apple yoki banana degan ma'noni anglatadi
* (): Qamrab olish va guruhlash

![Regular Expression cheat sheet](../images/regex.png)

Yuqoridagi meta-belgilarni aniqlashtirish uchun misoldan foydalanamiz

### Kvadrat qavs

Kichik va katta harflarni kiritish uchun kvadrat qavsdan foydalanamiz

```js
const pattern = '[Aa]pple' // bu kvadrat qavs A yoki a ekanligini anglatadi
const txt = 'Apple and banana are fruits. An old cliche says an apple a day a doctor way has been replaced by a banana a day keeps the doctor far far away. '
const matches = txt.match(pattern)

console.log(matches)  
```

```sh
["Apple", index: 0, input: "Apple and banana are fruits. An old cliche says an…by a banana a day keeps the doctor far far away. ", groups: undefined]

```

```js
const pattern = /[Aa]pple/g // bu kvadrat qavs A yoki a ekanligini anglatadi
const txt = 'Apple and banana are fruits. An old cliche says an apple a day a doctor way has been replaced by a banana a day keeps the doctor far far away. '
const matches = txt.match(pattern)

console.log(matches)  
```

```sh
["Apple", "apple"]
```

Agar biz _banana_ ni qidirmoqchi bo'lsak, naqshni quyidagicha yozamiz:

```js
const pattern = /[Aa]pple|[Bb]anana/g // bu kvadrat qavs A yoki a ekanligini anglatadi
const txt = 'Apple and banana are fruits. An old cliche says an apple a day a doctor way has been replaced by a banana a day keeps the doctor far far away. Banana is easy to eat too.'
const matches = txt.match(pattern)

console.log(matches)  
```

```sh
["Apple", "banana", "apple", "banana", "Banana"]
```

Kvadrat qavs yoki operatordan foydalanib, biz _Olma_, _olma_, _Banan_ va _banan_ larni ajratib olamiz.

### RegExp dagi Escape belgisi(\)

```js
const pattern = /\d/g  // d - bu raqamlarni bildiruvchi maxsus belgi 
const txt = 'This regular expression example was made in January 12,  2022.'
const matches = txt. match(pattern)

console.log(matches)  // ["1", "2", "2", "0", "2", "0"], bu biz xohlagan narsa emas
```

```js
const pattern = /\d+/g  // d - bu maxsus belgi, ya'ni raqamlar 
const txt = 'This regular expression example was made in January 12,  2022.'
const matches = txt. match(pattern)

console.log(matches)  // ["12", "2022"], bu biz xohlagan narsa emas
```

### Bir yoki bir necha marta (+)

```js
const pattern = /\d+/g  //  d - bu raqamlarni bildiruvchi maxsus belgi 
const txt = 'This regular expression example was made in January 12,  2022.'
const matches = txt. match(pattern)
console.log(matches)  // ["12", "2022"], bu biz xohlagan narsa emas
```

### Davr(.)

```js
const pattern = /[a]./g  // bu kvadrat qavs a va . ni bildiradi. yangi qatordan tashqari har qanday belgini bildiradi
const txt = 'Apple and banana are fruits'
const matches = txt.match(pattern)

console.log(matches)  // ["an", "an", "an", "a ", "ar"]
```

```js
const pattern = /[a].+/g  // . har qanday belgi, + har qanday belgi bir yoki bir necha marta 
const txt = 'Apple and banana are fruits'
const matches = txt.match(pattern)

console.log(matches)  // ['and banana are fruits']
```

### Nol yoki ko'p marta (*)

Nol yoki ko'p marta. Shakl paydo bo'lmasligi yoki ko'p marta paydo bo'lishi mumkin.

```js

const pattern = /[a].*/g  //. har qanday belgi, + har qanday belgi bir yoki bir necha marta 
const txt = 'Apple and banana are fruits'
const matches = txt.match(pattern)

console.log(matches)  // ['and banana are fruits']

```

### Nol yoki bir marta(?)

Nol yoki bir marta. Shakl paydo bo'lmasligi yoki bir marta paydo bo'lishi mumkin.

```js
const txt = 'I am not sure if there is a convention how to write the word e-mail.\
Some people write it email others may write it as Email or E-mail.'
const pattern = /[Ee]-?mail/g  // ? ixtiyoriy ekanligini anglatadi
matches = txt.match(pattern)

console.log(matches)  // ["e-mail", "email", "Email", "E-mail"]

```

### RegExp-dagi kvant

Biz jingalak qavsdan foydalanib, matndan izlayotgan pastki qator uzunligini belgilashimiz mumkin. Tasavvur qilaylik, biz ularning uzunligi 4 ta belgidan iborat bo'lgan pastki qatorga qiziqamiz

```js
const txt = 'This regular expression example was made in December 6,  2019.'
const pattern = /\d{4}/g  // aniq to'rt marta 
const matches = txt.match(pattern)
console.log(matches)  // ['2019']
```

```js
const txt = 'This regular expression example was made in December 6,  2019.'
const pattern = /\d{1,4}/g   // 1 dan 4 gacha 
const matches = txt.match(pattern)
console.log(matches)  // ['6', '2019']
```

### Cart ^

- bilan boshlanadi
  
```js
const txt = 'This regular expression example was made in December 6,  2019.'
const pattern = /^This/ // ^ bilan boshlanadi degan ma'noni anglatadi 
const matches = txt.match(pattern)
console.log(matches)  // ['This']
```

- Inkor qilish

```js
const txt = 'This regular expression example was made in December 6,  2019.'
const pattern = /[^A-Za-z,. ]+/g  // ^to'plamdagi belgi inkorni anglatadi, A dan Zgacha emas, a dan z gacha, bo'sh joy, vergul yo'q, davr 
const matches = txt.match(pattern)
console.log(matches)  // ["6", "2019"]
```

### Aniq moslik

Unda ^ boshlanishi va $ oxiri bo'lishi kerak.

```js
let pattern = /^[A-Z][a-z]{3,12}$/;
let name = 'Asabeneh';
let result = pattern.test(name)

console.log(result) // true
```

🌕 Siz uzoqqa ketyapsiz. Davom eting! Endi siz muntazam ifoda kuchiga egasiz. Siz har qanday matnni ajratib olish va tozalash imkoniyatiga egasiz va tuzilmagan ma'lumotlardan ma'no yaratishingiz mumkin. Siz hozirgina 12 kunlik sinovlarni yakunladingiz va siz buyuklik sari 12 qadam oldindasiz. Endi miyangiz va mushaklaringiz uchun bir nechta mashqlarni bajaring.

## 💻 Mashqlar

### Mashqlar: Level 1

1. Quyidagi matndan shaxsning umumiy yillik daromadini hisoblang. "U oyiga maoshdan 4000 yevro, yillik 10000 evro bonus, oyiga 5500 evro onlayn kurslar oladi."
2. Ba'zi zarrachalarning gorizontal x o'qidagi o'rni -12, -4, -3 va -1 manfiy yo'nalishda, 0 ga kelib, 4 va 8 musbat yo'nalishda. Ushbu raqamlarni ajratib oling va ikkita eng uzoq zarrachalar orasidagi masofani toping.

```js
points = ['-1', '2', '-4', '-3', '-1', '0', '4', '8']
sortedPoints =  [-4, -3, -1, -1, 0, 2, 4, 8]
distance = 12
```

1. String haqiqiy JavaScript oʻzgaruvchisi ekanligini aniqlaydigan naqsh yozing

    ```sh
    is_valid_variable('first_name') # True
    is_valid_variable('first-name') # False
    is_valid_variable('1first_name') # False
    is_valid_variable('firstname') # True
    ```

### Mashqlar: Level 2

1. Satrdan eng tez-tez uchraydigan o'nta so'zni oladigan **tenMostFrequentWords** funksiyasini yozing ?

    ```js
        paragraph = `I love teaching. If you do not love teaching what else can you love. I love Python if you do not love something which can give you all the capabilities to develop an application what else can you love.`
        console.log(tenMostFrequentWords(paragraph))
    ```

    ```sh
        [
        {word:'love', count:6},
        {word:'you', count:5},
        {word:'can', count:3},
        {word:'what', count:2},
        {word:'teaching', count:2},
        {word:'not', count:2},
        {word:'else', count:2},
        {word:'do', count:2},
        {word:'I', count:2},
        {word:'which', count:1},
        {word:'to', count:1},
        {word:'the', count:1},
        {word:'something', count:1},
        {word:'if', count:1},
        {word:'give', count:1},
        {word:'develop',count:1},
        {word:'capabilities',count:1},
        {word:'application', count:1},
        {word:'an',count:1},
        {word:'all',count:1},
        {word:'Python',count:1},
        {word:'If',count:1}]
    ```

    ```js
    console.log(tenMostFrequentWords(paragraph, 10))
    ```

    ```sh
   [{word:'love', count:6},
    {word:'you', count:5},
    {word:'can', count:3},
    {word:'what', count:2},
    {word:'teaching', count:2},
    {word:'not', count:2},
    {word:'else', count:2},
    {word:'do', count:2},
    {word:'I', count:2},
    {word:'which', count:1}
    ]
    ```

### Mashqlar: Level 3

1. Matnni tozalaydigan funksiya yozing. Quyidagi matnni tozalang. Tozalashdan so'ng, satrda eng ko'p uchraydigan uchta so'zni hisoblang.
  
  ```js
    sentence = `%I $am@% a %tea@cher%, &and& I lo%#ve %tea@ching%;. There $is nothing; &as& mo@re rewarding as educa@ting &and& @emp%o@wering peo@ple. ;I found tea@ching m%o@re interesting tha@n any other %jo@bs. %Do@es thi%s mo@tivate yo@u to be a tea@cher!?`

   console.log(cleanText(sentence))
   ```

   ```sh
    I am a teacher and I love teaching There is nothing as more rewarding as educating and empowering people I found teaching more interesting than any other jobs Does this motivate you to be a teacher
   ```
1. Write a function which find the most frequent words. After cleaning, count three most frequent words in the string.

    ```js
    console.log(mostFrequentWords(cleanedText))
    [{word:'I', count:3}, {word:'teaching', count:2}, {word:'teacher', count:2}]
    ```


🎉 TABRIKLAYMAN  ! 🎉


[<< 11-kun](../11_Day_Destructuring_and_spreading/11_day_destructuring_and_spreading.md) | [13-kun>>](../13_Day_Console_object_methods/13_day_console_object_methods.md)
