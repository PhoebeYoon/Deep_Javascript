#### :peach: javascript





## __proto__
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
```js
위의 내용에서 콘솔창에서 색상을 임의로 변경하면 
>x5.color="pink"
>'pink'
>x5.color
>'pink'

```
만약 임의로 변경하고 싶지 않다면 이때 클로저를 사용하면 된다     

```js
const Bmw = function(color){
    this.c = color
    this.getColor = function(){
        console.log(this.c)
    }
}
const x5= new Bmw('yellow')
``` 



