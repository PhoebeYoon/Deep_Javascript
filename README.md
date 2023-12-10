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


