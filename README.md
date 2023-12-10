#### :peach: javascript


## Class

Class는 사실 "특별한 함수"입니다. 함수를 함수 표현식과 함수 선언으로 정의할 수 있듯이 class 문법도 class 표현식 and class 선언 두 가지 방법을 제공합니다.  

### Class 선언
Class를 정의하는 한 가지 방법은 class 키워드를 사용하여 선언한다. 

```js
class Rectangle {
  constructor(height, width) {
    this.height = height;
    this.width = width;
  }
}
```
class도 특별한 함수라고 했다. 그런데 함수는 선언하기전에도 호출하여 사용할 수 있지만
class는 반드시 정의한 뒤에 사용해야 한다는 점이 다르다 즉 Hoisting에서 다른 것이다.  


### Class 표현식   
Class 표현식은 class를 정의하는 또 다른 방법이다. Classs 표현식은 이름을 가질 수도 있고 없을 수도 있는데 해당 Class 표현식의 이름을 알고 싶다면 name 속성으로 사용해야 한다. 
아래는 이에 대한 설명이다.  
```js
let Rectangle = class {
        constructor(height, width) {
            this.height = height;
            this.width = width;
        }
};
console.log(Rectangle.name);  // class 뒤에 이름이 없기 때문에 Rectangle 로 나온다.  

let Rectangle2 = class  Rectangle2{
        constructor(height, width) {
            this.height = height;
            this.width = width;
        }
};
console.log(Rectangle2.name)

```

## Class body에 뭘 넣을수 있을까

Class body 는 {  } 시작한다.  그리고 여기에 메서드와 constructor가 들어간다.  
constructor메서드는 class 로 생성된 객체를 생성하고 초기화하기 위한 특수한 메서드이다.
constructor라는 이름을 가진 메서드는 해당 클래스 안에 1개만 존재해야한다. 

## extends 
```js

class Car{
    constructor(color){
    this.color= color;
    this.wheels = 4;
    }
    drive(){
        console.log("drive...")
    }
    stop(){
        console.log("stop!")
    }
}

class Bmw extends Car{
    park(){
        console.log("Parking...")
    }
}

const z4 = new Bmw("blue")
```





