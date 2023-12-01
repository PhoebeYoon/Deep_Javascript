#### :peach: javascript

## transitionend event   


The transitionend event is fired when a CSS transition has completed. In the case where a transition is removed before completion, such as if the transition-property is removed or display is set to none, then the event will not be generated.  

### 사용법
```
addEventListener("transitionend", (event) => {});

ontransitionend = (event) => {};

```
### 예제
```
<style>
.transition {
  width: 100px;
  height: 100px;
  background: rgba(255, 0, 0, 1);
  transition-property: transform, background;
  transition-duration: 2s;
  transition-delay: 1s;
}

.transition:hover {
  transform: rotate(90deg);
  background: rgba(255, 0, 0, 0);
}
</style>


<div class="transition">Hover over me</div>
<div class="message"></div>

<script>
const message = document.querySelector(".message");
const el = document.querySelector(".transition");

el.addEventListener("transitionrun", () => {
  message.textContent = "transitionrun fired";
});

el.addEventListener("transitionstart", () => {
  message.textContent = "transitionstart fired";
});

el.addEventListener("transitioncancel", () => {
  message.textContent = "transitioncancel fired";
});

el.addEventListener("transitionend", () => {
  message.textContent = "transitionend fired";
});
</script>

```




>transitionend 이벤트
transitionend 이벤트는 CSS transition 이 완료되면 발생한다. transition 속성이 제거되거나 display가 none으로 설정된 경우와 같이 완료 전에 transition이 제거된 경우에는 이벤트가 생성되지 않는다.

참고 : https://velog.io/@hyowon_lee/JavaScript-transitionend-%EC%9D%B4%EB%B2%A4%ED%8A%B8



