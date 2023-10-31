#### :peach: javascript

Event 인터페이스의 읽기 전용 속성인 isTrusted는, 이벤트가 사용자 행위에 의하여 발생되었으면 true이고 이벤트가 스크립트로 인해 생성 또는 수정되었거나 dispatchEvent를 통해 보내졌으면 false인 논리 값이다.  

``` js
if (e.isTrusted) {
  /* The event is trusted */
} else {
  /* The event is not trusted */
}

```


``` html 
<!DOCTYPE html>
<html>
<body>

<p>Click this button to invoke an onclick event, and check whether it is trusted:</p>
<button id="myBtn" onclick="myFunction(event)">Try it</button>


<p>Click this button to trigger an onclick event by a script, and check whether it is trusted:</p>
<button onclick="triggerClick()">Try it</button>


<script>
// 유저가 클릭해서
function myFunction(event) {
  if ("isTrusted" in event) {
    if (event.isTrusted) {
      alert ("The " + event.type + " event is trusted.");
    } else {
      alert ("The " + event.type + " event is not trusted.");
    }
  } else {
    alert ("The isTrusted property is not supported by your browser");
  }
}

function triggerClick() {
  var btn = document.getElementById("myBtn");
  btn.click();
// btn에 클릭이벤트를 발생
} 
</script>

</body>
</html>
```
