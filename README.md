#### :peach: javascript


## Object란

자바스크립트는 단순한 객체기반(object-based) 패러다임을 기반으로 설계되었다.   
객체는 속성들의 집합이고 속성은 이름(키)과 값의 조합으로 이루어졌다.  또한 속성의 값은 함수가 될 수 있는데 이런 속성을 메소드(method) 라고 한다  

```
const person = {
  firstName: "John",
  lastName: "Doe",
  age: 50,
  eyeColor: "blue"
};
```
### 오브젝트 접근해서 값을 가져오기   
1. 오브젝트이름.속성이름  
2. 오브젝트이름['속성이름']   


```
const man ={
    adult: false,
    name : "Kim",
    age : 17,
    height: 170,
    weight: 60,
    school : 'SeaMeng',
    isHandsome:false
}
console.log(man.adult)
console.log(man.name)
console.log("--- value만 출력")
for(let key in man) {
    console.log(man[key])
}

console.log('----- key만 출력')
for(let key in man) {
    console.log(key)
}

```

### 속성값 약식
```js
function makeUser(name, age){
    return { 
        name:name,
        age:age
    }
}
let user1 = makeUser('Park' , 15)
console.log(user1.name, user1.age)
```


### 매개변수 없는 오브젝트와 메소드
```js

const person = {
  firstName: "John",
  lastName : "Doe",
  id       : 5566,
  fullName : function() {
    return this.firstName + " " + this.lastName;
  }
};
```
여기서의 this는 객체를 가리킨다.  




### 매개변수를 갖는 오브젝트와 메소드
위의 예제에 추가해서 사용해 보자.  
아래와 같은 형태를 객체리터럴 이라고 한다. 
```
const man ={
    adult: false,
    name : "Kim",
    age : 17,
    height: 170,
    weight: 60,
    school : 'SeaMeng',
    isHandsome:false,
    isReturn : function(yesno){
        console.log(` ${this.name}의 킥보드 반환여부는  ${yesno} 이다`)
    }
}

man.isReturn(true); //결과는 Kim의 킥보드 반환여부는 true이다
```


```js
    <script>
let circle = {
    color : 'yellow',
    diameter : 100,
    radius : function() {
    return this.diameter / 2; 
    }
};
console.log(circle.color);
console.log(circle.diameter);
    </script>
```




