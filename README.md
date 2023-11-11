#### :peach: javascript

### node.js에서 자바스크립트의 파일은 command 명령어로 실행하기

[myfile1.js]
```js
const people =['크롱','포비','패티','뽀로로'];
module.exports = people
```

[myfile2.js]

```js
const abc = require('./myfile1')
console.log(abc)

```
2개의 파일을 작성한 후에 cmd 실행 하고 
``` > node myfile2.js 엔터  ```   people 배열의 내용이 나온다.  

cmd 모드에서는 아직 export, import가 기본값으로 지정되어 있지않다. 그래서 import 를 사용시 에러가 발생한다 
node.js 기반의 경우 es6를 거의 지원하지만 그럼에도 불구하고 node.js는 commandjs 기반 모듈시스템를 사용하기 때문에 es6의 import, export 키워드를 사용할 수 없다.


