#### :peach: javascript


## RESTful 웹 서비스 
웹서비스 디자인 표준이다. 자원을 다루는 방법과 특정 웹페이지로 접근하는 방법을 어떤 형태로 구성한다는 것이다.  

|메소드 | 경로 | 설명
|---|---|---|
| GET| /user | 모든 사용자의 정보를 조회
|POST| /user| 사용자를 추가한다|
|GET | /user/:id|  특정 사용자의 정보를 조회|
|PUT| /user/:id|특정 사용자의 정보를 수정|
|DELETE| /user/:id|특정 사용자의 정보를 삭제|


```js
const express = require('express');
const bodyParser = require('body-parser');
const app = express();

app.listen(52273, ()=>{
    console.log('Server is running... http://127.0.0.1:52273')
})


app.use(bodyParser.urlencoded( { extended: false}))

let userCounter =0;
const users=[];

// 라우터
app.get('/user', (req, res)=>{
    res.send(users)
})

app.post('/user', (req, res)=>{

    const body = req.body;
    if( ! body.name) 
        return res.status(400).send('name를 보내주세요')
    else if( !body.region) 
        return res.status(400).send('name를 보내주세요')
    
    const name = body.name;
    const region = body.region;
 
    const data = {
        id: userCounter++,
        name :name,
        region : region
    }
    users.push(data)
   
    res.send(data)
})



app.get('/user/:id', (req,res)=>{
    const id = req.params.id;
    const filtered = users.filter( (user)=> user.id ==id)

    if(filtered.length ==1)
      res.send(filtered[0])
    else 
        res.status(404).send('데이터가 존재하지 않습니다')
})

app.put('/user/:id', (req,res)=>{
    const id= req.params.id;
    let isExist = false;
    // 데이터를 수정
    users.forEach((user) =>{

        if(user.id == id){
            isExist = true;
            if(req.body.name)
                users[id].name = req.body.name;
            if(req.body.region) 
                users[id].region = req.body.region;

            res.send(user)
        }
    })

   // 데이터가 존재하지 않는다면
    if(!isExist) 
        res.status(404).send('데이터가 존재하지 않습니다.')

})


app.delete('/user/:id', (req,res)=>{
    const id = req.params.id;
    let deleteUser =null;

    for(let i=users.length-1 ; i>=0; i--){
        if( users[i].id ==id){
            deleteUser = users[i]
            users.splice(i,1)
            break;
        }
    }

    if(deleteUser)
        res.send(deleteUser)
    else 
        res.status(404).send('데이터가 존재하지 않습니다.')
})

```
> 이때 GET 이외의 요청은 모두 x-www-form-urlencoded 방식으로 데이터를 전달한다. 따라서 body-parser를 사용해 클라이언트에서 데이터를 분석해야 한다. 


### postman을 이용하여 POST, GET 요청을 만들어보자 

postman 데스크탑을 설치합니다.    

<img width="600" alt="스크린샷 2023-12-09 오전 12 23 51" src="https://github.com/PhoebeYoon/Deep_Javascript/assets/48478079/80638b6f-27be-49e4-89d4-f4d1235bab2f">   

몇개의 데이터를 더 입력합니다.   

   
<img width="600" alt="스크린샷 2023-12-09 오전 12 24 42" src="https://github.com/PhoebeYoon/Deep_Javascript/assets/48478079/f8bc8915-7e1f-4adb-8563-6e9b352324a2">



``` > node index.js  ```  서버를 실행하고 웹브라우저로 접속해 보면 아래와 같다.  

<img width="706" alt="스크린샷 2023-12-09 오전 12 30 27" src="https://github.com/PhoebeYoon/Deep_Javascript/assets/48478079/b3f22f7b-b8f6-4d43-8e95-96c329d9832a">


id가 0 을 접속하면   
<img width="300" alt="스크린샷 2023-12-09 오전 12 33 55" src="https://github.com/PhoebeYoon/Deep_Javascript/assets/48478079/8609d137-5759-409b-a33f-e898a9fa95f2">

id가 1을 접속하면  
<img width="300" alt="스크린샷 2023-12-09 오전 12 35 18" src="https://github.com/PhoebeYoon/Deep_Javascript/assets/48478079/6a6fe839-1c36-4632-a857-91515f832a6d">




