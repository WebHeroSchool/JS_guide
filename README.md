# JavaScript Style Guide
___
*Наиболее разумный подход к написанию JS*
___
## Правила

1. Избегайте однобуквенных названий и давайте логичное название переменным и функциям.
2. Всегда пользуйтесь `;` в конце строк кода.
3. Используйте `===` и `!==` (строгое сравнение ), вместо `==` и `!=` (нестрогое сравнение).
4. Не пишите повторяющийся код.
5. Для создания объектов используйте `{}` вместо `new Object()`.
6. Для создания массивов используйте `[]` вместо `new Array()`.
7. Используйте поиск в DOM по `id`, а не по селектору.
8. Используйте camelCase для названий переменных, объектов и функций.
9. Всегда используйте `let` или `const` для объявления переменных, не используйте `var`.
10. Если не переназначаете переменную, то используйте `const` для ее объявления. И наоборот.
___
### 1. Избегайте однобуквенных названий и давайте логичное название переменным и функциям.

✔ **Хорошо**
```js
function makeTable() {
}
let userName = 'Greg';
```
❌ **Плохо**
```js
function t() {
}

let n = 'Greg';
```

### 2. Всегда пользуйтесь `;` в конце строк кода.
✔ **Хорошо**
```js
let someItem = 'some string';
function doSomething() {
  return 'something';
}
```
❌ **Плохо**
```js
let someItem = 'some string'
function doSomething() {
  return 'something'
}
```

### 3. Используйте `===` и `!==` (строгое сравнение ), вместо `==` и `!=` (нестрогое сравнение).
✔ **Хорошо**
```js
typeof foo === 'undefined'
'hello' !== 'world'
0 === 0
true === true
foo === null
```
❌ **Плохо**
```js
a == b 
foo == true
bananas != 1
value == undefined
```

### 4. Не пишите повторяющийся код.
##### Если вам приходится копировать и вставлять блок кода, это признак того, что данный блок можно выделить в отдельную функцию.
✔ **Хорошо**
```js
function writeTable(row, col){  
  document.write("<table border=2 cellspacing=0>");
    for(let i = 1; i <= row; i++) {
      document.write("<tr>");
      for(let j = 1; j <= col; j++) {
        document.write("<td>Ячейка " + j + "</td>");
      }
      document.write("</tr>");
      }
    document.write("</table>");    
    }
writeTable(7,7);
```
❌ **Плохо**
```js
document.write("<table border=1 cellspacing=0>");
document.write("<tr>");
document.write("<td>Ячейка1</td>");
document.write("</tr>");
document.write("<tr>");
document.write("<td>Ячейка1</td>");
document.write("</tr>");
document.write("</table>");
```
### 5. Для создания объектов используйте `{}` вместо `new Object()`.
✔ **Хорошо**
```js
let o = {
   name: 'Jeffrey',
   lastName = 'Way',
   someFunction : function() {
      console.log(this.name);
   }
};
```
❌ **Плохо**
```js
let o = new Object();
o.name = 'Jeffrey';
o.lastName = 'Way';
o.someFunction = function() {
   console.log(this.name);
}
```
### 6. Для создания массивов используйте `[]` вместо new `Array()`.
✔ **Хорошо**
```js
let b = []; //пустой массив
let a = ['Joe','Plumber'];
```
❌ **Плохо**
```js
let a = new Array();
a[0] = "Joe";
a[1] = 'Plumber';
```
### 7. Используйте поиск в DOM по `id`, а не по селектору.
✔ **Хорошо**
```
<button class="btn" id="button">Request to Book</button>
```
```js
const button = document.getElementById('button');
```
❌ **Плохо**
```
<button class="btn">Request to Book</button>
```
```js
const button = document.querySelector('.btn');
```

### 8. Используйте camelCase для названий переменных, объектов и функций.
✔ **Хорошо**
```js
const thisIsMyObject = {};
function thisIsMyFunction() {}
```
❌ **Плохо**
```js
const OBJEcttsssss = {};
const this_is_my_object = {};
function 1234c() {}
```

### 9. Всегда используйте `let` или `const` для объявления переменных, не используйте `var`.
✔ **Хорошо**
```js
const superPower = new SuperPower();
```
❌ **Плохо**
```js
uperPower = new SuperPower();
var number = 4;
```

### 10. Если не переназначаете переменную, то используйте `const` для ее объявления. И наоборот.
✔ **Хорошо**
```js
const age = 18;
```
❌ **Плохо**
```js
let name = "Sara";
```