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
즉 next()가 호출되기까지 실행을 멈추었다가 재개하는 것이다.   
next()문은 value (산출값) , done (함수실행이 끝나면 ture, 아니면 false를 갖는다)  

> function* 함수이름() 또는 function *함수이름() 둘다 맞는 표현   

```js
function* abc() {
    yield 1;
    yield 2;
    return 3;
}

let generator = abc();
// console.log(generator) 이렇게는 1,2가 출력되지 않는다. 

for(let value of generator) {
  console.log (value); // 1, 2가 출력됨
}
// 여기서 3이 출력되지 않는이유는 for문으로 인해 yield문을 차례로 접근해서
// 실행할때 {value:3, done:true} 를 반환하고 이때 done:true이면
// 마지막 value를 무시하기 때문입니다 
```
그래서 위의내용을 아래와 같이 변경해 본다. 
```js
function* abc() {
    yield 1;
    yield 2;
    return 3;
}

let generator = [0,...abc()]  //전개구문을 이용
console.log(generator)
결과는,
(3)[0,1,2] 
```   
참고로 다음의 코드를 실행해보자   


```js
function* abc() {
    yield 1;
    yield 2;
    return 3;
}

let generator = abc()
// 위의 코드에서는 for of 문을 사용했다. 
for(let i=0; i<3; i++) {
  console.log (generator.next()); // 1, 2가 출력됨
}
결과는
{value: 1, done: false}
{value: 2, done: false}
{value: 3, done: true}

// for문안의   console.log (generator.next().value); 변경해보면
결과는
1
2
3 이다 
```

### 제너레이터함수의 장점
다른 프로그래밍 언어에서 while문은 무한루프에 빠지기 쉽다. 그런데 generator함수를 이용하면 next()를 호출할때 실행되기 때문에 무한루프에 빠지지 않게 할 수 있다. 

```js
 function* abc(){
    let i=0;
    while (true){
        yield i++
    }
}
const a= abc()

브라우저 콘솔창에서 a.next()를 할때만 계산이 되므로 무한루프에 빠지지 않는다
>a.next()
<{value: 0, done: false}
>a.next()
<{value: 1, done: false}
>a.next()
<{value: 2, done: false}
```
이것으로 제너레이터는 값을 미리 만들어두지 않고 next()로 호출될때만 실행되니 메모리를 미리 많이 잡아두지 않는다것을 알 수 있다. 





