#### :peach: javascript





## ```__proto__```   
```js
const car = {
        wheels :4,
        drive(){
            console.log(`drive ${this.wheels}`)
        }
        }

        const bmw = {
            color:"red",
            navi:1
        }
       
        const benz = {
            color:"blue"
        }
        bmw.__proto__ = car;
        benz.__proto__ = car;
```

## new 키워드 
```js
const Bmw = function(color){
    this.color=color
}

Bmw.prototype.wheels =4;
Bmw.prototype.drive = function(){
    console.log('drive...')
}
const x5= new Bmw('red')
const x4 = new Bmw('green')
```

- hasOwnProperty
- instanceof
- x5.constructor === Bmw

## 클로저
“A closure is the combination of a function and the lexical environment within which that function was declared.”   

이것은 클로저로 선언된 부분의 위에서 선언된 변수( free variable)를 기억하고 자신이 호출될때의 상태를 기억하며, 자기자신이 리턴된다.  

```js
위의 내용에서 콘솔창에서 색상을 임의로 변경하면 
>x5.color="pink"
>'pink'
>x5.color
>'pink'

```
만약 임의로 변경하고 싶지 않다면 이때 클로저를 사용하면 된다     

```js
function Bmw(){
    let c = 'red'
    let getColor = function(){
        console.log(c)
    }
    return getColor;
}
let x5= Bmw()

브라우저 콘솔창에서
> x5()
>'red' 출력

------ 생성자를 사용하면
function Bmw(){
    let c = 'red'
    this.getColor = function(){   // this을 붙여주어야 한다. 
        return c
    }
}
let x5= new Bmw()

>브라우저 콘솔창에서 
>x5.getColor()
< 'red' 출력
``` 



