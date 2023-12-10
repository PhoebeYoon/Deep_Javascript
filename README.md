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

또한 마무리를 짓는 의미에서 .finally()를 사용할 수 있는데 성공했든 실패를 했듯
finally()를 실행해서 마무리를 해 준다고 생각하면 된다.   

```js
const demo = new Promise((res, err)=>{
        setTimeout(()=>{
           res('1초 지남')  // res를 호출해서 어떤 값을 전달할지 적어야 한다
        } , 1000)
    })
    console.log('시작')
    demo.then( (result)=>{
        console.log(`전달된 result :${result}`)
    }).catch((result)=>{
        console.log(`전달된 result :${result}`)
    }).finally(()=>{
        console.log("--end--")
    })
```


```js
const f1 = ()=>{
  return new Promise((resolve, reject)=>{
     setTimeout( ()=>{
      resolve(' 1번 주문 완료')
      }, 1000)
  })
  }
  const f2 = (message)=>{
  console.log(message) // f1에서 전달된 resolve()결과를 출력한다
  return new Promise((resolve, reject)=>{
      setTimeout( ()=>{
      resolve(' 2번 주문 완료')
      }, 3000)
  })
  }
  const f3 = (message)=>{
  console.log(message) // f2에서 전달된 resolve()결과를 출력한다
  return new Promise((resolve, reject)=>{
      setTimeout( ()=>{
      resolve(' 3번 주문 완료')
      }, 2000)
  })
        }
  console.log('시작')
   f1()
   .then((resolve) => f2(resolve))
   .then((resolve) => f3(resolve))
   .then((resolve) => console.log(resolve) )

```

