#### :peach: javascript

서버를 구성할때 우리가 express를 불러와서 사용하였다. 이는 서버 구성을 좀더 쉽게 하기 위해서인데, 이런 기능을 해 주는 것을 미들웨어라 부른다.   
use()를 미들웨어를 설정할때 사용한다.   
우리는 정적파일제공 미들웨어, morgan미들웨어, body-parser 미들웨어를 살펴볼 것이다.

## 정적파일 미들웨어

정적파일이란   
이미지, 음악, 자바스크립트 파일, 스타일시트와 같은 파일을 말하는데, 
use()는 이런 파일등을 어떤 폴더에 저장해 놓고 use()로 해당 폴더를 지정한 뒤 모조건 그 폴더에서 불러오겠다는 뜻으로 사용한다.    

sample.png 파일을 \public 폴더로 옮긴다.


```js

const express = require('express');
const fs = require('fs') ;
const app = express();

app.use( express.static('public'))

app.get('/', (req, res)=>{
    fs.readFile('sample.png', (err, data)=>{
        res.type('image/png');
        res.send(data)
    })
})

app.listen(52273, ()=>{
    console.log('Server is running... http://127.0.0.1:52273')
})

1. 터미널에서 서버를 실행하고
2. 웹브라우저에서 http://127.0.0.1:52273/ 접속한 뒤 , 해당파일을 불러오면 되는데
http://127.0.0.1:52273/sample.png 라고만 하면 이 파일이 있는 실제폴더인 \public 폴더에서 파일을 가져온다 
```





