#### :peach: javascript

## IntersectionObserver    
Intersection Observer API는 상위 요소 또는 최상위 문서의 뷰포트와 대상 요소의 교차에 대한 변화를 비동기적으로 관찰하는 방법을 제공한다.  
즉, 어떤요소가 기본적으로 브라우저의 뷰포트 안에 들어왔는지 지금 보이는 요소인지 아닌지를 구별할 수 있게 해준다.  
이 기능은 비동기적으로 실행되므로 scroll 이벤트 사용시 발생하는 렌더링성능을 좋아지고 이벤트 연속호출과 같은 문제를 해결할 수 있다.   

기본사용방법은 여러 엘리먼트에 이벤트를 한번에 등록하고 싶다면 콜백함수에 forEach()를 사용한다. IntersectionObserver를 생성하기 위해서는 교차되었을대 실행할 콜백함수를 등록하고 options 지정할 수 있다

### 기본구조 
```
const io = new IntersectionObserver((entries , observer )=>{    }[, options])
io.observe(element)
```

#### callback: 타겟 엘리먼트가 교차되었을 때 실행할하며  배열형식으로 리턴하며, 2개의 값 (entries, observer)를 가진다.
  - entries :  IntersectionObserverEntry 객체의 리스트로 배열형식으로 반환된다. 그래서 forEach()를 사용한다.
  - observer : 콜백함수가 호출되는 IntersectionObserver

### entires는 IntersectionObserverEntry 인스턴스의 배열이다. 이는 읽기전용으로 다음과 같은 속성을 가진다.
  - boundingClientRect : 관찰대상의 사각형 정보
  - intersectionRect : 관찰대상의 교차영역정보
  - intersectionRatio : 관찰대상의 교차할 영역 백분율로 intersectionRect 영역에서 boundingClientRect영역까지의 비율
  - insIntersecting : 관찰대상의 교차상태로 boolean 값이다
  - rootBounds : 지정한 루트요소의 사각형정보
  - target : 관찰대상 요소
  - time : 변경이 발생한 시간정보
    
#### options: 
 - root : default: null, 브라우저의 viewport, 교차 영역의 기준이 될 root 엘리먼트. observe의 대상으로 등록할 엘리먼트는 반드시 root의 하위 엘리먼트여야 합니다.
 - rootMargin : default: '0px 0px 0px 0px , root 엘리먼트의 마진값. css에서 margin을 사용하는 방법으로 선언할 수 있고, 축약도 가능하다. px과 %로 표현할 수 있습니다. rootMargin 값에 따라 교차 영역이 확장 또는 축소된다.

  ( 추적하고 있는 타켓이 뷰포트 안으로 들어갈때 0px이면 원래 주어진값으로 마진값을 계산하고 100px 이면 ahead의 개념으로 실제존재하는 위치보다 100px 더 위쪽에 있다고 계산하는 듯, 반대로 -100px 이라고 하면 뷰포트안에 들어갔지만 반응하지 않는다 )


 - threshold : default: 0 , 
    threshold는 교차점 관찰자의 생성자에 전달되는 콜백 함수를 실행하는 역할을 합니다. 이 함수는 단일 숫자 또는 숫자 배열일 수 있으며, 이는 콜백 함수가 트리거되는 시기를 결정합니다. 예를 들어, 뷰포트 내부의 대상 요소의 가시성이 30% 표시를 통과할 때 콜백 함수를 실행하려면 임계값의 값을 0.3으로 설정합니다. 마찬가지로 가시성이 25%를 통과할 때마다 콜백 함수를 실행하려면 임계값이 배열 [0, 0.25, 0.5, 0.75, 1]로 설정됩니다. 기본값인 0은 뷰포트에 한 픽셀이 보이는 즉시 콜백 함수를 트리거하는 반면 최대값인 1은 대상 요소의 모든 픽셀이 뷰포트 내부에 보일 때까지 임계값이 통과된 것으로 간주되지 않음을 의미한다


   
### methods
    - IntersectionObserver.observe(targetElement) : 
         타겟 엘리먼트에 대한 IntersectionObserver를 등록할 때(관찰을 시작할 때) 사용합니다.
    - IntersectionObserver.unobserve(targetElement) :  
        타겟 엘리먼트에 대한 관찰을 멈추고 싶을 때 사용하면 됩니다. 
       예를 들어 Lazy-loading(지연 로딩)을 할 때는 한 번 처리를 한 후에는 관찰을 멈춰도 됩니다. 
       이 경우에는 처리를 한 후 해당 엘리먼트에 대해 unobserve(targetElement)을 실행하면 
       이 엘리먼트에 대한 관찰만 멈출 수 있습니다.
    - IntersectionObserver.disconnect() : 
       다수의 엘리먼트를 관찰하고 있을 때, 이에 대한 모든 관찰을 멈추고 싶을 때 사용하면 됩니다.
    - IntersectionObserver.takerecords() : 
      IntersectionObserverEntry 객체의 배열을 리턴합니다.

> 연속적인 scroll 의 문제는 reflow 현상이다.  reflow는 문서내의 요소들의 위치과 도형을 다시 계산하기위해 다시 랜더링하는 것을 말한다. 


참고 ) https://blog.hyeyoonjung.com/2019/01/09/intersectionobserver-tutorial/
https://developer.mozilla.org/ko/docs/Web/API/IntersectionObserver/IntersectionObserver

### 분석하기
```js
 const io = new IntersectionObserver(entries =>{ 
      })
console.log(io)
```
결과로는 
```
IntersectionObserver {root: null, rootMargin: '0px 0px 0px 0px',
 thresholds: Array(1), delay: 0, trackVisibility: false}
```
출력한다    

```html
    <style>
.section {height: 100vh;width: 100vw;
  display: flex;justify-content: center;align-items: center;}
.one {background: lightblue;}
.two {background: lightgreen;}
.three {background: lightblue;}
.circle { position: fixed; height: 200px;
  width: 200px; border-radius: 150px;
  background: blue;}
.active {background: green;}
    </style>
 <section class="section one"> 
        <div class="circle"></div>
</section>
<section class="section two"></section>
<section class="section three"> </section>

<script>
  let circle = document.querySelector('.circle');

 const changeColor= (entries, observer) =>{
         entries.forEach( entry =>{
            console.log( "entry.isIntersecting", entry.isIntersecting)
            if(entry.isIntersecting){
                circle.classList.add('active')
            } else {
                circle.classList.remove('active')
            }
        })
  }

 let options ={
  root: null,
  rootMargin: '0px',
  threshold: 0
}
let observer = new IntersectionObserver(changeColor, options)
let target = document.querySelector('.two')
observer.observe(target)
// observe할 대상으로 target를 주고 target이 변경이 되면 observer로 지정된 즉,
// const changeColor= (entries, observer) =>{  }를 실행하도록 한다. 이때
// changeColor는 어떤 일을 해야 하는지를 알려주는 것이다

```
코드출처 ) https://medium.com/@syogifse/intersection-observer-api ~ ,
https://codepen.io/ygsjv/pen/oNGREeR






