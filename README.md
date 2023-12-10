#### :peach: javascript


## Class

Class는 사실 "특별한 함수"입니다. 함수를 함수 표현식과 함수 선언으로 정의할 수 있듯이 class 문법도 class 표현식 and class 선언 두 가지 방법을 제공합니다.  

### Class 선언
Class를 정의하는 한 가지 방법은 class 키워드를 사용하여 선언한다. 

```
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
