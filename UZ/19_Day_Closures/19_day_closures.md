<div align="center">
  <h1> JavaScript-ning 30 kuni: Closures</h1>
  <a class="header-badge" target="_blank" href="https://www.linkedin.com/in/asabeneh/">
  <img src="https://img.shields.io/badge/style--5eba00.svg?label=LinkedIn&logo=linkedin&style=social">
  </a>


<sub>Author:
<a href="https://www.linkedin.com/in/asabeneh/" target="_blank">Asabeneh Yetayeh</a><br>
<small> January, 2022</small>
</sub>

</div>

[<< 18-kun](../18_Day_Promises/18_day_promise.md) | [20-kun >>](../20_Day_Writing_clean_codes/20_day_writing_clean_codes.md)

![Thirty Days Of JavaScript](../images/banners/day_1_19.png)
- [19-Kun](#19-kun)
  - [Closure](#closure)
  - [Mashqlar](#mashqlar)
    - [Mashqlar: Level 1](#mashqlar-level-1)
    - [Mashqlar: Level 2](#mashqlar-level-2)
    - [Mashqlar: Level 3](#mashqlar-level-3)

# 19-Kun

## Closure

JavaScript tashqi funksiya ichida yozish funksiyasiga ruxsat beradi. Biz xohlagancha ichki funksiyalarni yozishimiz mumkin. Agar ichki funktsiya tashqi funktsiyaning o'zgaruvchilariga kirsa, u yopish deb ataladi.

```js
function outerFunction() {
    let count = 0;
    function innerFunction() {
        count++
        return count
    }

    return innerFunction
}
const innerFunc = outerFunction()

console.log(innerFunc())
console.log(innerFunc())
console.log(innerFunc())
```

```sh
1
2
3
```

Keling, ichki funktsiyalarga ko'proq misol keltiraylik

```js
function outerFunction() {
    let count = 0;
    function plusOne() {
        count++
        return count
    }
    function minusOne() {
        count--
        return count
    }

    return {
        plusOne:plusOne(),
        minusOne:minusOne()
    }
}
const innerFuncs = outerFunction()

console.log(innerFuncs.plusOne)
console.log(innerFuncs.minusOne)
```

```sh
1
1
```

🌕 Siz taraqqiyotga erishasiz. Tezlikni saqlang, yaxshi ishni davom eting. Endi miyangiz va mushaklaringiz uchun bir nechta mashqlarni bajaring.

## Mashqlar

### Mashqlar: Level 1

1. Bitta ichki funktsiyaga ega bo'lgan yopishni yarating

### Mashqlar: Level 2

1. Uchta ichki funktsiyaga ega bo'lgan yopishni yarating

### Mashqlar: Level 3

1. PersonalAccount out funksiyasini yarating. Uning ismi, familiyasi, daromadlari, xarajatlari ichki o'zgaruvchilari mavjud. U TotalIncome, totalExpense, accountInfo, addIncome, addExpense va accountBalance ichki funksiyalariga ega. Daromadlar - bu daromadlar majmui va uning tavsifi va xarajatlari ham xarajatlar va uning tavsifi.

🎉 TABRIKLAYMAN ! 🎉

[<< 18-kun](../18_Day_Promises/18_day_promises.md) | [20-kun >>](../20_Day_Writing_clean_codes/20_day_writing_clean_codes.md)