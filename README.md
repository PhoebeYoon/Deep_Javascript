#### :peach: javascript


## 프로미스의 형식
```js
const 변수 = new Promise((resolve, reject)=>{
  코드
})
```
resolve 는 성공했을때
reject 는 실패했을때이다. 그럼 이 각각의 경우에 따라 결과가 있고    
이 결과를 어떻게 처리할지를 알려줘야 한다.    
위의 코드에서 'const 변수'에서 변수를 demo라고 하자    
  
성공이든 실패이든 그 결과를 demo 변수가 갖게 되고   
이 demo의 내용을 꺼내야(?) 하는데 이때 then() 과 catch()를 사용하면 된다.   
즉, demo.then(성공했을때 ) .catch(실패했을때 )이라고 적으면 된다.    

