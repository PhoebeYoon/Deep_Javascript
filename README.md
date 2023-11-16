#### :peach: javascript



## fetch()
구문  
```
fetch(resource) :  
fetch(resource, options) :

resource :  취득하려는 리소스의 URL을 제공하는 문자열 또는 URL처럼 문자열 변환자를 포함한 객체.   
options : 요청에 적용하고자 하는 사용자 지정 설정을 포함하는 객체이며 다음과 같은 것이 있다. 
    - method 
    - headers
    - body 
```

```
fetch(url, options)
  .then(response => response.json())
  .then(result => /* 결과 처리 */)   
```
에서  
**응답 객체의 프로퍼티는 다음과 같습니다.**    
response.status – 응답의 HTTP 코드    
response.ok – 응답 상태가 200과 299 사이에 있는 경우 true    
response.headers – 맵과 유사한 형태의 HTTP 헤더    

**응답 본문을 얻으려면 다음과 같은 메서드를 사용하면 됩니다.**   
response.text() – 응답을 텍스트 형태로 반환함   
response.json() – 응답을 파싱해 JSON 객체로 변경함      
response.formData() – 응답을 FormData 객체 형태로 반환(form/multipart 인코딩에 대한 내용은 다음 챕터에서 다룸)    
response.blob() – 응답을 Blob(타입이 있는 바이너리 데이터) 형태로 반환     
response.arrayBuffer() – 응답을 ArrayBuffer(바이너리 데이터를 로우 레벨로 표현한 것) 형태로 반환    


**위의 내용을 종합하면 fetch 옵션은 다음과 같습니다.**    
method – HTTP 메서드    
headers – 요청 헤드가 담긴 객체(제약 사항이 있음)    
body – 보내려는 데이터(요청 본문)로 string이나 FormData, BufferSource, Blob, UrlSearchParams 객체 형태    

참조 : https://ko.javascript.info/fetch    
