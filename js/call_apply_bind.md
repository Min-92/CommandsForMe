# Call, Apply, Bind

### Call, Apply


- call 과 apply  는 주어진 this값과 인수와 함께 함수를 호출한다.
- call과 apply 는 거의 동일하지만 중요한 차이는 call 은 **인수목록을** apply는 **인수 배열 하나**를 받는다는 점이다.



###### function.prototype.call()

- 함수를 호출하면서 call을 사용하고 this로 사용할 객체를 넘기면 해당 함수가 주어진 객체의 메쏘드인 것처럼 사용할수 있다.

fun.call(thisArg[, arg1[, arg2[, ....]]])

```
    const min = {
        name : 'Min'
    };

    const wangmin = {
        name : 'wangmin'
    };

    //이 함수는 어떤 객체에도 연결되지 않았지만 this를 사용함.
    function greet(){
        return `Hello, I'm ${this.name}`;
    };

    console.log(greet());             
    console.log(greet.call(min));    
    console.log(greet.call(wangmin));
    
    //출력
    Hello, I'm undefined
    Hello, I'm Min
    Hello, I'm wangmin
```



```
    function update(birthYear, occupation){
        this.birthYear = birthYear;
        this.occupation = occupation;
    };
    console.log(min);
    update.call(min, 1949, 'singer'); // min 변경
    console.log(min);

    console.log(wangmin);
    update.call(wangmin, 1942, 'actress'); // wangmin 변경
    console.log(wangmin);
```

```
    //출력
    { name: 'Min' }
    { name: 'Min', birthYear: 1949, occupation: 'singer' }
    { name: 'wangmin' }
    { name: 'wangmin', birthYear: 1942, occupation: 'actress' }
```



###### function.prototype.apply()

fun.apply(thisArg, [argsArray])

- apply는 매개변수를 처리한는 방법을 제외하면 call과 완전히 같다.

- 배열로 매개변수를 받는다

  ```
  update.apply(min, [1955, 'actor']);
  console.log(min);
  
  update.apply(wangmin, [1918, 'writer']);
  console.log(wangmin);
  ```

  ```
  //출력
  { name: 'Min', birthYear: 1955, occupation: 'actor' }
  { name: 'wangmin', birthYear: 1918, occupation: 'writer' }
  ```

- apply는 배열 요소를 함수 매개변수로 사용 해야 할 때 유용하다

- 흔히 최댓값, 최솟값을 구할 때 사용한다

  ```
      const arr = [2,3,-5,15,7];
  
      Math.min.apply(null, arr); // -5
      Math.max.apply(null, arr); // 15
      
     //max,min은 this값에 상관 없이 작동한다
  ```



###### function.prototype.bind()

func.bind(thisArg[, arg1[, arg2[, ...]]])

- bind는 새로운 바인딩한 함수를 만든다
- 바인딩한 함수는 원본 함수 객체를 감싸는 함수

```
const updatemin = update.bind(min);

updatemin(1904, "actor");
console.log(min);

console.log(wangmin);
updatemin.call(wangmin, 1274, "king");
console.log(min);
```

```
//출력
{ name: 'Min', birthYear: 1904, occupation: 'actor' }
{ name: 'wangmin', birthYear: 1918, occupation: 'writer' }
{ name: 'wangmin', birthYear: 1918, occupation: 'writer' }
{ name: 'Min', birthYear: 1274, occupation: 'king' }
```

updatemin 함수는 영구적으로 this 값이 min으로 고정되어 있기 때문에 call 을 이용하더라도 변경이 불가능하다.

영구적으로 바꾸므로 찾기 어려운 버그의 원인이 될 수도 있다.



### reference

- <https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Function/apply>
- <https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Function/call>
- <https://ibrahimovic.tistory.com/29>