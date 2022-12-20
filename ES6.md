ES6_22.12.20
============

* 외부링크<https://wormwlrm.github.io/2019/04/29/ECMAScript-tutorial.html>

* * *

### var
> 전체 함수에서 블록 스코프(Block Scope)와 관계 없이 전역(Global)변수나 지역(Local)변수를 선언할 때 사용됨.
> 따라서 블록 스코프 밖에서도 해당 변수를 참조할 수 있어 혼란을 일으킴.

```
var x = 1;
if (true) {
  var x = 2;
  console.log(x); // 2
}
console.log(x); // 2
```

### let
> 변수의 범위를 현재 선언되어 있는 블록까지로 제한합니다.

```
if (true) {
  let hello = "Hello";
}
console.log(hello); // undefined
```
```
let x = 1;
if (true) {
  let x = 2;
  console.log(x); // 2
}
console.log(x); // 1
```

### const
> let처럼, **블록 스코프의 범위**를 가지고 있습니다. 
> 하지만 let과는 다르게 const는 **변수 재할당이 불가능**하다는 특징을 갖고 있습니다.

```
const a = "Hello";
a = "Bye"; // Uncaught TypeError: Assignment to constant variable.
```

> **주의** 변수의 재할당이 불가능한 것이지, **변수의 수정은 가능**하답니다.


특히 변수가 Object거나 Array일 경우에 헷갈릴 수 있습니다. 아래 예시를 참조해주세요.


```
// Object의 property 수정은 가능합니다.
const man = {
  name: "john",
};
man.name = "mike";
console.log(man.name); // mike

// 하지만 Object를 재할당 할 수는 없습니다.
man = {
  name: "peter",
}; // Uncaught TypeError: Assignment to constant variable.
```

```
// Array의 item들을 수정할 수 있습니다.
const dishes = ["bread", "coffee"];
dishes.push("butter");
console.log(dishes); // ['bread', 'coffee', 'butter']

// 하지만 Array를 재할당 할 수는 없습니다.
dishes = ["rice", "cake"]; // Uncaught TypeError: Assignment to constant variable.
```
