---
layout: single
title:  "var, let, const"
excerpt: "JavaScript 변수"

categories:
- JavaScript

tags:
- [JavaScript, variable, var, let, const]

date: 2022-11-6
published: true
---

## JavaScript 변수 식별자의 차이
---

### 변수
변수(variable)는 하나의 값을 저장하기 위해 확보한 메모리 공간 또는 그 메모리 공간을 식별하기 위해 붙인 이름을 말한다.

```javascript
const myNumber = 33
// 변수명(식별자): myNumber
// 해당 값의 위치(메모리 주소): 0011CCGWH88
// 변수 값(저장된 값): 33
```
위 예제에서 변수명 myNumber는 변수 값인 33이 아닌 33이 들어가 있는 메모리의 주소를 기억하고 있다.
변수를 사용하면 자바스크립트 엔진이 myNumber가 가르키는 메모리주소를 통해 변수 값인 33을 반환하는 것이다.

이처럼 변수에 값을 저장하는 것을 할당(assignment, 대입, 저장)이라 하며 변수에 저장된 값을 읽어 들이는 것을 참조(reference)라 한다. 그리고 변수명을 자바스크립트 엔진에 알리는 것을 선언(declaration)이라 한다.

### var, let, const의 차이

'let' 과 'const' 는 기존 var에서의 세 가지 문제점을 해결하기 위해 ES6 이후로 출연한 변수명이고 var의 문제점은 다음과 같다.
- 변수 중복 선언이 가능하다.
- 함수 레벨 스코프로 인해 함수 외부에서 선언한 변수는 모두 전역 변수로 선언된다.
- 변수 선언문 이전에 참조 시 undefined를 반환 한다.

### 1. let

```javascript
let name = 'phw'
console.log(name) // phw

let name = 'jpark' //SyntaxError

name = 'jyp'

console.log(name) // jyp
```
위 예제 처럼 let은 중복 선언은 불가능 하지만, 재할당은 가능하다.

### 2. const
``` javascript

const name; // SyntaxError: 
const name = 'phw'
```
위의 예제 처럼 const는 let 과 달리 선언과 할당이 동시에 진행되어야 한다.
또한 const 변수명은 재 할당이 불가능 하다. 재할당의 경우, 원시 값은 불가능 하지만, 객체는 가능하다.

```javascript
const name = [1,2,3]
console.log(name) //[1,2,3]
name[0] = 2
console.log(name) // [2,2,3]
```

### 변수의 스코프

```javascript
let a = 1

if (true) {
  let a = 3
}

console.log(a) // output: 1
```

위의 예제에서 알 수 있듯 if 문 안의 let a는 지역 스코프를 갖기 때문에 전역에서 선언된 a의 값을 재할당 하지 않는다 const 로 작성했을 경우도 동일하다.
하지만 var로 작성할 경우는 a가 재할당 되어 3이 된다.


변수의 스코프를 최대한 좁게하는 것이 잠재적인 버그를 줄일수 있으므로 var보다는 let과 const를 사용하는것이 좋다.



