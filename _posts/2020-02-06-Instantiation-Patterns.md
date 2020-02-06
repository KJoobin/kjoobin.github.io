---
title: "[TID] Instantiation Patterns 4가지 패턴 "
date: 2020-02-06 21:34:00  -0400
categories: TID InstanstiationPatterns functional functionalShare objectCreate prototypal pseudoclassical
---

## Instantiation Patterns  
Instance 를 만드는데 4가지 방법을 소개하려고한다.  

## functional  
가장 간단한 방법으로  

```js
var Car = function() {
  var someInstance = {};
  someInstance.position = 0;
  someInstance.move = function() {
    this.position += 1;
  }
}

var car1 = Car();
var car2 = Car();
car1.move();
console.log(car1.position)  //1
```
이해하기도 쉽고, 작성하기도 쉽다. 하지만 그만큼 메모리낭비가 심하다는 단점이 존재한다.  
```js
//if
var car1 = Car();
var car2 = Car();
var car3 = Car();
.
.
.
```

각 변수마다 메소드의 수 만큼 할당하므로, 그만큼 메모리 낭비가 심하다.  
```
functional 은 메모리의 낭비가 있다.
```

## functional shared  
functional 의 메모리 낭비를 줄이기위해 생긴것으로, 메소드를 각각 선언하기보다 한번 선언하여 그 주소값을 참조하게 한다.  
```js
var extends = function(to, from) {
  for (var key in from) {
  to[key] = from[key];
  }
}

var someMethods = {};
someMethods.move = function() {
  this.position += 1;
}

var Car = function(position) {
  var someInstance = {};
  someInstance.position = position;
  extends(someInstance, someMethods);
  return someInstance;
}

var car1 = Car(1);
var car2 = Car(2);
```

```
메소드를 선언한뒤 주소값을 참조함으로 메모리 낭비를 줄일수 있다.
```

## prototypal  

prototype 을 사용하는 방법으로써, object.create() 메소드를 사용한다.  

```js
var someMethods = {};
someMethods.move = function() {
  this.position += 1;
}

var Car = function(position) {
  var someInstance = Object.create(someMethods);
  someInstance.position = position;
  return someInstance;
}

var car1 = Car(1);
var car2 = Car(2);
```

### functional shared 과 prototypal 의 차이점  
prototypal 의 경우 prototype chain 을 사용할수 있어 결과값이 다르다.  
```js
//functional  shared 의 결과값
{ position: 2, move: [function] }

//prototypal 의 결과값

{ position: 2 }

```
prototypal 에 move:[function] 값이 나오지 않는 이유는  Object.create() 를 사용할 경우 prototype chain 을 사용하여 직접
Car 에 move 메소드가 선언된것이 아닌 prototype 에 선언된 값을 참조하기 때문이다.  

## Pseudoclassical

Pseudoclassical 의 경우 더욱 간단하다.
```js
var Car = function(position) {
  this.position = position;
}

Car.prototype.move = function() {
  this.position += 1;
}

var car1 = new Car(1);
var car2 = new Car(2);
```
Pseudoclassical 의 경우 new operator 를 꼭 써야한다.  
```
4가지 패턴중 가장 많이 쓰이고, new operator 를 꼭 써야한다.
```
