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
1.
const Bmw = function (color){
    const c = color;
    this.getColor = function(){
        console.log(c)
    }
}
const x5 = new Bmw('red')
이렇게 작성하고
브라우저 콘솔창에서
>x5.getColor()
< red
>x5.c ="pink" 로 주고
>x5.c 엔터 하면 'pink'로 출력되지만
>x5.getColor() 로 주면 여전히 red 가 출력되므로 결과적으로 값이 변경되질 않는다.
>x5 instanceof Bmw // 결과는 true  


2.
function Bmw(){
    let c = 'red'
    this.getColor = function(){   // this을 붙여주어야 한다. 
        return c
    }
}
let x5= new Bmw()

>브라우저 콘솔창에서 
>x5.getColor()
<'red' 출력

참고로 , this.getColor  ~ 대신 let getColor ~ 로 하게되면
해당 스코프 아래에 return getColor;를 해주고 x5.getColor() 가 아닌 x5()로 컬러러값을 얻는다.
생각해보면 당연하다. let getColor는 해당 함수를 변수로 선언했기 때문에 getColor 변수를 리턴해야 하고
 x5() 함수 형태로 접근해야 한다.
this.getColor로 적었다면 return getColor; 없어도 되고 접근할때 x5.getColor() 함수로 컬러값을 얻어야 한다. 

``` 



