#### :peach: javascript

## 배열복사

```js
<script>
// 배열의 복사 , 레퍼런스복사
let array = [1,2,3];
let arrayCopy = array
console.log(array)
console.log(arrayCopy)
console.log(array === arrayCopy)
arrayCopy[2] =1004; 
console.log(array[2])
console.log(arrayCopy[2])
// 복사된 배열의 내용이 바뀌면 원본 배열도 변경된다
console.log('배열복사에 스프레드 연산자 이용 / 레퍼런스복사')
let arr2 = [...array]
console.log(arr2)
console.log(arrayCopy)
arrayCopy[2] =20000;
console.log(arr2[2])
console.log(arrayCopy[2])
    </script>

```

