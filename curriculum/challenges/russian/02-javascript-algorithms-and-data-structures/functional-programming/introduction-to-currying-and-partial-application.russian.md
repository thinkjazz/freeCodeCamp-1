---
id: 587d7dab367417b2b2512b70
title: Introduction to Currying and Partial Application
challengeType: 1
forumTopicId: 301232
localeTitle: Введение в каррирование и частичное применение
---

## Description
<section id='description'>
<code>Arity</code> функции - это количество аргументов, которое она требует. Функция currying означает преобразование функции N <code>arity</code> в N функций <code>arity</code> 1. Другими словами, она реструктурирует функцию таким образом, что принимает один аргумент, затем возвращает другую функцию, которая принимает следующий аргумент, и так далее. 
 Вот пример:

```js
//Un-curried function
function unCurried(x, y) {
  return x + y;
}

//Curried function
function curried(x) {
  return function(y) {
    return x + y;
  }
}
//Alternative using ES6
const curried = x => y => x + y

curried(1)(2) // Returns 3
```

Это полезно в вашей программе, если вы не можете предоставить все аргументы в функцию за один раз. Вы можете сохранить каждый вызов функции в переменную, в которой будет храниться ссылка на возвращаемую функцию, которая принимает следующий аргумент, когда он доступен. Приведем пример использования функции <code>curried</code> в примере выше:

```js
// Call a curried function in parts:
var funcForY = curried(1);
console.log(funcForY(2)); // Prints 3
```

Аналогично, <code>partial application</code> можно описать как применение нескольких аргументов к функции одновременно и возврат другой функции, которая применяется к большему количеству аргументов.
Приведем пример:

```js
//Impartial function
function impartial(x, y, z) {
  return x + y + z;
}
var partialFn = impartial.bind(this, 1, 2);
partialFn(10); // Returns 13
```

</section>

## Instructions
<section id='instructions'>
Заполните тело функции <code>add</code> чтобы он использовал currying для добавления параметров <code>x</code> , <code>y</code> и <code>z</code> .
</section>

## Tests
<section id='tests'>

```yml
tests:
  - text: <code>add(10)(20)(30)</code> should return <code>60</code>.
    testString: assert(add(10)(20)(30) === 60);
  - text: <code>add(1)(2)(3)</code> should return <code>6</code>.
    testString: assert(add(1)(2)(3) === 6);
  - text: <code>add(11)(22)(33)</code> should return <code>66</code>.
    testString: assert(add(11)(22)(33) === 66);
  - text: Your code should include a final statement that returns <code>x + y + z</code>.
    testString: assert(code.match(/[xyz]\s*?\+\s*?[xyz]\s*?\+\s*?[xyz]/g));

```

</section>

## Challenge Seed
<section id='challengeSeed'>

<div id='js-seed'>

```js
function add(x) {
  // Add your code below this line


  // Add your code above this line
}
add(10)(20)(30);

```

</div>

</section>

## Solution
<section id='solution'>

```js
const add = x => y => z => x + y + z
```

</section>
