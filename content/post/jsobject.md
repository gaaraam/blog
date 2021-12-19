---
title: "[javascript] 객체"
date: 2021-12-19
tags: ["javascript"]

---

## 객체의 선언과 호출
객체는 하나의 이름에 여러 종류의 값을 넣을 수 있게 해준다.
```js
const yeji = {
  name: '황예지',
  age: 22,
  position: 'leader'
};

const ryujin = {
  name: '신류진',
  age: 21,
  position: 'center'
};
  
console.log(yeji.name); // return 황예지
console.log(yeji.age); // return 22
console.log(ryujin.position); // return center
```

yeji라는 객체에 name이라는 값이 존재하듯이,
`console.log()`는 console이라는 객체에 log라는 함수가 존재하는 것으로 이해할 수 있다.
## 객체 비구조화 할당(객체 구조 분해)
yeji 내부의 값을 조회할 때마다 yeji. 을 입력해야 하는 것이 장황하게 느껴진다면, 객체 구조 분해를 통하여 간결하게 만들 수 있다.
```js
const yeji = {
  name: '황예지',
  age: 22,
  position: 'leader'
};

const ryujin = {
  name: '신류진',
  age: 21,
  position: 'center'
};

function print(itzy){
  const{name, age, position} = itzy;
 // 객체에서 값을 추출해서 새로운 상수로 선언해주는 것이다.
 //아래와 같이 파라미터 단계에서 할당을 할 수도 있다.
  /*
  function print({name, age, position}){
  */
  const text = `${age}살의 ${name}(은/는)
itzy에서 ${position}을 맡고 있다.`;
  console.log(text);
}

print(yeji);
print(ryujin);
```
## 객체 내부에 함수 추가
```js
const dog = {
  name: '멍멍이'
  sound: '멍멍!' 
  say: function say() {
    console.log(this.sound);
  }
};

dog.say();
```
함수가 객체 안에 들어가게 되면, this는 자신이 속해있는 객체를 가리키게 된다. 함수명을 적지 않아도 동일하게 작동한다.
