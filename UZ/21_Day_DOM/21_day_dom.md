<div align="center">
  <h1> JavaScript-ning 30 kuni: Document Object Model(DOM)</h1>
  <a class="header-badge" target="_blank" href="https://www.linkedin.com/in/asabeneh/">
  <img src="https://img.shields.io/badge/style--5eba00.svg?label=LinkedIn&logo=linkedin&style=social">
  </a>


<sub>Author:
<a href="https://www.linkedin.com/in/asabeneh/" target="_blank">Asabeneh Yetayeh</a><br>
<small> January, 2022</small>
</sub>

</div>

[<< 20-kun](../20_Day_Writing_clean_codes/20_day_writing_clean_codes.md) | [22-kun >>](../22_Day_Manipulating_DOM_object/22_day_manipulating_DOM_object.md)

![Thirty Days Of JavaScript](../images/banners/day_1_21.png)

- [21-Kun](#21-kun)
  - [Document Object Model (DOM) - 1-kun](#document-object-model-dom---1-kun)
    - [Elementni olish](#elementni-olish)
      - [Elementni tag nomi orqali olish](#elementni-tag-nomi-orqali-olish)
      - [Elementni class nomi orqali olish](#elementni-class-nomi-orqali-olish)
      - [Elementni id orqali olish](#elementni-id-orqali-olish)
      - [Elementlarni querySelector methodlari orqali olish](#elementlarni-queryselector-methodlari-orqali-olish)
    - [Attribute qo'shish](#attribute-qoshish)
      - [Attribute qo'shish setAttribute orqali](#attribute-qoshish-setattribute-orqali)
      - [Attribute qo'shish setAttribute dan foydalanmay](#attribute-qoshish-setattribute-dan-foydalanmay)
      - [Class qo'shish classList orqali](#class-qoshish-classlist-orqali)
      - [Classni olib tashlash remove orqali](#classni-olib-tashlash-remove-orqali)
    - [HTML elementga matn qo'shish](#html-elementga-matn-qoshish)
      - [Matn kontentini qo'shish textContent orqali](#matn-kontentini-qoshish-textcontent-orqali)
      - [Matn kontentini qo'shish innHTML orqali](#matn-kontentini-qoshish-innhtml-orqali)
        - [Text Content](#text-content)
        - [Inner HTML](#inner-html)
    - [Style qo'shish](#style-qoshish)
      - [Style qo'shish Rang](#style-qoshish-rang)
      - [Style qo'shish Orqa fon rangi](#style-qoshish-orqa-fon-rangi)
      - [Style qo'shish Shrift o'lchami](#style-qoshish-shrift-olchami)
  - [Mashqlar](#mashqlar)
    - [Mashqlar: Level 1](#mashqlar-level-1)
    - [Mashqlar: Level 2](#mashqlar-level-2)
    - [Mashqlar: Level 3](#mashqlar-level-3)
      - [DOM: Mini loyiha 1](#dom-mini-loyiha-1)

# 21-Kun

## Document Object Model (DOM) - 1-kun

HTML hujjati JavaScript obyekti sifatida tuzilgan. Har bir HTML elementi uni manipulyatsiya qilishga yordam beradigan turli xil xususiyatlarga ega. JavaScript yordamida HTML elementlarini olish, yaratish, qo'shish yoki o'chirish mumkin. Quyidagi misollarni tekshiring. JavaScript yordamida HTML elementini tanlash CSS yordamida tanlashga o'xshaydi. HTML elementini tanlash uchun biz teg nomi, id, sinf nomi yoki boshqa atributlardan foydalanamiz.

### Elementni olish

Biz allaqachon yaratilgan element yoki elementlarga JavaScript yordamida kirishimiz mumkin. Elementlarga kirish yoki olish uchun biz turli usullardan foydalanamiz. Quyidagi kodda to'rtta h1 elementi mavjud. Keling, h1 elementlariga kirishning turli usullarini ko'rib chiqaylik .

```html
<!DOCTYPE html>
  <html>
    <head>
      <title>Document Object Model</title>
    </head>
    <body>

     <h1 class='title' id='first-title'>First Title</h1>
     <h1 class='title' id='second-title'>Second Title</h1>
     <h1 class='title' id='third-title'>Third Title</h1>
     <h1></h1>

    </body>
  </html>
```

#### Elementni tag nomi orqali olish

**_getElementsByTagName()_**: string parametri sifatida qabul nomini oladi va bu usul HTMLCollection obyektini qaytaradi. HTMLCollection - bu HTML elementlari ob'ektiga o'xshash massiv. Uzunlik xususiyati kollektsiya hajmini ta'minlaydi. Ushbu usuldan foydalanganda biz har bir alohida element orqali indeks yoki keyin tsikl yordamida alohida elementlarga kiramiz. HTMLCollection barcha massiv usullarini qo'llab-quvvatlamaydi, shuning uchun biz forEach o'rniga muntazam for tsiklidan foydalanishimiz kerak.

```js
// syntax
document.getElementsByTagName('tagname')
```

```js
const allTitles = document.getElementsByTagName('h1')

console.log(allTitles) //HTMCollections
console.log(allTitles.length) // 4

for (let i = 0; i < allTitles.length; i++) {
  console.log(allTitles[i]) // prints each elements in the HTMLCollection
}
```

#### Elementni class nomi orqali olish

**_getElementsByClassName()_** usuli HTMLCollection obyektini qaytaradi. HTMLCollection - bu HTML elementlari ro'yxatiga o'xshash massiv. Uzunlik xususiyati kollektsiya hajmini ta'minlaydi. Barcha HTMLCollection elementlarini aylanib chiqish mumkin. Quyidagi misolga qarang

```js
//syntax
document.getElementsByClassName('classname')
```

```js
const allTitles = document.getElementsByClassName('title')

console.log(allTitles) //HTMCollections
console.log(allTitles.length) // 4

for (let i = 0; i < allTitles.length; i++) {
  console.log(allTitles[i]) // prints each elements in the HTMLCollection
}
```

#### Elementni id orqali olish

**_getElementsById()_** bitta HTML elementiga mo'ljallangan. Biz argument sifatida # identifikatorini o'tkazamiz.

```js
//syntax
document.getElementById('id')
```

```js
let firstTitle = document.getElementById('first-title')
console.log(firstTitle) // <h1>First Title</h1>
```

#### Elementlarni querySelector methodlari orqali olish

_document.querySelector_ usuli HTML yoki HTML elementlarini teg nomi, id yoki sinf nomi boʻyicha tanlashi mumkin .

**_querySelector_**: HTML elementini teg nomi, identifikatori yoki sinfi bo'yicha tanlash uchun ishlatilishi mumkin. Agar teg nomi ishlatilsa, u faqat birinchi elementni tanlaydi.

```js
let firstTitle = document.querySelector('h1') // birinchi mavjud h2 elementni tanlash 
let firstTitle = document.querySelector('#first-title') // ID si first-title ga teng bo'lgan elementni tanlash 
let firstTitle = document.querySelector('.title') // sinf nomi title ga teng, birinchi mavjud h2 elementini tanlash

```

**_querySelectorAll_**: HTML elementini teg nomi yoki sinfi boʻyicha tanlash uchun ishlatilishi mumkin. U massiv usullarini qo'llab-quvvatlaydigan massivga o'xshash ob'ekt bo'lgan nodeListni qaytaradi. Har bir nodeList elementi orqali aylanish uchun for `loop` yoki `forEach` dan foydalanishimiz mumkin

```js
const allTitles = document.querySelectorAll('h1')

console.log(allTitles.length) // 4
for (let i = 0; i < allTitles.length; i++) {
  console.log(allTitles[i])
}

allTitles.forEach(title => console.log(title))
const allTitles = document.querySelectorAll('.title') // sinf yordamida tanlash uchun ham xuddi shunday
```

### Attribute qo'shish

HTML ning ochilish yorlig'iga element haqida qo'shimcha ma'lumot beruvchi atribut qo'shiladi. Umumiy HTML atributlari: id, sinf, src, style, href, o'chirilgan, sarlavha, alt. To'rtinchi sarlavha uchun id va sinf qo'shamiz.

```js
const titles = document.querySelectorAll('h1')
titles[3].class = 'title'
titles[3].id = 'fourth-title'
```

#### Attribute qo'shish setAttribute orqali

**_setAttribute()_** usuli har qanday html atributini o'rnatadi . U atributning turi va atribut nomi kabi ikkita parametrni oladi. To'rtinchi sarlavha uchun sinf va id atributini qo'shamiz.

```js
const titles = document.querySelectorAll('h1')
titles[3].setAttribute('class', 'title')
titles[3].setAttribute('id', 'fourth-title')
```

#### Attribute qo'shish setAttribute dan foydalanmay

Biz atributni o'rnatish uchun oddiy ob'ektni sozlash usulidan foydalanishimiz mumkin, ammo bu barcha elementlar uchun ishlamaydi. Ba'zi atributlar DOM ob'ekt xususiyati bo'lib, ular to'g'ridan-to'g'ri o'rnatilishi mumkin. Masalan, id va sinf

```js
// attribute o'rnatishning yana bir usuli
titles[3].className = 'title'
titles[3].id = 'fourth-title'
```

#### Class qo'shish classList orqali

Sinflar ro'yxati usuli qo'shimcha sinf qo'shishning yaxshi usuli hisoblanadi. Agar sinf mavjud bo'lsa, u asl sinfni bekor qilmaydi, balki element uchun qo'shimcha sinf qo'shadi.

```js
// atributni o'rnatishning yana bir usuli: sinfni qo'shing, qayta yozmaydi
titles[3].classList.add('title', 'header-title')
```

#### Classni olib tashlash remove orqali

Qo'shishga o'xshab biz ham elementdan sinfni olib tashlashimiz mumkin. Biz elementdan ma'lum bir sinfni olib tashlashimiz mumkin.

```js
// atributni o'rnatishning yana bir usuli: sinfni olib tashlash, qayta yozmaydi 
titles[3].classList.remove('title', 'header-title')
```

### HTML elementga matn qo'shish

HTML - bu ochilish yorlig'i, yopish tegi va matn tarkibining qurilish blokidir. Biz _textContent_ yoki *innerHTML xususiyatidan foydalanib, matn tarkibini qo'shishimiz mumkin .

#### Matn kontentini qo'shish textContent orqali

_textContent_ xususiyati HTML elementiga matn qo'shish uchun ishlatiladi.

```js
const titles = document.querySelectorAll('h1')
titles[3].textContent = 'Fourth Title'
```

#### Matn kontentini qo'shish innHTML orqali

Ko'pchilik _textContent_ va _innerHTML_ o'rtasida chalkashib ketishadi . _textContent_ HTML elementiga matn qo'shish uchun mo'ljallangan, ammo innerHTML matn yoki HTML elementi yoki elementlarni bola sifatida qo'shishi mumkin.

##### Text Content

Biz matnga _textContent_ HTML obyekti xossasini tayinlaymiz

```js
const titles = document.querySelectorAll('h1')
titles[3].textContent = 'Fourth Title'
```

##### Inner HTML

Biz innerHTML xususiyatidan ota-ona elementni almashtirish yoki butunlay yangi bolalar tarkibini yoqtirganimizda foydalanamiz. Biz tayinlagan qiymat HTML elementlari qatori bo'ladi.

```html
<!DOCTYPE html>
<html>
  <head>
    <title>JavaScript for Everyone:DOM</title>
  </head>
  <body>
    <div class="wrapper">
        <h1>Asabeneh Yetayeh challenges in 2022</h1>
        <h2>30DaysOfJavaScript Challenge</h2>
        <ul></ul>
    </div>
    <script>
    const lists = `
    <li>30DaysOfPython Challenge Done</li>
            <li>30DaysOfJavaScript Challenge Ongoing</li>
            <li>30DaysOfReact Challenge Coming</li>
            <li>30DaysOfFullStack Challenge Coming</li>
            <li>30DaysOfDataAnalysis Challenge Coming</li>
            <li>30DaysOfReactNative Challenge Coming</li>
            <li>30DaysOfMachineLearning Challenge Coming</li>`
  const ul = document.querySelector('ul')
  ul.innerHTML = lists
    </script>
  </body>
</html>
```

InnerHTML xususiyati bizga ota-elementning barcha bolalarini olib tashlashga ham imkon beradi. removeChild() dan foydalanish o'rniga men quyidagi usulni tavsiya qilaman.

```html
<!DOCTYPE html>
<html>
  <head>
    <title>JavaScript for Everyone:DOM</title>
  </head>
  <body>
    <div class="wrapper">
        <h1>Asabeneh Yetayeh challenges in 2022</h1>
        <h2>30DaysOfJavaScript Challenge</h2>
        <ul>
            <li>30DaysOfPython Challenge Done</li>
            <li>30DaysOfJavaScript Challenge Ongoing</li>
            <li>30DaysOfReact Challenge Coming</li>
            <li>30DaysOfFullStack Challenge Coming</li>
            <li>30DaysOfDataAnalysis Challenge Coming</li>
            <li>30DaysOfReactNative Challenge Coming</li>
            <li>30DaysOfMachineLearning Challenge Coming</li>
        </ul>
    </div>
    <script>
  const ul = document.querySelector('ul')
  ul.innerHTML = ''
    </script>
  </body>
</html>
```

### Style qo'shish

#### Style qo'shish Rang

Keling, _titles_ ga biroz style qo'shaylik. Agar element teng indeksga ega bo'lsa, biz unga yashil rangni, qizil rangni beramiz.

```js
const titles = document.querySelectorAll('h1')
titles.forEach((title, i) => {
  title.style.fontSize = '24px' // barcha sarlavhalar 24px shrift hajmiga ega bo'ladi, 
  if (i % 2 === 0) {
    title.style.color = 'green'
  } else {
    title.style.color = 'red'
  }
})
```

#### Style qo'shish Orqa fon rangi

Keling, sarlavhalarimizga biroz style qo'shaylik. Agar element teng indeksga ega bo'lsa, biz unga yashil rangni, qizil rangni beramiz.

```js
const titles = document.querySelectorAll('h1')
titles.forEach((title, i) => {
  title.style.fontSize = '24px' // barcha sarlavhalar 24px shrift hajmiga ega bo'ladi, 
  if (i % 2 === 0) {
    title.style.backgroundColor = 'green'
  } else {
    title.style.backgroundColor = 'red'
  }
})
```

#### Style qo'shish Shrift o'lchami

Keling, sarlavhalarimizga biroz style qo'shaylik. Agar element juft indeksga ega bo'lsa, biz unga 20px, boshqa 30px beramiz

```js
const titles = document.querySelectorAll('h1')
titles.forEach((title, i) => {
  title.style.fontSize = '24px' // barcha sarlavhalar 24px shrift hajmiga ega bo'ladi, 
  if (i % 2 === 0) {
    title.style.fontSize = '20px'
  } else {
    title.style.fontSize = '30px'
  }
})
```

E'tibor berganingizdek, biz JavaScript-da CSS-dan foydalanganda uning xususiyatlari camelCase bo'ladi. Quyidagi CSS xususiyatlari fon rangidan backgroundColorga, font-size fontSizega, font-family fontFamilyga, margin-bottomdan marginBottomga o‘zgaradi.

---

🌕 Endi siz super kuch bilan to'liq zaryadlangansiz, siz sinovning eng muhim va qiyin qismini va umuman JavaScript-ni yakunladingiz. Siz DOM-ni o'rgandingiz va endi siz ilovalarni yaratish va ishlab chiqish imkoniyatiga egasiz. Endi miyangiz va mushaklaringiz uchun bir nechta mashqlarni bajaring.

## Mashqlar

### Mashqlar: Level 1

1. Index.html faylini yarating va yuqoridagi kabi to'rtta p elementni qo'ying: document.querySelector(tagname) va teg nomidan foydalanib birinchi xatboshini oling.
2. Har bir paragrafni document.querySelector('#id') yordamida va ularning identifikatori orqali oling
3. Document.querySelectorAll(tagname) va teg nomidan foydalanib, barcha p ni nodeList sifatida oling
4. NodeList orqali aylanib chiqing va har bir paragrafning matn mazmunini oling
5. To'rtinchi xatboshi, To'rtinchi xatboshiga matn mazmunini o'rnating
6. Turli atributlarni sozlash usullaridan foydalangan holda barcha paragraflar uchun id va sinf atributini o'rnating

### Mashqlar: Level 2

1. JavaScript yordamida har bir paragrafning rangini o'zgartiring (masalan, rang, fon, chegara, shrift o'lchami, shrift oilasi)
2. Barcha paragraflarni tanlang va har bir elementni aylantiring va birinchi va uchinchi xatboshiga yashil rang, ikkinchi va to'rtinchi xatboshiga esa qizil rang bering.
3. Har bir paragrafga matn mazmuni, identifikator va sinfni o'rnating

### Mashqlar: Level 3

#### DOM: Mini loyiha 1

1. Quyidagi dasturni ishlab chiqing, boshlash uchun quyidagi HTML elementlaridan foydalaning. Siz boshlang'ich jildida bir xil kodni olasiz. Faqat JavaScript-dan foydalanib, barcha uslublar va funksiyalarni qo'llang.

   - Yil rangi har 1 soniyada o'zgarib turadi
   - Sana va vaqt fon rangi har soniyada o'zgarib turadi
   - Bajarilgan topshiriq yashil fonga ega
   - Davom etayotgan chaqiruv fonida sariq rang mavjud
   - Kelgusi qiyinchiliklar qizil fonga ega

```html
<!-- index.html -->
<!DOCTYPE html>
<html>
  <head>
    <title>JavaScript for Everyone:DOM</title>
  </head>
  <body>
    <div class="wrapper">
        <h1>Asabeneh Yetayeh challenges in 2022</h1>
        <h2>30DaysOfJavaScript Challenge</h2>
        <ul>
            <li>30DaysOfPython Challenge Done</li>
            <li>30DaysOfJavaScript Challenge Ongoing</li>
            <li>30DaysOfReact Challenge Coming</li>
            <li>30DaysOfFullStack Challenge Coming</li>
            <li>30DaysOfDataAnalysis Challenge Coming</li>
            <li>30DaysOfReactNative Challenge Coming</li>
            <li>30DaysOfMachineLearning Challenge Coming</li>
        </ul>
    </div>
  </body>
</html>
```

![Project 1](../images/projects/dom_min_project_challenge_info_day_1.1.gif)

![Project 2](../images/projects/dom_min_project_challenge_info_day_1.1.png)

🎉 TABRIKLAYMAN  ! 🎉

[<< 20-kun](../20_Day_Writing_clean_codes/20_day_writing_clean_codes.md) | [22-kun >>](../22_Day_Manipulating_DOM_object/22_day_manipulating_DOM_object.md)
