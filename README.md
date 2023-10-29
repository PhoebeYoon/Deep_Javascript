#### :peach: javascript
## styleSheet 
css 스타일시트를 가리킨다.  document.styleSheets 를 사용하여 문서에 대한 CSSStyleSheet 목록을 가져온다.
HTMLStyleEleElement를 만들고 해당 시트 속성에 액세스하여 만들 수 있다. 

```html
<style>
#foo { background-color:red;} 
</style>

<div id='foo'>foo</div>
<script> document.styleSheets[0].disabled = false;</script> 
```
위의 속성에서 disabled=false 이기 때문에 배경색 빨강이 보인다. 만약 true로 바꾸게 되면 disabled 속성으로 인해 배경색이 보이질 않는다.

외부스타일시트를,   
[mystyle1.css]
```
#foo { background-color:red;} 
```

[mystyle2.css]
```
div {color:gold;}
```   

```html
<link rel="stylesheet" href="mystyle1.css">
<link rel="stylesheet" href="mystyle2.css">
<style>
빈css
</style>

<script>  console.log(document.styleSheets.length)  </script>
```
콘솔창에서 확인해 보면 3이 출력된다.   

이번에는, 
```
 <script>
        console.log(document.styleSheets.length)
        document.styleSheets[0].disabled = true;
</script> 
```   
이렇게하면 첫번째 스타일은 적용되지 않는다. 
이번에는  아래와 같이 하면 첫번째 css를 가리킨다
```js
    console.log(document.styleSheets.item(0)) 
```



