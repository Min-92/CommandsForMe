# JavaScript

## 자바스크립트 버전
- ECMAScript(ES)의 버전에 따라서 결정되고 이를 실행 엔진이 반영한다.
- 2019년 현재는 ES2015(ES6) 기준

## 변수

- Scope(유효범위) : 변수의 수명을 의미
- 지역변수(local)
- 전역변수(global) 

1. var
    1. 함수레벨 스코프(Function-level scope)  

        - 전역변수로써 외부에서 참조가 가능하다
    2. var 생략 허용  

        - 암묵적 전역변수 양산 가능성
    3. 변수 호이스팅
        1. 선언단계
        2. 초기화단계
        3. 할당단계
        - 변수를 선언 이전에 참조 가능

2. let
    1. 블록레벨 스코프(Block-level scope)
        - 코드블록 내에서만 유효
    2. 중복선언 금지
    3. 변수 호이스팅
        - 3단계중 선언단계만 이루어짐
3. const
    1. 선언과 동시에 할당
    2. 재할당 불가

## 연산자
- 수학연산자
    - +,-,*,/,%
- 논리연산자
    - &&, ||, !
- 관계연산자
    - <,>,<=,>=,==,!=, ===, !==
- 삼항연산자
    - (조건) ? a : b ;
    - true -> a, false -> b

## Type
- 자바스크립트에서 타입은 선언할때가 아니고 실행타임에 결정된다
- 타입체크하는 명확한 방법은 없다
- toString.call 을 이용하거나 기본타입은 typeof 키워드를 사용

## 비교문,반복문, 분기문

### 비교문
1. If else
    - 조건에 해당하면 명령문을 실행
~~~
if(조건1){
    명령문1
}else if(조건2){
    명령문2
}else{
    명령문3
}
~~~

2. Switch
    - 표현이 case 와 같으면 따르는 명령을 실행
~~~
switch (expr) {
  case 'Oranges':
    console.log('Oranges are $0.59 a pound.');
    break;
  case 'Mangoes':
  default:
    console.log('Sorry, we are out of ' + expr + '.');
}
~~~

## 반복문
1. while
~~~
while(true){
    console.log("hello");
}
~~~
2. do while
~~~
do{
    console.log("hello");
}while(true);
~~~
3. for
~~~
for(var i = 0; i < N; i++){
    console.log("hello");
}
~~~
## 분기문
1. continue
~~~
for(var i = 0; i < N; i++){
    if(i === 3){
        continue;
    }
    console.log("hello");
}
~~~
2. break
~~~
for(var i = 0; i < N; i++){
    if(i === 3){
        break;
    }
    console.log("hello");
}
~~~
3. return
~~~
for(var i = 0; i < N; i++){
    if(i === 3){
        return 0;
    }
    console.log("hello");
}
~~~



## 반복문 추가

1. for in
~~~
for(var i in object1){
    cosole.log("hello");
}
~~~
2. for of
~~~
for (var value of object){
    console.log(value);
}
~~~



## 배열(Array) "[]"

------

### 배열 선언

~~~
var arr = new Array();
var arr = new Array(2);
var arr = [1,2,3];

~~~

### 배열 속성

Array.length

### 배열 메소드

#### 추가

~~~
array.push(); // 배열 마지막에 원소 추가
array = array.concat(['a','b']); // 복수 원소 추가
array.unshift(0); // 첫번째 원소에 추가하고 기존값들 인덱스 1씩 추가
array.splice(n,a,data); // 배열의 n번째부터 a갯수 만큼 삭제하고 data를 추가
~~~

#### 제거

~~~
array.shift(); // 첫번재 원소 제거
array.pop(); // 마지막 원소 제거
~~~

#### 정렬

~~~
array.sort(); //숫자의 경우 정상적으로 이루어지진 않는다
array.reverse(); //역순정렬

//숫자 정렬법
function sortNumber(a,b){
    return a-b;
}
array.sort(sortNumber);

//역순정렬
function sortNumber(a,b){
    return b-a;
}
array.sort(sortNumber);
~~~

#### forEach

forEach() 메소드는 배열의 인자값만큼 fucntion이 반복된다.  
3개의 매개변수 를 사용할수 있다.

- item : 배열 내 현재 값
- index : 배열내 현재값의 인덱스
- array : 현재 배열

~~~
var sum = 0;  
var arr = [5,13,8];  

arr.forEach(function(item,index,array){  
  sum +=item;  
});  

console.log(sum);
~~~



## 객체(Object) ''{}''

------

-  배열과 유사한 역할
- 식별자로 key 를 사용
- key 와 value 로 이루어짐

### 선언

- 객체 key 값에는 ""가 필요없다

- 하지만 아래의 경우엔 오류발생

- ~~~
  var grades = {
      list : {name : '이민재', nickname : '왕민'},
       show : function(){
          console.log("Hello");
      }
  }
  console.log(grades[list]);// grades['list'] 가 되어야함 
  ~~~

  

```
var grade1 = {name : '이민재' , nickname : '왕민' };

var grade2 = ();
grade2['name'] = '이민재';
grade2['nickname'] = '왕민';

var grade3 = new Object();
grade2['name'] = '이민재';
grade2['nickname'] = '왕민';
```

### 속성에 접근

~~~
grade1['name']
grade1['na'+'me']
grade1.name
~~~

###### 데이터 추가

```
let friend = {key : 'value'};
friend.age = 20;
console.log(friend); //{ key: 'value', age: 20 }
```



### 탐색(반복문)

