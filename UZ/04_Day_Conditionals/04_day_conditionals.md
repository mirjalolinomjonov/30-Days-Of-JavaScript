<div align="center">
  <h1> 30 kunlik JavaScript: Conditionals (Shartlar)</h1>
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

[<< 3-kun](../03_Day_Booleans_operators_date/03_booleans_operators_date.md) | [5-kun >>](../05_Day_Arrays/05_day_arrays.md)

![Thirty Days Of JavaScript](../images/banners/day_1_4.png)

- [📔 4-Kun](#-4-kun)
  - [Conditionals (Shartlar)](#conditionals-shartlar)
    - [If](#if)
    - [If Else](#if-else)
    - [If Else if Else](#if--else-if-else)
    - [Switch](#switch)
    - [Ternar Operatorlar](#ternar-operatorlar)
  - [💻 Mashqlar](#-mashqlar)
    - [Mashqlar: Level 1](#mashqlar-level-1)
    - [Mashqlar: Level 2](#mashqlar-level-2)
    - [Mashqlar: Level 3](#mashqlar-level-3)

# 📔 4-Kun

## Conditionals (Shartlar)

Shartli bayonotlar turli shartlarga asoslangan qarorlar qabul qilish uchun ishlatiladi. Odatiy bo'lib, JavaScript skriptidagi bayonotlar yuqoridan pastgacha ketma-ket bajariladi. Agar ishlov berish mantig'i shuni talab qilsa, ketma-ket bajarilish jarayoni ikki yo'l bilan o'zgartirilishi mumkin:

- Shartli bajarish: agar ma'lum bir ifoda to'g'ri bo'lsa, bir yoki bir nechta bayonotlar bloki bajariladi.
- Takroriy bajarilish: bir yoki bir nechta bayonotlar bloki ma'lum bir ifoda to'g'ri bo'lsa, takroriy bajariladi. Ushbu bo'limda if , else , else if iboralarini ko'rib chiqamiz . Oldingi bo'limlarda biz o'rgangan taqqoslash va mantiqiy operatorlar bu erda foydali bo'ladi.

Shartlar quyidagi usullar yordamida amalga oshirilishi mumkin:


- if
- if else
- if else if else
- switch
- uchlik operator

### If

JavaScript va boshqa dasturlash tillarida _if_ kalit so'zi shartning to'g'ri yoki yo'qligini tekshirish va blok kodini bajarish uchun ishlatiladi. If shartini yaratish uchun bizga _if_ kalit so'zi, qavs ichidagi shart va jingalak qavs ({}) ichidagi kod bloki kerak bo'ladi .

```js
// sintaksis
if (condition) {
  //kodning bu qismi haqiqat sharti uchun ishlaydi
}
```

**Misol:**

```js
let num = 3
if (num > 0) {
  console.log(`${num} musbat son`)
}
//  3 musbat son
```

Yuqoridagi shart misolida ko'rib turganingizdek, 3 0 dan katta, shuning uchun u ijobiy sondir. Shart to'g'ri edi va kod bloki bajarildi. Biroq, agar shart noto'g'ri bo'lsa, biz hech qanday natijani ko'ra olmaymiz.

```js
let isRaining = true
if (isRaining) {
  console.log('Yomg\'ir paltongizni olishni unutmang.')
}
```

Xuddi shu narsa ikkinchi shartga ham tegishli, agar isRaining noto'g'ri bo'lsa, if bloki bajarilmaydi va biz hech qanday chiqishni ko'rmayapmiz. Noto'g'ri holatning natijasini ko'rish uchun bizda boshqa blok bo'lishi kerak .

### If Else

Agar shart rost bo'lsa, birinchi blok bajariladi, bo'lmasa boshqa shart bajariladi.

```js
// sintaksis 
if (condition) {
  // kodning bu qismi to'g'ri shart uchun ishlaydi
} else {
  // kodning bu qismi noto'g'ri holat uchun ishlaydi
}
```

```js
let num = 3
if (num > 0) {
  console.log(`${num} musbat son`)
} else {
  console.log(`${num} musbat son`)
}
//  3 musbat son

num = -3
if (num > 0) {
  console.log(`${num} musbat son`)
} else {
  console.log(`${num} musbat son`)
}
//  -3 musbat son
```

```js
let isRaining = true
if (isRaining) {
  console.log('Sizga yomg\'ir palto kerak.')
} else {
  console.log('Yomg\'ir paltosi kerak emas.')
}
// Sizga yomg'ir palto kerak.

isRaining = false
if (isRaining) {
  console.log('Sizga yomg\'ir palto kerak.')
} else {
  console.log('Yomg\'ir paltosi kerak emas.')
}
// Yomg\'ir paltosi kerak emas.
```

Oxirgi shart noto'g'ri, shuning uchun else bloki bajarildi. Agar bizda ikkitadan ortiq shart bo'lsa-chi? Bunday holda, biz _else if_ shartlaridan foydalanamiz.

### If  Else if Else

Kundalik hayotimizda biz har kuni qaror qabul qilamiz. Biz bir yoki ikkita shartni tekshirib emas, balki bir nechta shartlarga asoslanib qaror qabul qilamiz.
Bizning kundalik hayotimizga o'xshab, dasturlash ham shartlarga to'la. Agar bizda bir nechta shartlar mavjud bo'lsa, biz _else if_ dan foydalanamiz .

```js
// sintaksis 
if (condition) {
     // code
} else if (condition) {
   // code
} else {
    //  code

}
```

**Misol:**

```js
let a = 0
if (a > 0) {
  console.log(`${a} musbat son`)
} else if (a < 0) {
  console.log(`${a} musbat son`)
} else if (a == 0) {
  console.log(`${a} nolga teng`)
} else {
  console.log(`${a} raqam emas`)
}
```

```js
// if else if else
let weather = 'quyoshli'
if (weather === 'yomg\'irli') {
  console.log('Sizga yomg\'ir palto kerak.')
} else if (weather === 'bulutli') {
  console.log('Havo sovuq bo\'lishi mumkin, sizga kurtka kerak.')
} else if (weather === 'quyoshli') {
  console.log('Bemalol tashqariga chiqing.')
} else {
  console.log('Yomg\'ir kiyimi kerak emas.')
}
```

### Switch

Switch - bu **if else if else else** ga alternativdir. Ya'ni ma'nosi bir lekin sintaksisi qisqa va ixcham.
Switch bayonoti kalit so'zdan keyin qavs va kod blokidan boshlanadi. Kod blokida bizda turli holatlar bo'ladi. Agar switch bayonotidagi qavsdagi qiymat case qiymatiga mos kelsa, Case bloki ishlaydi. Tanaffus bayonoti shart bajarilgandan keyin kod bajarilishi pasaymasligi uchun bajarishni tugatishdir. Standart blok barcha holatlar shartni qoniqtirmasa ishlaydi.
```js
switch(caseValue){
  case 1:
    // code
    break
  case 2:
   // code
   break
  case 3:
  // code
  default:
   // code
}
```

```js
let weather = 'bulutli'
switch (weather) {
  case 'yomg\'irli':
    console.log('Sizga yomg\'ir palto kerak.')
    break
  case 'bulutli':
    console.log('Havo sovuq bo\'lishi mumkin, sizga kurtka kerak.')
    break
  case 'quyoshli':
    console.log('Bemalol tashqariga chiqing.')
    break
  default:
    console.log('Yomg\'ir kiyimi kerak emas.')
}

// Switch ko'roq misollarda
let dayUserInput = prompt('Bugun qaysi kun ?') // Brouzer orqali kiritasiz
let day = dayUserInput.toLowerCase()

switch (day) {
  case 'monday':
    console.log('Bugun  Monday')
    break
  case 'tuesday':
    console.log('Bugun  Tuesday')
    break
  case 'wednesday':
    console.log('Bugun  Wednesday')
    break
  case 'thursday':
    console.log('Bugun  Thursday')
    break
  case 'friday':
    console.log('Bugun  Friday')
    break
  case 'saturday':
    console.log('Bugun  Saturday')
    break
  case 'sunday':
    console.log('Bugun  Sunday')
    break
  default:
    console.log('Bu hafta kuni emas')
}

```

// Shartlardan foydalanishga misollar

```js
let num = prompt('Raqamni kiriting');
switch (true) {
  case num > 0:
    console.log('Raqam musbat');
    break;
  case num == 0:
    console.log('Raqamlar nolga teng');
    break;
  case num < 0:
    console.log('Raqam manfiy');
    break;
  default:
    console.log('Kiritilgan qiymat raqam emas edi');
}
```

### Ternar Operatorlar

Shartlarni yozishning yana bir usuli - uchlik operatorlardan foydalanish. Biz buni boshqa bo'limlarda ko'rib chiqdik, lekin bu erda ham eslatib o'tishimiz kerak.

```js
// isRaining => yomg'ir yog'ayaptimi = true
let isRaining = true
isRaining
  ? console.log('Sizga yomg\'ir palto kerak.')
  : console.log('Yomg\'ir paltosi kerak emas.')
```

🌕  Siz ajoyibsiz va ajoyib salohiyatga egasiz. Siz hozirgina 4-kun sinovlarini yakunladingiz va siz buyuklik sari to'rt qadam oldindasiz. Endi miyangiz va mushaklaringiz uchun bir nechta mashqlarni bajaring.

## 💻 Mashqlar

### Mashqlar: Level 1

1. So'rov yordamida foydalanuvchi ma'lumotlarini oling ("Yoshingizni kiriting:"). Agar foydalanuvchi 18 yosh yoki undan katta bo'lsa, fikr-mulohaza bildiring: "Siz haydash uchun yetarli yoshdasiz", lekin agar 18 yoshda bo'lmasa, u 18 yoshga to'lishi uchun qancha yil kutish kerakligini aytib, yana bir fikr bildiring.

   ```sh
    Yoshingizni kiriting: 30
    Siz haydash uchun etarlicha yoshdasiz.
    
    Yoshingizni kiriting: 15
    Haydash uchun 3 yil vaqtingiz bor.
   ```

2. if … else yordamida myAge va yourAge qiymatlarini solishtiring. Taqqoslash asosida va natijani konsolga yozib qo'ying, kim katta (men yoki siz). Yoshni kiritish uchun taklifdan (“Yoshingizni kiriting:”) foydalaning.

   ```sh
    Yoshingizni kiriting: 30
    Siz mendan 5 yosh kattasiz.
   ```

3. Agar a b dan katta bo'lsa, 'a b dan katta', aks holda 'a b dan kichikdir. Uni turli yo'llar bilan amalga oshirishga harakat qiling

    - if else orqali
    - ternar operator orqali.

    ```js
      let a = 4
      let b = 3
    ```

    ```sh
      4 3 dan katta
    ```

4. Juft sonlar 2 ga bo'linadi, qolganlari esa nolga teng. Raqam juft yoki JavaScript ishlatmayotganligini qanday tekshirish mumkin?

    ```sh
    Raqamni kiriting: 2
    2 - juft son

    Raqamni kiriting: 9
    9 - toq raqam.
    ```

### Mashqlar: Level 2

1. Talabalarga ballari bo'yicha baho qo'yadigan kodni yozing:
   - 80-100, A
   - 70-89, B
   - 60-69, C
   - 50-59, D
   - 0-49, F
2. Fasl kuz, qish, bahor yoki yoz ekanligini tekshiring. Agar foydalanuvchi kiritishi:
   If the user input is :
   - Sentyabr, oktyabr yoki noyabr, mavsum - kuz.
   - Dekabr, yanvar yoki fevral, mavsum - qish.
   - Mart, aprel yoki may, mavsum - bahor
   - Iyun, iyul yoki avgust, mavsum - yoz
3. Bir kun dam olish kuni yoki ish kuni ekanligini tekshiring. Skriptingiz kirish sifatida bir kunni oladi.

    ```sh
      Bugun qanday kun ? shanba
      Shanba - dam olish kuni.
    
      Bugun qanday kun ? shanba
      Shanba - dam olish kuni.
    
      Bugun qanday kun ? Juma
      Juma - ish kuni.
    
      Bugun qanday kun ? juma
      Juma - ish kuni.
    ```

### Mashqlar: Level 3

1. Bir oydagi kunlar sonini ko'rsatadigan dastur yozing.

    ```sh
      Oyni kiriting: yanvar
      Yanvarda 31 kun bor.
    
      Oyni kiriting: YANVAR
      Yanvarda 31 kun bor
    
      Oyni kiriting: fevral
      Fevralda 28 kun bor.
    
      Oyni kiriting: fevral
      Fevralda 28 kun bor.
    ```

1. Bir oydagi kunlar sonini ko'rsatadigan dastur yozing, endi kabisa yilini ko'rib chiqing.


🎉 TABRIKLAYMAN ! 🎉

[<< 3-kun](../03_Day_Booleans_operators_date/03_booleans_operators_date.md) | [5-kun >>](../05_Day_Arrays/05_day_arrays.md)
