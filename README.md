#### :peach: javascript

## transitionend event   


The transitionend event is fired when a CSS transition has completed. In the case where a transition is removed before completion, such as if the transition-property is removed or display is set to none, then the event will not be generated.  

### 사용법
```
addEventListener("transitionend", (event) => {});

ontransitionend = (event) => {};

```


>transitionend 이벤트
transitionend 이벤트는 CSS transition 이 완료되면 발생한다. transition 속성이 제거되거나 display가 none으로 설정된 경우와 같이 완료 전에 transition이 제거된 경우에는 이벤트가 생성되지 않는다.

참고 : https://velog.io/@hyowon_lee/JavaScript-transitionend-%EC%9D%B4%EB%B2%A4%ED%8A%B8



