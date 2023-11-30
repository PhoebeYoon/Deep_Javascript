#### :peach: javascript

기술이 좀 달라진것을 느낀다. 다시 점검하는 시간을 갖자.

## 이벤트 정리하기
```js
1.
document.addEventListener('DOMContentLoaded', ()=>{
  console.log('loaded')
})

window.addEventListener('scroll', function(){
    console.log(' scrolled')
})

window.addEventListener('resize', function(){
    console.log('resized')
})

```    
이렇게는 모두 작동한다.   
아래와 같이 내용을 바꿔보면 약간 다른다. 

```js
function pageLoad() {
    console.log('loaded again')
}

function winResize() {
    console.log('resize again')
}

function winScroll(){
    console.log('scroll again')
}
document.onload = pageLoad;
window.onresize = winResize;
window.onscroll = winScroll;

```    
윈도우의 resize와 scroll는 잘 인식되지만 document.onload는 실행되지 않는다 뭐 그렇다고 틀린것은 아니다.   
방법을 바꿔주면 된다.  
```
<body onload="pageLoad()">
이런식으로 하면 된다. DOM형성과 관계있기 때문이다.
그런데 이렇게 사용하지 않고 위의 방식대로 사용하고 싶다면
document.onload --> window.onload = pageLoad;
onload 이벤트를 window에 붙여주면 된다.  
```
🌟 1. 에서 봤듯이 'DOMContentLoaded'는 DOM 형성되고 이미지, css등이 로드된 후를 말하기 때문에 생각대로 작동했지만, 
document.onload는 그렇지 않기 때문에 잘못된 것처럼 보인다.   

```html


```

