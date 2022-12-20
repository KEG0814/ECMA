ES10(ECMAScript2019)_22.12.20
=============================

### Array.flat()

`Array.flat()` returns a new array with any sub-array(s) flattened.
> `Array.flat()`은 모든 하위 배열이 병합된 새 배열을 반환합니다.

```
let arr = [1, 2, 3, [4, 5, 6, [7, 8, 9, [10, 11, 12]]]];

arr.flat(); // [1, 2, 3, 4, 5, 6, Array(4)];
```


A call to `Array.flat()` without any arguments will only flatten one-level deep.
> 인수 없이 `Array.flat()`을 호출하면 한 수준 깊이만 평평해집니다.

```
arr.flat().flat(); // [1, 2, 3, 4, 5, 6, 7, 8, 9, Array(3)];
```


An optional depth argument can be provided or it can just be called consecutively.
> 선택적 깊이 인수를 제공하거나 연속적으로 호출할 수 있습니다.

```
arr.flat(3); // [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12]

// Or, if you're not sure about the depth of the array:
arr.flat(Infinity); // [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12]
```

* * *

### Array.flatMap()

The `flatMap()` method is identical to the ES6 map method, but also flattens at the same time.
> `flatMap()` 메서드는 ES6 맵 메서드와 동일하지만 동시에 평면화됩니다.


the `flatMap()` method first maps each element using a mapping function,
> `flatMap()` 메서드는 먼저 매핑 함수를 사용하여 각 요소를 매핑합니다.


then flattens the result into a new array.
> 그런 다음 결과를 새 배열로 병합합니다


`flatMap()` is often quite useful, as merging both into one method is slightly more efficient.
> `flatMap()`은 둘 다 하나의 방법으로 병합하는 것이 약간 더 효율적이므로 종종 매우 유용합니다.


**Examples:**

```
let arr = [1, 2, 3, 4, 5];

arr.map(x => [x, x * 2]);
// [Array(2), Array(2), Array(2)]
// 0: (2)[1, 2]
// 1: (2)[2, 4]
// 2: (2)[3, 6]

arr.flatMap(v => [v, v * 2]);
// [1, 2, 2, 4, 3, 6, 4, 8, 5, 10]
```

* * *

### String.trimStart()&String.trimEnd()

`String.trimStart()` can be used to trim white space from the start of a string.
> `String.trimStart()`는 문자열의 시작 부분에서 공백을 제거하는 데 사용할 수 있습니다.

**Examples:**

```
let greeting = "      Hello everyone";

console.log(greeting.trimStart());
//"Hello everyone"
```
```
let greeting = "Hello world    ";

console.log(greeting.trimEnd());
// "Hello world"
```

* * *

### Optional Catch Binding

Optional catch binding allows developers to use try/catch without the error parameter inside the catch block.
> 선택적 catch 바인딩을 통해 개발자는 catch 블록 내에서 error 매개 변수 없이 try/catch를 사용할 수 있습니다.

**Examples:**

Before ES2019 we use:
```
try {
  // some code
}
catch (err) {
  // error handling code
}
```

Now we can use try/catch like this with ES2019:
```
try  {
  // some code
}
catch {
  // error handling code
}
```

* * *

### Object.fromEntries()

It creates an object or transforms key-value pairs into an object. 
> 객체를 생성하거나 키-값 쌍을 객체로 변환합니다.


It only accepts iterables e.g: `Object.fromEntries(someIterable)`.
> Iterable만 허용합니다. 예: `Object.fromEntries(someIterable)`.

**Examples:**

```
let entries = new Map([["name", "john"], ["age", 22]]);

console.log(Object.fromEntries(entries));
// { name: 'john', age: 22 }
```

* * *

### Symbol.description

The read-only description property is a string returning the optional description of Symbol objects.
> 읽기 전용 설명 속성은 Symbol 개체의 선택적 설명을 반환하는 문자열입니다.

**Examples:**

```
let mySymbol = `My Symbol`;

let symObj = Symbol(mySymbol);

console.log(symObj) // Symbol(mySymbol);

console.log(String(symObj) === `Symbol(${mySymbol})`); // true

console.log(symObj.description); // "My Symbol"
```

* * *
