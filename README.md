#### :peach: javascript

## 객체의 요소 할당 
```html
   <h1>객체연습</h1>
    <script>
 let user ={name:'Hong', age:18}
 console.log(user.name, user.age)

 let { surname, lastname} = user;
 console.log(surname) // 에러
 console.log(lastname)  // 에러

 // let { name, age} = user;
 // 객체에 사용된 키 를 사용해야 한다. 다른 이름은 에러
 let { age ,name} = user; 
 console.log(name)
 console.log(age)

    </script>
```



