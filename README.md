#### :peach: javascript


## window.matchMedia()
사용방법 : window.matchMedia(mediaQueryString); 

Window.matchMedia() 메서드는 주어진 미디어 쿼리 문자열의 분석 결과를 나타내는 MediaQueryList (en-US) 객체를 반환합니다.  
MediaQueryList에 말 그대로 media query 절이 들어간다. MediaQueryList 인터페이스는 상위 인터페이스에서 속성을 상속합니다.  
matches는 Instance properties에 속하며, media 라는 읽기전용 속성도 있습니다.

### Instance properties
-  matches : 문서가 현재 미디어 쿼리 목록과 일치하는 경우 true를 반환하고 그렇지 않은 경우 false를 반환하는 부울 값입니다.
-  media :직렬화된 미디어 쿼리를 나타내는 문자열입니다.
### Instance methods
- addListener  // 이것은 이전 버전의 호환을 위해 존재하므로 addEventListener() 사용권고
- removeListener // 이것은 이전 버전의 호환을 위한 것으로 removeEventListener() 사용권고 합니다

### Events
- change : 문서에 대해 미디어 쿼리를 실행한 결과가 변경될 때 MediaQueryList로 전송됩니다 ( 맨 아래 예제 참조)


```html
<div> 내용 </div>
<script>
    if(window.matchMedia("(min-width: 800px)").matches) {
        // 뷰포트 너비가 800픽셀이상
        document.querySelector('div').style.backgroundColor="red"
     } 
</script>

```
위의 예제에서 
```
console.log(window.matchMedia("(min-width: 800px)").matches)  // false or ture
console.log(window.matchMedia("(min-width: 800px)").media)  // (min-width: 800px) 출력
```


[change  이벤트]
```html
<p>Lorem ipsum dolor sit amet consectetur, adipisicing elit. Similique corporis, reiciendis impedit at non sunt laboriosam earum sit necessitatibus id incidunt harum neque tempore ad consequuntur nulla. Culpa, eligendi illo?</p>
    <script>
const para = document.querySelector("p");
const mql = window.matchMedia("(max-width: 600px)");

function screenTest(e) {
  if (e.matches) {
    /* the viewport is 600 pixels wide or less */
    para.textContent = "This is a narrow screen — less than 600px wide.";
    document.body.style.backgroundColor = "red";
  } else {
    /* the viewport is more than 600 pixels wide */
    para.textContent = "This is a wide screen — more than 600px wide.";
    document.body.style.backgroundColor = "blue";
  }
}

mql.addEventListener("change", screenTest);
    </script>
```




