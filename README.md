#### :peach: javascript


## Generator ( 제너레이터)
일반 함수는 하나의 값(혹은 0개의 값)만을 반환한다. 
하지만 제너레이터(generator)를 사용하면 여러 개의 값을 필요에 따라 하나씩 반환(yield)할 수 있다.   
> yield 단어는 흔히 '양보하다' 의미로 사용되기도 하지만 '산출/생산하다', (농작물등의) 산출량을 뜻하기도 한다   

### Generator 함수 구조 및 메서드
```js
function* 함수이름(){
  yield
}

let 변수 = 함수이름() 
```
이런 구조로 되어 있으면 Generator 함수는 Generator 객체를 생성한다.    
제너레이터함수의 메소드로는 next()가 있으며 이것은 yield문을 차례대로 찾아 실행한다.  
next()문은 value (산출값) , done (함수실행이 끝나면 ture, 아니면 false를 갖는다)  

> function* 함수이름() 또는 function *함수이름() 둘다 맞는 표현   
