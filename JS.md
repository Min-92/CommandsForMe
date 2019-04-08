# JavaScript

## 자바스크립트 버전
- ECMAScript(ES)의 버전에 따라서 결정되고 이를 실행 엔진이 반영한다.
- 2019년 현재는 ES2015(ES6) 기준

## 변수
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

## 함수
### 함수 선언
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
~~~
function getName(name) {
   return "Kim " + name ;
}

//위 함수는 아래 arrow함수와 같다.
const getName = (name) => "Kim " + name;
~~~

## 미션
1. 반지름을 입력받아 원의 넓이를 계산하는 함수를 만든다
2. 필요한 인자를 입력받아 사각형의 넓이를 계산하는 함수를 만든다
3. 필요한 인자를 입력받아 사다리꼴의 넓이를 계산하는 함수를 만든다
4. 필요한 인자를 입력받아 원기둥의 넓이를 계산하는 함수를 만든다
5. 숫자가 아니면 에러를 반환하도록 구현한다.
6. 인자의 갯수가 부족하면 에러를 반환한다.

~~~

function areaC(r) {
    let area = 0;
    if(arguments.length != 1){
        throw "인자 갯수가 맞지않습니다.";
    }
    if(typeof r != "number"){
        throw "숫자를 입력하세요";
    }

    area = Math.PI*r*r;

    return area.toFixed(2);
}

function areaR(a,b){
    let area = 0;
    if(arguments.length != 2){
        throw "인자 갯수가 맞지않습니다.";
    }
    if(typeof a != "number" || typeof b != "number"){
        throw "숫자를 입력하세요";
    }
    area = a*b;

    return area;
}

function areaT(a,h){
    let area = 0;
    if(arguments.length != 2){
        throw "인자 갯수가 맞지않습니다.";
    }
    if(typeof a != "number" || typeof h != "number"){
        throw "숫자를 입력하세요";
    }
    area = a*h;

    return area;
}

function areaS(r,h){
    let area = 0;
    if(arguments.length != 2){
        throw "인자 갯수가 맞지않습니다.";
    }
    if(typeof r != "number" || typeof h != "number"){
        throw "숫자를 입력하세요";
    }
    let AC = areaC(r);
    area = 2*AC+2*Math.PI*r*h;
    
    return area.toFixed(2);
}
~~~


### Reference
- [poiemaweb](https://poiemaweb.com/es6-block-scope)
- [MDN web docs](https://developer.mozilla.org/ko/)
- [nextstep](https://nextstep.camp/courses)
