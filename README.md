#### :peach: javascript

## json 이란
참조 : https://docs.fileformat.com/ko/web/json/

JSON(JavaScript Object Notation)은 사람이 읽을 수 있는 텍스트를 사용하여 데이터를 저장하고 전송하는 데이터 공유를 위한 개방형 표준 파일 형식입니다. JSON 파일은 .json 확장자로 저장됩니다. JSON은 형식이 덜 필요하며 XML에 대한 좋은 대안입니다. JSON은 JavaScript에서 파생되지만 언어 독립적인 데이터 형식입니다. JSON의 생성 및 구문 분석은 많은 최신 프로그래밍 언어에서 지원됩니다. application/json은 JSON에 사용되는 미디어 유형입니다

## JSON 파일 구조 
JSON 데이터는 키/값 쌍으로 작성됩니다. 키와 값은 중간에 **콜론(:)** 으로 구분되며 왼쪽에는 키, 오른쪽에는 값이 있습니다. 다른 키/값 쌍은 **쉼표(,)로**  구분됩니다. 키는 “name"과 같이 **큰따옴표로**  묶인 문자열입니다. 값은 다음 유형일 수 있습니다.




```js
<script>
// stringify() - 자바스크립트 오브젝트, 혹은 배열 같은 데이터를 문자열로 변환    
//  클라이언트에서 서버로 전송할 때는 이렇게 stringify 함수를 사용해서 JSON 데이터 포맷에 해당하는 문자열로 변환해서 서버로 전송    
// 서버에서 클라이언트로 JSON 포맷으로 데이터가 전송되었을 때 , 문자,  parse() - 문자열로 되어 있는 JSON 포맷을 자바스크립트 오브젝트로 변환을 해줘요.    


   let person = {
      name: "홍길동",
      age: 22,
      tel: "010-0000-0000",
      address: "서울시",
      email: "hong@gmail.com",
      obj: {},
      arr: [],
};

      let arr = [3, 4, 5, 9];
      console.log(person)
      const strPerson = JSON.stringify(person)
      console.log(strPerson)

      console.log("-----")
      console.log(strPerson + "1111")
      let demo ='{ "fullname": "Tom", "Job":"Student"}'
      let ex = JSON.parse(demo);
      console.log(JSON.parse(demo))
    console.log(typeof ex)
    </script>


```
