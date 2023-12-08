#### :peach: javascript


## node.js 환경으로 서버 자바스크립트
[1].   
``` js
[index.js]
const express = require('express')
const app = express();
app.use( (req,res)=>{
    res.send('<h1> Server ... </h1>')
  })

app.listen(52273, ()=>{
    console.log('Server is running... http://127.0.0.1:52273')
})

> node index.js
```

이렇게 하고 터미널에 나오는 http://127.0.0.1:52273 열면 브라우저로 해당 내용이 보인다.  
[2].   
```
const express = require('express')
const app = express();

app.get('/page/:name', (req,res)=>{
    const name = req.params.name
    res.send(`<h1> ${name} </h1>`)
})

app.listen(52273, ()=>{
    console.log('Server is running... http://127.0.0.1:52273')
})

```
위의것과 비슷하지만 http://127.0.0.1:52273를 브라우저창으로 열어도 ~ /get 이라고 나오면서 에러처럼 보인다.    
이것은 get문의 형식대로 url 이 들어오지 않았기 때문이다.    
주소창에 /page/product 처럼 내용을 입력해야 제대로 나온다    

또한 **:id** ,  **:name** 는 토큰형식으로 접근한 것이다.   
토큰은 ```  :토큰이름  ``` 의 형태를 가진다.   

[1]은 res.send()로 라우팅없기 때문에 바로 내용이 브라우저에 출력되고,  페이지 라우팅을 사용하려면 express의 라우팅을 해주는 메소드와 토큰방식으로 접근해야 한다.  

### express 모듈를 사용한 서버 생성과 실행에 관련된 명령어
1. express() - 서버 어플리케이션 객체를 생성한다. ex) 'const app = express();' 
2. app.use() - 요청이 왔을때 실행할 함수를 지정
3. app.listen() - 서버를 실행


### express 라우팅 메소드
express는 페이지 라이팅을 지원한다.  페이지 라이팅을 할때는 위에서 언급한대로 토큰형식으로 각각의 페이지를 접근해야 한다.   
``` app.get('/page/:name' ~ ) ```    
``` app.get('/page/:id' ~ ) ```   

:name , :id 가 토큰형식대로 표현한 것이고 이것을 브라우저에서 확인할때는  url에  
```  http://127.0.0.1:52273/page/products  ```   
```  http://127.0.0.1:52273/page/30  ```    처럼 주소창에 적어야 한다.  
또한, **req에는 params라는 속성이 있는데**  이 속성을 이용하여 사용자가 어떤 토큰을 사용했는지 알 수 있다. 



|메소드| 설명|
|--|---|
|get (path, callback)   | get요청이 발생했을때 이벤트 리스너를 지정한다|
|post(path, callback)  |  post  요청이 발생했을때 이벤트 리스너를 지정한다|
|put (path, callback)  |  put  요청이 발생했을때 이벤트 리스너를 지정한다|
|delete (path, callback) | delete 요청이 발생했을때 이벤트 리스너를 지정한다|    
|all (path, callback)  |  모든 요청이 발생했을때 이벤트 리스너를 지정한다  |



### response 객체
- send() : 데이터본문을 제공
- status() : 상태코드를 제공
- set() : 헤더를 설정




