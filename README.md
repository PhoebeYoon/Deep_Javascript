#### :peach: javascript

작성 중... 


💢 주석처리 ``` /**    */  ``` 는 .js 파일에서 사용



### 위의 파일 fullstack-javascript.zip 에서 json 부분 다룰때  실행방법 
1. 터미널에서 npm install -g json-server
2. db.json
3.
 ```json
  {
 "posts" :[{"id":1, "title":"json-server"}],
 "comments" : [{"id":1 , "body":"some comment"}],
 "profile":{"name":"ttt"}
}
```

4. json-server --watch db.json 실행 후 터미널 창에
```
 Resources
  http://localhost:3000/posts
  http://localhost:3000/comments
  http://localhost:3000/profile

  Home
  http://localhost:3000
  ```
출력된다.  

5. 파일 중 38_fetch.html 파일을 vscode로 불러온 후 설치된 확장 프로그램 Live Server 를 이용하여 브라우저로 연다.  


📖  명령어 참조   
https://mirabo.tistory.com/178

https://ko.javascript.info/fetch     
https://docs.fileformat.com/ko/web/json/   

📖 참조영상 :  
https://www.youtube.com/watch?v=FhguwBJeqWs&list=PL4cUxeGkcC9haFPT7J25Q9GRB_ZkFrQAc&index=2   
