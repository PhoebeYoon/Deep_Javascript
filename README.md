#### :peach: javascript




## Null vs undefined vs math.js:9 Uncaught ReferenceError
그냥 남겨놓는다. 누군가 보여주기 위해

null 은  null 값이다. undefined 는 변수를 초기화하지 않았다는 것으로 Uncaught ReferenceError와 같다.   


```js
let empty1= null;
let empty2 ;

console.log(empty1, empty2)
console.log(empty3)

```

결과를 보면 아래와 같이 나온다. 결국 empty2와 empty3는 같다고 봐야 한다.   
```
null undefined
math.js:9 Uncaught ReferenceError: empty3 is not defined
```
