#### :peach: javascript

## IntersectionObserver

Intersection Observer API는 타겟 엘리먼트가 조상 엘리먼트, 
또는 최상위 문서의 뷰포트(브라우저에서는 보통 브라우저의 viewport)의 교차영역에서 발생하는 변화를
비동기로 관찰하는 방법을 제공한다. 


### 기본구조 
```
const io = new IntersectionObserver(callback[, options]) 
```

callback: 타겟 엘리먼트가 교차되었을 때 실행할 함. 배열형식으로 리턴   
options: 
 - root : default: null, 브라우저의 viewport, 교차 영역의 기준이 될 root 엘리먼트. observe의 대상으로 등록할 엘리먼트는 반드시 root의 하위 엘리먼트여야 합니다.
 - rootMargin : default: '0px 0px 0px 0px , root 엘리먼트의 마진값. css에서 margin을 사용하는 방법으로 선언할 수 있고, 축약도 가능하다. px과 %로 표현할 수 있습니다. rootMargin 값에 따라 교차 영역이 확장 또는 축소된다.
 - threshold : default: 0 , 
     0.0부터 1.0 사이의 숫자 혹은 이 숫자들로 이루어진 배열로, 타겟 엘리먼트에 대한 교차 영역 비율을 의미합니다. 0.0의 경우 타겟 엘리먼트가 교차영역에 진입했을 시점에 observer를 실행하는 것을 의미하고, 1.0의 경우 타켓 엘리먼트 전체가 교차영역에 들어왔을 때 observer를 실행하는 것을 의미합니다.

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


참고 ) https://blog.hyeyoonjung.com/2019/01/09/intersectionobserver-tutorial/
https://developer.mozilla.org/ko/docs/Web/API/IntersectionObserver/IntersectionObserver
