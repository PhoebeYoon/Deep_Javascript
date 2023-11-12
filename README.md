#### :peach: javascript

## 함수의 정의 여러가지 와 호출방법

```html
<h1>함수의 호출</h1>
 함수란 반복적으로 해야 하는 문장들을 미리 만들어 놓고
 필요시에 함수를 호출하여 해당 내용을 실행하도록 만들어 놓은 구조
 <script>
    // 1. 일반함수 정의 및 호출
      sayHello('Choi');
    function sayHello(boy){
        console.log(` ${boy} Hello  ~~ `)
    }
    sayHello('Kim');

    // 2. 함수를 변수에 할당하고 그 변수를 함수로 호출한다
    let func = sayHello;
    func('Park')

    // 3. 즉시실행함수
    let instant = (function(){ 
        console.log("즉시실행함수")
    })();
    // 4. 매개변수가 언급되지 않은  함수에서 매개변수출력
  function showSub(){
    console.log(`${arguments[0]}`)
    console.log(`${arguments[1]}`)
 }
 showSub('html','css')

 // 5. 스프레드 연산자를 이용한 함수

 function add(...num) {
    let result =0;
    num.forEach(item =>{
        result +=item
    })
    console.log('보내온 숫자의 합계는 ', result)
}

add(1,2,3,4,5)
add(100,4,56,34,90,6,2,11)

// 6. 매개변수에 스프레드 연산자 사용
function user(name, age, ...skills){
    this.name = name;
    this.age =age;
    this.skills =skills;
 }
 console.log(user('Tom', 30, 'html', 'css')); 에러발생


// 7. 주의 함수의 이름의 첫자는 대문자 
function User(name, age, ...skills){
    this.name = name;
    this.age =age;
    this.skills =skills;
 }

let user1 = new User('Tom', 30, 'html', 'css')
console.log(user1)
console.log(user1.skills)

const user2 = new User('Mike', 25, 'html', 'css', 'js','vue')
console.log(user2)
console.log(user2.skills)

```

