#### :peach: javascript


```html
  <h1>구조분해 할당, spread 연산자</h1>
    <script>
    //   1. 
    //   const i = 10;
    //   console.log(i)

    // 2.
    //   let arr =[11,12,13]
    //   console.log(arr[0], arr[1], arr[2]) 

    // 3.
    // const [a,b,c,...x] = [1,2,3, 100,200,300]
    // console.log(a)
    // console.log(b)
    // console.log(c)
    // console.log(x)
  
    //4. 배열의 복사
    // let arr1 = [21,22,23]
    // let arr2 = arr1;
    //  console.log(arr2[0])

    //  let arr3 =[...arr1]
    //  console.log(arr3[0])
    
   // 5. 
    // let fruit = [31,32,33,34,35]
    // fruit.forEach( (item)=>{
    //     console.log(item)
    // })

    // fruit.forEach( item=>{
    //     console.log(item)
    // })

     //6.  배열의 교환
     //console.log(" 배열의 교환")
    
    // let [c,d] = [100,200];
    // console.log(c,d);

    // [c,d] =[d,c]; 
    // console.log(c,d);


    // 7. 할당
//  let str="Hong-Gil-Dong"
//  let [name1,name2,name3] = str.split('-')
//  console.log(name1)
//  console.log(name2)
//  console.log(name3)

//  let users =['Smith','Peter',"John"]
//  let [user1, user2,user3] = users;
//  console.log(user1)
//  console.log(user2)
//  console.log(user3)

// 8. 기본값지정
// let [a,b,c] =[100,200]
// console.log(a)
// console.log(c)
// let [a=1,b=2,c=3] =[100,200]
// console.log(a)
// console.log(c)

    </script>

```