~~~
for(key in grade1){
	console.log(`key : ${key}, value : ${grade1[key]});
}
~~~



### 객체에 담길 수 있는것

- 이를 이용해서 객체를 그룹화 가능
- -> 객체지향 프로그래밍

~~~
var grades = {
    'list' : {name : '이민재', nickname : '왕민'},
    'show' : function(){
        console.log("Hello");
    }
}
console.log(grades['list']);
console.log(grades['list']['name']);
grades['show']();
~~~







## 진수변환

------

~~~
var dec = 123;

console.log(dec.toString(16)); //7b
~~~





## 함수

---

- javaScript 에서는 함수도 객체다 = 일종의 값이다

- First-class citizen(object) : 변수,매개변수, 리턴값으로 사용 될 수 있는 데이터

- 함수는 값이기 때문에 다른 함수의 인자로 전달될 수도 있다

- 객체에 저장된 함수를 메쏘드라 부른다

  ~~~
  function cal (func, num){
      return func(num);
  }
  function increase(num){
      return num+1;
  }
  console.log(cal(increase,1));
  ~~~

- 함수는 함수의 리턴값으로 사용 할 수도 있다.

  ~~~
  function cal(mode){
      var funcs = {
          'plus' : function(left,right){return left + right}
          'minus' : function(left,right){return left - right}
          
      }
      return funcs[mode];
  }
  
  console.log(cal('plus')(2,1)); // 3
  ~~~

- 배열의 값으로도 사용할 수 있다

  ~~~
  var process = [
      function(input) {return input + 10;},
      function(input) {return input*input;},
      function(input) {return input/2;}
  ];
  
  var input = 1;
  for(let i = 0; i < process.length; i++){
      input = process[i](input);
  	console.log(input);
  }
  // 11
  // 121
  // 60.5
  ~~~



### 함수 선언식

- 호이스팅에 영향

~~~
function areaC(r) {
    let area = 0;
    if(typeof r != "number"){
        throw "숫자를 입력하세요";
    }

    area = Math.PI*r*r;

    return area.toFixed(2);
}
~~~

### 함수 표현식

- 호이스팅에 영향을 받지 않음
- 클로져로 사용
- 콜백으로 사용

~~~
var areaC = function() {
    let area = 0;
    if(typeof r != "number"){
        throw "숫자를 입력하세요";
    }

    area = Math.PI*r*r;

    return area.toFixed(2);
}
~~~


### arrow function

```
function getName(name) {
   return "Kim " + name ;
}

//위 함수는 아래 arrow함수와 같다.
const getName = (name) => "Kim " + name;
```



### 콜백

- 어떠한 함수가 수신하는 인자가 함수인 경우

  ~~~
  var numbers = [20,10,9,8,7,6,5,4,3,2,1];
  function sortNumber(a,b){
      return a-b;
  }
  console.log(numbers.sort(sortNumber));
  
  // sortNumber : 콜백함수
  
  ~~~

  



### 클로저(Closure)

- 내부함수가 외부함수의 맥락에 접근 할 수 있는것을 가르킨다

  ~~~
  function outter(){
  	var title = 'coding everybody';
      function inner() {
          console.log(title);
      }
      inner();
  }
  outter(); // 내부함수 inner 가 외부함수 outter 에 있는 지역변수 title 에 접근
  ~~~

- 클로저는 독립적인 변수를 가리키는 함수이다. 또는 클로저 안에 정의된 함수는 만들어진 환경을 기억한다

  ~~~
  function outter(){
      var title = "coding everybody";
      return function(){
          console.log(title);
      }
  }
  inner = outter();
  inner(); // "coding everbody"
  ~~~

- private variable : 프로그램을 아무나 수정하지 못하도록

  ~~~
   function factory_movie(title){
      return{
          get_title : function(){
              return title;
          },
          set_title : function(_title){
              title = _title;
          }
      }
  }
  ghost = factory_movie('Ghost in the shell');
  matrix = factory_movie('Matrix');
  console.log(ghost.get_title()); //'Ghost in the shell'
  console.log(matrix.get_title()); //'Matrix'
  
  
  ghost.set_title('ghost');
  console.log(ghost.get_title()); // 'ghost'
  ~~~

## rest parameter
~~~
// Rest 파라미터 이전에, "arguments" 는 다음을 사용해 일반적인 배열로 변환될 수 있음

function f(a, b) {

  var normalArray = Array.prototype.slice.call(arguments);
  // -- 또는 --
  var normalArray = [].slice.call(arguments);
  // -- 또는 --
  var normalArray = Array.from(arguments);

  var first = normalArray.shift(); // OK, 첫 번째 인수를 반환
  var first = arguments.shift(); // ERROR (arguments 가 일반적인 배열이 아님)

}

// 이제 rest 파라미터를 사용해 쉽게 일반적인 배열에 접근할 수 있음

function f(...args) {
  var normalArray = args;
  var first = normalArray.shift(); // OK, 첫 번째 인수를 반환
}
~~~

## 재귀
- 함수가 함수 안에서 자신을 다시 호출하는 것
~~~
//팩토리얼 출력하는 재귀함수
function factorial(a){
    if(a === 1) {
        return a;
    }else{
    return a*factorial(a-1);
    }
        
}

console.log(factorial(10));

//피보나치 수열
function fibonacci(n){
    if(n===0){
        return n;
    }else if(n===1){
        return n;
    }else{
        return fibonacci(n-1)+fibonacci(n-2);
    }

}
console.log(fibonacci(11));

~~~



































### Reference

- [opentutorials](https://opentutorials.org/course/743/6508)

- [poiemaweb](https://poiemaweb.com/es6-block-scope)
- [MDN web docs](https://developer.mozilla.org/ko/)
- [nextstep](https://nextstep.camp/courses)
