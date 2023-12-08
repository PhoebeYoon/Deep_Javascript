#### :peach: javascript


## Content-Type

서버가 클라이언트 웹 브라우저에 데이터를 제공하면 웹 브라우저는 해당 데이터가 어떤 데이터인지 구별해야 합니다.
이때 사용하는 것이 Content-Type 이라는 것입니다.
서버가 Content-Type 을 제공해주면 웹 브라우저는 헤더를 확인하고 제공된 데이터 형태를 확인하는데 이런 형태는 MIME 라는 문자열로 제공됩니다.

| MIME 형식 | 설명|
|---|---|
|text/plain | 기본적인 텍스트를 의히 |  
| text/html | html 데이터를 의미 |
|image/png| | png데이터를 의미 |
|audio/ mpe |  mp3 음악파일를 의미 |
|video /mpeg |   mpeg 비디오 파일을 의미 |
|application/json|  json 데이터를 의미  |
|multipart/form-data|  입력 양식데이터를 의미  |

## 이미지 파일을 전송한다고 할때 

```js
const express = require('express');
const fs = require('fs') ;
const app = express();

app.get('/image', (req, res)=>{       // http://127.0.0.1:52273/image 경로로 접근
    fs.readFile('image.png', (err, data)=>{    // 불러올 이미지파일 이름은 image.png dlek
        res.type('image/png');
        res.send(data) // 해당 이미지는 data로 받는다
    })
})

app.listen(52273, ()=>{
    console.log('Server is running... http://127.0.0.1:52273')
})

```

### HTTP 상태코드   
1xx : 처리 중   
2xx : 성공     
3xx : 리다이렉트    
4xx : 클라이언트 오류   
5xx : 서버 오류     


## response객체들
Response.body (Read only)      
Response.headers (Read only)    
Response.ok (Read only)    
Response.redirected  (Read only)    
Response.status (Read only)    
Response.type (Read only)   
Response.url (Read only)   

### Static methods
Response.error()     
Response.redirect()     
Response.json()     
Response.clone()      
Response.blob()      
Response.text()    






