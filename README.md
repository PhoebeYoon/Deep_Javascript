#### :peach: javascript


## cloneNode()

노드 인터페이스의 cloneNode() 메서드는 이 메서드가 호출된 노드의 복제를 반환합니다. 이 매개 변수는 노드에 포함된 하위 트리도 복제되었는지 여부를 제어합니다. 노드를 복제하면 intrinsic (inline) listeners를 포함하여 모든 속성과 값이 복사됩니다.  
```html
 <div id="para1">
        clone test
    </div>
  <script>
      let p = document.getElementById("para1");
      let p_prime = p.cloneNode(true);
      document.body.appendChild(p_prime);
  </script>

```

