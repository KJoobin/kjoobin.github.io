# Inheritance partterns 의 주요 개념 정리  

- prototype   
- constructor   
- \_\_proto\_\_   
- Object.create   
- class   

OOP 는 4가지 특성을 가지는데, 그중에 하나인 상속에서의 주요 개념을 정리하는 문서이다.   

## prototype   
prototype 은 상속을하는 객체에서 가지고 있는 특성 이라고 생각하면 된다.   
상속을 받는 객체에서도 prototype 에 접근을 하여 읽을수 있으며, 코드에서는   
```js
var Car = function() {
  var name = this.name;
  // ......
}

Car.prototype.stop = function() {
  console.log('Stop!!!');
}

var avante = new Car('avante');
avante.stop() //Stop!!!
```
## constructor   
constructor 는 번역을 하면 생성자 이다.  위의 코드에서 avante 의 생성자는 Car 이며, Car 의 생성자는 Objcet method 이다.   
constructor 만 new 키워드를 사용하여 instance 를 만들수 있다.   
```js
//avante 의 경우 Car 의 prototype, Object method 의 prototype 을 가지게 된다.
//avante 의 constructor 는 Car, Car 의 constructor 는 Object 이다.
avante.__proto__.constructor  //Car
avante.__proto__.__proto__.constructor  //Object
```
## __proto__   
__proto__ 는 prototype 에 접근을 가능하게 하는 method 이다. 사용법은 위의 코드에 나와있으므로 생략을 하겠다.   

## Object.create   
Object.create 는 prototype 을 deep copy 하여 다른 constructor 에 할당해주는 method 로써 
```js
var Car = function(name) {
  this.name = name;
  console.log(this.name + ' ' + 'running');
};
Car.prototype.stop = function() {
  console.log(this.name + ' ' + 'Stop!!');
};
var Humen = function() {
  Car.apply(this, arguments);                     // Car 의 this 값을 apply 하고, 실행
  console.log(this.name + ' ' + 'Eatting');
};
Humen.prototype = Object.create(Car.prototype);   // Humen 의 prototype 을 Car 의 Prototype 의 값으로 할당; (Deep copy);

var avante = new Car('avante'); // avante running
console.log(avante.stop());     // avnate Stop!!
var runner = new Humen('Kim');  // Kim runnig 
                                // Kim Eatting
console.log(runner.stop());     // Kim Stop!!


```
## class   
위의 OOP 를 쉽게 하기 위해 ES6 에서 만들어진 문법으로, super, constructor, extends 를 이용하여 확장을 손쉽게 할수 있다.   
extends : 하위 class 를 상위 class 에 확장하기 위해서 필요한 문법   
Constructor : instance 화를 하기 위해 필요하다.   
super : subclass 에 constructor 가 있으며, constructor 에 this 키워드를 사용하려면 super 을 먼저 선언해야한다.
```js
//var Car = function(name) {
//  this.name = name;
//  console.log(this.name + ' ' + 'running');
//};
//Car.prototype.stop = function() {
//  console.log(this.name + ' ' + 'Stop!!');
//};
class Car {
  constructor(name) {
    this.name = name;
    console.log(`${this.name} running`);
  }
  stop() {
    console.log(`${this.name} Stop!!`);
  }
}
//var Humen = function() {
//  Car.apply(this, arguments);                     // Car 의 this 값을 apply 하고, 실행
//  console.log(this.name + ' ' + 'Eatting');
//};
//Humen.prototype = Object.create(Car.prototype);   // Humen 의 prototype 을 Car 의 Prototype 의 값으로 할당; (Deep copy);

class Humen extends Car {
  constructor(name){
    super(name);    //Car 에 constructor 에 arguments 가 된다.
    console.log(`${this.name} Eatting`); 
  }
}

var avante = new Car('avante'); // avante running
console.log(avante.stop());     // avnate Stop!!
var runner = new Humen('Kim');  // Kim runnig 
                                // Kim Eatting
console.log(runner.stop());     // Kim Stop!!


```
