#### :peach: javascript


## async  
기억할 것은 async는 Promise를 먼저 알아야 하고 async의 결과는 Promise다.   

```js
 async function getName(){
      return 'Mike'
  } 
console.log(getName())  // async를 붙이지 않는 상태에서 실행
console.log(typeof(getName()))   // async를 붙이지 않는 상태에서 실행

getName().then( (abc)=>{
console.log(` ${abc} 이 뭔들` )
})

```


