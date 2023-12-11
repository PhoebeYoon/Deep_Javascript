#### :peach: javascript


## async  
기억할 것은 async는 Promise를 먼저 알아야 하고 async의 결과는 Promise다.   

```js
 async function getName(){
      return 'Mike'
  } 
console.log(getName())  // async를 붙이지 않는 상태에서 실행
console.log(typeof(getName()))   // async를 붙이지 않는 상태에서 실행

getName().then( (abc)=>{   // async의 결과가 Promise라는 것은 then()를 사용할 수 있다는 것이다 
console.log(` ${abc} 이 뭔들` )
})
```


그래서 아래처럼 return 'Mike' 대신 Promise를 리턴해주어도 된다.  
``` js
async function getName(){
    return Promise.resolve('Tom')
}

 getName().then( (abc)=>{
    console.log(` ${abc} 이 뭔들` )
})

```

이제 가장 간단히 사용하되 await, async를 사용하지 않은 코드를 사용해보자   
```js
function showName(){
    console.log("1")
    let result= getName();
     console.log(result)
} 

function getName(){
    console.log("2")
    return new Promise((res,rej)=>{
        res('Tom')
    })
   
}
console.log("0")
showName()

이 코드의 결과는
0
1
2
Promise{<fulfilled>:'Tom'} 이다

```
같은 코드이지만 await 과 async를 붙여보자. **await는 async 안에서만 사용할 수 있다.**
동일코드에 아래 부부만 바꾼다.   
```js
 async function showName(){
    console.log("1")
    let result= await getName();
     console.log(result)
} 

이 코드의 결과는
0
1
2
Tom 이다 
```
흔히들 setTimeout() 함수를 중간에 붙이는 것은 사용자가 눈으로 확인할 시간을 주기 위한 것이지 꼭 필요해서는 아니다.  

await, async에서 에러가 났을때는 **try{} catch{} 문으로 처리해준다.**   
```js
 async function showName(){
    console.log("1")
    try {
        let result= await getName();
         console.log(result)
    } catch(e){
     console.log('error 발생',e)
    }
} 

function getName(){
    console.log("2")
    return new Promise((res,rej)=>{
        res('Tom')  // 일부러 에러를 발생시키기위해 re('Tom')해보자
    })
}
console.log("0")
showName()

결과는 동일하다
0
1
2
Tom

에러가 발생되면 결과는
0
1
2
error 발생 ReferenceError: re is not defined
...

```











