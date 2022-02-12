<div align="center">
  <h1> JavaScript-ning 30 kuni: Klasslar</h1>
  <a class="header-badge" target="_blank" href="https://www.linkedin.com/in/asabeneh/">
  <img src="https://img.shields.io/badge/style--5eba00.svg?label=LinkedIn&logo=linkedin&style=social">
  </a>


<sub>Author:
<a href="https://www.linkedin.com/in/asabeneh/" target="_blank">Asabeneh Yetayeh</a><br>
<small> January, 2022</small>
</sub>

</div>

[<< 14-kun](../14_Day_Error_handling/14_day_error_handling.md) | [16-kun>>](../16_Day_JSON/16_day_json.md)

![Thirty Days Of JavaScript](../images/banners/day_1_15.png)

- [15-Kun](#15-kun)
  - [Klasslar](#klasslar)
    - [Klassni e'lon qilish](#klassni-elon-qilish)
    - [Klassni namunasini olish](#klassni-namunasini-olish)
    - [Klass konstruktori](#klass-konstruktori)
    - [Konstruktor bilan standart qiymatlar](#konstruktor-bilan-standart-qiymatlar)
    - [Klass methodlari](#klass-methodlari)
    - [Boshlang'ich qiymatga ega bo'lgan xususiyatla](#boshlangich-qiymatga-ega-bolgan-xususiyatla)
    - [getter](#getter)
    - [setter](#setter)
    - [Statik method](#statik-method)
  - [Meros olish](#meros-olish)
    - [Override methodlari](#override-methodlari)
  - [Mashqlar](#mashqlar)
    - [Mashqlar Level 1](#mashqlar-level-1)
    - [Mashqlar Level 2](#mashqlar-level-2)
    - [Mashqlar Level 3](#mashqlar-level-3)

# 15-Kun

## Klasslar

JavaScript - bu ob'ektga yo'naltirilgan dasturlash tili. JavScript-dagi hamma narsa o'zining xususiyatlari va usullari bilan ob'ektdir. Ob'ekt yaratish uchun sinf yaratamiz. Sinf ob'ekt konstruktori yoki ob'ektlarni yaratish uchun "loyiha"ga o'xshaydi. Ob'ektni yaratish uchun biz sinfni yaratamiz. Sinf ob'ektning atributlari va xatti-harakatlarini belgilaydi, ob'ekt esa sinfni ifodalaydi.

Biz sinf yaratganimizdan so'ng, biz xohlagan vaqtda undan ob'ekt yaratishimiz mumkin. Sinfdan ob'ekt yaratish sinf instantsiyasi deb ataladi.

Ob'ekt bo'limida biz ob'ekt literalini qanday yaratishni ko'rdik. Ob'ekt literal - bu singleton. Agar shunga o'xshash ob'ektni olishni istasak, uni yozishimiz kerak. Biroq, sinf ko'plab ob'ektlarni yaratishga imkon beradi. Bu kod miqdorini va kodning takrorlanishini kamaytirishga yordam beradi.

### Klassni e'lon qilish

JavaScript-da sinfni aniqlash uchun bizga class kalit so'zi , **CamelCase** -dagi sinf nomi va blok kodi (ikki jingalak qavs) kerak. Keling, shaxs nomini yarataylik.

```sh
// sintaksis
class ClassName {
    //  kod shu yerda
}

```

**Misol:**

```js
class Person {
  //  kod shu yerda
}
```

Biz Person sinfini yaratdik, lekin uning ichida hech qanday narsa yo'q.

### Klassni namunasini olish

Instantsiya sinfi sinfdan ob'ekt yaratishni anglatadi. Bizga new kalit so'zi kerak va biz new so'zidan keyin sinf nomini chaqiramiz.

Keling, Person sinfimizdan it ob'ektini yarataylik.

```js
class Person {
  // kod shu yerda
}
const person = new Person()
console.log(person)
```

```sh
Person {}
```

Ko'rib turganingizdek, biz shaxs ob'ektini yaratdik. Sinf hech qanday xususiyatga ega bo'lmagani uchun ob'ekt ham bo'sh.

Sinf uchun turli xususiyatlarni o'tkazish uchun sinf konstruktoridan foydalanishga ruxsat bering.

### Klass konstruktori

Konstruktor - bu bizning ob'ektimiz uchun loyihani yaratishga imkon beruvchi o'rnatilgan funksiya. Konstruktor funktsiyasi kalit so'z konstruktoridan keyin qavsdan boshlanadi. Qavslar ichida biz ob'ektning xususiyatlarini parametr sifatida beramiz. Konstruktor parametrlarini sinfga biriktirish uchun this kalit so'zidan foydalanamiz .

Quyidagi Person klassi konstruktorida firstName va LastName xossalari mavjud. Ushbu xususiyatlar Person sinfiga ushbu kalit so'z yordamida biriktirilgan . Bu sinfning o'ziga tegishli.

```js
class Person {
  constructor(firstName, lastName) {
    console.log(this) // Bu yerdan chiqishni tekshiring 
    this.firstName = firstName
    this.lastName = lastName
  }
}

const person = new Person()

console.log(person)
```

```sh
Person {firstName: undefined, lastName}
```

Ob'ektning barcha kalitlari aniqlanmagan. Har doim biz yaratganimizda, biz xususiyatlarning qiymatini o'tkazishimiz kerak. Keling, sinfni yaratganimizda qiymatni o'tkazaylik.

```js
class Person {
  constructor(firstName, lastName) {
    this.firstName = firstName
    this.lastName = lastName
  }
}

const person1 = new Person('Asabeneh', 'Yetayeh')

console.log(person1)
```

```sh
Person {firstName: "Asabeneh", lastName: "Yetayeh"}
```

Biz boshida aytib o'tganimizdek, sinfni yaratganimizdan so'ng, biz sinf yordamida ko'plab ob'ektlarni yaratishimiz mumkin. Keling, Person sinfidan foydalanib, ko'plab shaxs ob'ektlarini yarataylik.

```js
class Person {
  constructor(firstName, lastName) {
    console.log(this) // Bu yerdan chiqishni tekshiring 
    this.firstName = firstName
    this.lastName = lastName
  }
}

const person1 = new Person('Asabeneh', 'Yetayeh')
const person2 = new Person('Lidiya', 'Tekle')
const person3 = new Person('Abraham', 'Yetayeh')

console.log(person1)
console.log(person2)
console.log(person3)
```

```sh
Person {firstName: "Asabeneh", lastName: "Yetayeh"}
Person {firstName: "Lidiya", lastName: "Tekle"}
Person {firstName: "Abraham", lastName: "Yetayeh"}
```

Person sinfidan foydalanib, biz uchta shaxs ob'ektini yaratdik. Ko'rib turganingizdek, bizning sinfimiz unchalik ko'p emas edi, bizga sinfga qo'shimcha xususiyatlar qo'shish imkonini beradi.

```js
class Person {
  constructor(firstName, lastName, age, country, city) {
    console.log(this) // Bu yerdan chiqishni tekshiring 
    this.firstName = firstName
    this.lastName = lastName
    this.age = age
    this.country = country
    this.city = city
  }
}

const person1 = new Person('Asabeneh', 'Yetayeh', 250, 'Finland', 'Helsinki')

console.log(person1)
```

```sh
Person {firstName: "Asabeneh", lastName: "Yetayeh", age: 250, country: "Finland", city: "Helsinki"}
```

### Konstruktor bilan standart qiymatlar

Konstruktor funksiyasi xususiyatlari boshqa oddiy funksiyalar kabi standart qiymatga ega bo'lishi mumkin.


```js
class Person {
  constructor(
    firstName = 'Asabeneh',
    lastName = 'Yetayeh',
    age = 250,
    country = 'Finland',
    city = 'Helsinki'
  ) {
    this.firstName = firstName
    this.lastName = lastName
    this.age = age
    this.country = country
    this.city = city
  }
}

const person1 = new Person() // u standart qiymatlarni oladi 
const person2 = new Person('Lidiya', 'Tekle', 28, 'Finland', 'Espoo')

console.log(person1)
console.log(person2)
```

```sh
Person {firstName: "Asabeneh", lastName: "Yetayeh", age: 250, country: "Finland", city: "Helsinki"}
Person {firstName: "Lidiya", lastName: "Tekle", age: 28, country: "Finland", city: "Espoo"}
```

### Klass methodlari

Sinf ichidagi konstruktor o'rnatilgan funksiya bo'lib, u bizga ob'ekt uchun loyihani yaratishga imkon beradi. Sinfda biz sinf usullarini yaratishimiz mumkin. Metodlar sinf ichidagi JavaScript funksiyalaridir. Keling, ba'zi sinf usullarini yarataylik.

```js
class Person {
  constructor(firstName, lastName, age, country, city) {
    this.firstName = firstName
    this.lastName = lastName
    this.age = age
    this.country = country
    this.city = city
  }
  getFullName() {
    const fullName = this.firstName + ' ' + this.lastName
    return fullName
  }
}

const person1 = new Person('Asabeneh', 'Yetayeh', 250, 'Finland', 'Helsinki')
const person2 = new Person('Lidiya', 'Tekle', 28, 'Finland', 'Espoo')

console.log(person1.getFullName())
console.log(person2.getFullName())
```

```sh
Asabeneh Yetayeh
test.js:19 Lidiya Tekle
```

### Boshlang'ich qiymatga ega bo'lgan xususiyatla

Ba'zi xususiyatlar uchun sinf yaratganimizda biz boshlang'ich qiymatga ega bo'lishimiz mumkin. Misol uchun, agar siz o'yin o'ynasangiz, sizning boshlang'ich ballingiz nolga teng bo'ladi. Shunday qilib, bizda boshlang'ich ball yoki nolga teng bo'lgan ball bo'lishi mumkin. Boshqacha qilib aytganda, bizda boshlang'ich mahorat bo'lishi mumkin va biz bir muncha vaqt o'tgach, qandaydir mahoratga ega bo'lamiz.

```js
class Person {
  constructor(firstName, lastName, age, country, city) {
    this.firstName = firstName
    this.lastName = lastName
    this.age = age
    this.country = country
    this.city = city
    this.score = 0
    this.skills = []
  }
  getFullName() {
    const fullName = this.firstName + ' ' + this.lastName
    return fullName
  }
}

const person1 = new Person('Asabeneh', 'Yetayeh', 250, 'Finland', 'Helsinki')
const person2 = new Person('Lidiya', 'Tekle', 28, 'Finland', 'Espoo')

console.log(person1.score)
console.log(person2.score)

console.log(person1.skills)
console.log(person2.skills)
```

```sh
0
0
[]
[]
```

Usul oddiy usul yoki oluvchi yoki setter bo'lishi mumkin. Keling, ko'raylik, olish va sozlash.


### getter

Get usuli bizga ob'ektdan qiymatga kirish imkonini beradi. Biz get usulini get kalit so'zidan keyin funksiyadan foydalanib yozamiz. Xususiyatlarga ob'ektdan to'g'ridan-to'g'ri kirish o'rniga biz qiymatni olish uchun getterdan foydalanamiz. Quyidagi misolga qarang

```js
class Person {
  constructor(firstName, lastName, age, country, city) {
    this.firstName = firstName
    this.lastName = lastName
    this.age = age
    this.country = country
    this.city = city
    this.score = 0
    this.skills = []
  }
  getFullName() {
    const fullName = this.firstName + ' ' + this.lastName
    return fullName
  }
  get getscore() {
    return this.score
  }
  get getSkills() {
    return this.skills
  }
}

const person1 = new Person('Asabeneh', 'Yetayeh', 250, 'Finland', 'Helsinki')
const person2 = new Person('Lidiya', 'Tekle', 28, 'Finland', 'Espoo')

console.log(person1.getScore) // We do not need parenthesis to call a getter method
console.log(person2.getScore)

console.log(person1.getSkills)
console.log(person2.getSkills)
```

```sh
0
0
[]
[]
```

### setter

Setter usuli bizga ma'lum xususiyatlarning qiymatini o'zgartirish imkonini beradi. Biz to'plam kalit so'zidan keyin funktsiyadan foydalangan holda sozlash usulini yozamiz . Quyidagi misolga qarang.

```js
class Person {
  constructor(firstName, lastName, age, country, city) {
    this.firstName = firstName
    this.lastName = lastName
    this.age = age
    this.country = country
    this.city = city
    this.score = 0
    this.skills = []
  }
  getFullName() {
    const fullName = this.firstName + ' ' + this.lastName
    return fullName
  }
  get getScore() {
    return this.score
  }
  get getSkills() {
    return this.skills
  }
  set setScore(score) {
    this.score += score
  }
  set setSkill(skill) {
    this.skills.push(skill)
  }
}

const person1 = new Person('Asabeneh', 'Yetayeh', 250, 'Finland', 'Helsinki')
const person2 = new Person('Lidiya', 'Tekle', 28, 'Finland', 'Espoo')

person1.setScore = 1
person1.setSkill = 'HTML'
person1.setSkill = 'CSS'
person1.setSkill = 'JavaScript'

person2.setScore = 1
person2.setSkill = 'Planning'
person2.setSkill = 'Managing'
person2.setSkill = 'Organizing'

console.log(person1.score)
console.log(person2.score)

console.log(person1.skills)
console.log(person2.skills)
```

```sh
1
1
["HTML", "CSS", "JavaScript"]
["Planning", "Managing", "Organizing"]
```

Oddiy usul va getter o'rtasidagi farqga hayron bo'lmang. Agar siz oddiy usulni qanday qilishni bilsangiz yaxshi. Person sinfiga getPersonInfo deb nomlangan oddiy usulni qo'shamiz.

```js
class Person {
  constructor(firstName, lastName, age, country, city) {
    this.firstName = firstName
    this.lastName = lastName
    this.age = age
    this.country = country
    this.city = city
    this.score = 0
    this.skills = []
  }
  getFullName() {
    const fullName = this.firstName + ' ' + this.lastName
    return fullName
  }
  get getScore() {
    return this.score
  }
  get getSkills() {
    return this.skills
  }
  set setScore(score) {
    this.score += score
  }
  set setSkill(skill) {
    this.skills.push(skill)
  }
  getPersonInfo() {
    let fullName = this.getFullName()
    let skills =
      this.skills.length > 0 &&
      this.skills.slice(0, this.skills.length - 1).join(', ') +
        ` and ${this.skills[this.skills.length - 1]}`
    let formattedSkills = skills ? `He knows ${skills}` : ''

    let info = `${fullName} is ${this.age}. He lives ${this.city}, ${this.country}. ${formattedSkills}`
    return info
  }
}

const person1 = new Person('Asabeneh', 'Yetayeh', 250, 'Finland', 'Helsinki')
const person2 = new Person('Lidiya', 'Tekle', 28, 'Finland', 'Espoo')
const person3 = new Person('John', 'Doe', 50, 'Mars', 'Mars city')

person1.setScore = 1
person1.setSkill = 'HTML'
person1.setSkill = 'CSS'
person1.setSkill = 'JavaScript'

person2.setScore = 1
person2.setSkill = 'Planning'
person2.setSkill = 'Managing'
person2.setSkill = 'Organizing'

console.log(person1.getScore)
console.log(person2.getScore)

console.log(person1.getSkills)
console.log(person2.getSkills)
console.log(person3.getSkills)

console.log(person1.getPersonInfo())
console.log(person2.getPersonInfo())
console.log(person3.getPersonInfo())
```

```sh
1
1
["HTML", "CSS", "JavaScript"]
["Planning", "Managing", "Organizing"]
[]
Asabeneh Yetayeh is 250. He lives Helsinki, Finland. He knows HTML, CSS and JavaScript
Lidiya Tekle is 28. He lives Espoo, Finland. He knows Planning, Managing and Organizing
John Doe is 50. He lives Mars city, Mars.
```

### Statik method

Static kalit so'zi sinf uchun statik usulni belgilaydi. Statik usullar sinf misollarida chaqirilmaydi. Buning o'rniga ular sinfning o'zida chaqiriladi. Bu ko'pincha yordamchi funktsiyalar, masalan, ob'ektlarni yaratish yoki klonlash funktsiyalari. Statik usulga misol Date.now() . Now usuli to'g'ridan-to'g'ri sinfdan chaqiriladi .

```js
class Person {
  constructor(firstName, lastName, age, country, city) {
    this.firstName = firstName
    this.lastName = lastName
    this.age = age
    this.country = country
    this.city = city
    this.score = 0
    this.skills = []
  }
  getFullName() {
    const fullName = this.firstName + ' ' + this.lastName
    return fullName
  }
  get getScore() {
    return this.score
  }
  get getSkills() {
    return this.skills
  }
  set setScore(score) {
    this.score += score
  }
  set setSkill(skill) {
    this.skills.push(skill)
  }
  getPersonInfo() {
    let fullName = this.getFullName()
    let skills =
      this.skills.length > 0 &&
      this.skills.slice(0, this.skills.length - 1).join(', ') +
        ` and ${this.skills[this.skills.length - 1]}`

    let formattedSkills = skills ? `He knows ${skills}` : ''

    let info = `${fullName} is ${this.age}. He lives ${this.city}, ${this.country}. ${formattedSkills}`
    return info
  }
  static favoriteSkill() {
    const skills = ['HTML', 'CSS', 'JS', 'React', 'Python', 'Node']
    const index = Math.floor(Math.random() * skills.length)
    return skills[index]
  }
  static showDateTime() {
    let now = new Date()
    let year = now.getFullYear()
    let month = now.getMonth() + 1
    let date = now.getDate()
    let hours = now.getHours()
    let minutes = now.getMinutes()
    if (hours < 10) {
      hours = '0' + hours
    }
    if (minutes < 10) {
      minutes = '0' + minutes
    }

    let dateMonthYear = date + '.' + month + '.' + year
    let time = hours + ':' + minutes
    let fullTime = dateMonthYear + ' ' + time
    return fullTime
  }
}

console.log(Person.favoriteSkill())
console.log(Person.showDateTime())
```

```sh
Node
15.1.2022 23:56
```

Statik usullar bu foydali funktsiyalar sifatida ishlatilishi mumkin bo'lgan usullardir.

## Meros olish

Merosdan foydalanib, biz ota-klassning barcha xususiyatlari va usullariga kirishimiz mumkin. Bu kodning takrorlanishini kamaytiradi. Esingizda bo'lsa, bizda Person ota-onalar sinfi bor va biz undan bolalar yaratamiz. Bizning bolalar sinfimiz talaba bo'lishi mumkin, o'rgatadi va hokazo.

```js
// sintaksis
class ChildClassName extends {
 //  kod shu yerda
}
```

Keling, Shaxs ota sinfidan Student bola sinfini yarataylik.

```js
class Student extends Person {
  saySomething() {
    console.log('I am a child of the person class')
  }
}

const s1 = new Student('Asabeneh', 'Yetayeh', 'Finland', 250, 'Helsinki')
console.log(s1)
console.log(s1.saySomething())
console.log(s1.getFullName())
console.log(s1.getPersonInfo())
```

```sh
Student {firstName: "Asabeneh", lastName: "Yetayeh", age: "Finland", country: 250, city: "Helsinki", …}
I am a child of the person class
Asabeneh Yetayeh
Student {firstName: "Asabeneh", lastName: "Yetayeh", age: "Finland", country: 250, city: "Helsinki", …}
Asabeneh Yetayeh is Finland. He lives Helsinki, 250.
```

### Override methodlari

Ko'rib turganingizdek, biz Person Class-dagi barcha usullarga kirishga muvaffaq bo'ldik va uni Student bola sinfida ishlatdik. Biz ota-ona usullarini sozlashimiz mumkin, biz bolalar sinfiga qo'shimcha xususiyatlar qo'shishimiz mumkin. Agar biz usullarni moslashtirmoqchi bo'lsak va qo'shimcha xususiyatlar qo'shmoqchi bo'lsak, biz konstruktor funktsiyasidan bolalar sinfini ham ishlatishimiz kerak. Konstruktor funktsiyasi tomonida biz ota-sinfdagi barcha xususiyatlarga kirish uchun super() funksiyasini chaqiramiz. Shaxs sinfida jins yo'q edi, lekin endi bolalar sinfi uchun jins xususiyatini beramiz, Student. Agar bolalar sinfida bir xil usul nomi ishlatilsa, ota-ona usuli bekor qilinadi.

```js
class Student extends Person {
  constructor(firstName, lastName, age, country, city, gender) {
    super(firstName, lastName, age, country, city)
    this.gender = gender
  }

  saySomething() {
    console.log('I am a child of the person class')
  }
  getPersonInfo() {
    let fullName = this.getFullName()
    let skills =
      this.skills.length > 0 &&
      this.skills.slice(0, this.skills.length - 1).join(', ') +
        ` and ${this.skills[this.skills.length - 1]}`

    let formattedSkills = skills ? `He knows ${skills}` : ''
    let pronoun = this.gender == 'Male' ? 'He' : 'She'

    let info = `${fullName} is ${this.age}. ${pronoun} lives in ${this.city}, ${this.country}. ${formattedSkills}`
    return info
  }
}

const s1 = new Student(
  'Asabeneh',
  'Yetayeh',
  250,
  'Finland',
  'Helsinki',
  'Male'
)
const s2 = new Student('Lidiya', 'Tekle', 28, 'Finland', 'Helsinki', 'Female')
s1.setScore = 1
s1.setSkill = 'HTML'
s1.setSkill = 'CSS'
s1.setSkill = 'JavaScript'

s2.setScore = 1
s2.setSkill = 'Planning'
s2.setSkill = 'Managing'
s2.setSkill = 'Organizing'

console.log(s1)

console.log(s1.saySomething())
console.log(s1.getFullName())
console.log(s1.getPersonInfo())

console.log(s2.saySomething())
console.log(s2.getFullName())
console.log(s2.getPersonInfo())
```

```sh
Student {firstName: "Asabeneh", lastName: "Yetayeh", age: 250, country: "Finland", city: "Helsinki", …}
Student {firstName: "Lidiya", lastName: "Tekle", age: 28, country: "Finland", city: "Helsinki", …}
I am a child of the person class
Asabeneh Yetayeh
Student {firstName: "Asabeneh", lastName: "Yetayeh", age: 250, country: "Finland", city: "Helsinki", …}
Asabeneh Yetayeh is 250. He lives in Helsinki, Finland. He knows HTML, CSS and JavaScript
I am a child of the person class
Lidiya Tekle
Student {firstName: "Lidiya", lastName: "Tekle", age: 28, country: "Finland", city: "Helsinki", …}
Lidiya Tekle is 28. She lives in Helsinki, Finland. He knows Planning, Managing and Organizing
```

Endi getPersonInfo usuli bekor qilindi va u erkak yoki ayol ekanligini aniqlaydi.


🌕 Siz ajoyibsiz. Endi siz sinfni bilardingiz va siz hamma narsani ob'ektga aylantirishga qodirsiz. Siz buyuklik sari yo'lning yarmiga etib keldingiz. Endi miyangiz va mushaklaringiz uchun bir nechta mashqlarni bajaring.

## Mashqlar

### Mashqlar Level 1

1. Create an Animal class. The class will have name, age, color, legs properties and create different methods
2. Create a Dog and Cat child class from the Animal Class.

### Mashqlar Level 2

1. Override the method you create in Animal class

### Mashqlar Level 3

1. Let's try to develop a program which calculate measure of central tendency of a sample(mean, median, mode) and measure of variability(range, variance, standard deviation). In addition to those measures find the min, max, count, percentile, and frequency distribution of the sample. You can create a class called Statistics and create all the functions which do statistical calculations as method for the Statistics class. Check the output below.

```JS
ages = [31, 26, 34, 37, 27, 26, 32, 32, 26, 27, 27, 24, 32, 33, 27, 25, 26, 38, 37, 31, 34, 24, 33, 29, 26]

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
console.log('Frequency Distribution: ',statistics.freqDist()) // [(20.0, 26), (16.0, 27), (12.0, 32), (8.0, 37), (8.0, 34), (8.0, 33), (8.0, 31), (8.0, 24), (4.0, 38), (4.0, 29), (4.0, 25)]
```

```sh
// you output should look like this
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

1. Create a class called PersonAccount. It has firstname, lastname, incomes, expenses properties and it has totalIncome, totalExpense, accountInfo,addIncome, addExpense and accountBalance methods. Incomes is a set of incomes and its description and expenses is also a set of expenses and its description.

🎉 TABRIKLAYMAN ! 🎉

[<< 14-kun](../14_Day_Error_handling/14_day_error_handling.md) | [16-kun>>](../16_Day_JSON/16_day_json.md)
