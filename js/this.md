# this 

---

### this 는 현재 실행 문맥이다

- this는 함수 내에서 함수 호출 맥락(context)를 의미한다.
- 실행 문맥이란 호출자가 누구인가와 같다.
- this는 그 소속, 객체를 가르킨다.
- 함수와 함수를 호출한 객체를 연결시켜주는 실질적 연결점 역할



- ##### 객체 소속이 아닌 메소드에서의 this

```
function func(){
    if(this === global){
        console.log('global');

    }
}
func(); // global
```

- ##### 객체 소속인 메소드에서의 this 

```
var o = {
    func : function(){
        if( o === this){
            console.log('o');
        }
    }   
}
o.func(); // o
```

- ##### 생성자를 이용해 객체를 생성한 경우

```
var funcThis = null; 
 
function Func(){
    funcThis = this;
}
var o1 = Func();
if(funcThis === global){
    console.log('global');
}
 
var o2 = new Func();
if(funcThis === o2){
    console.log('o2');
}

// global
// o2
```

- ##### class에서의  this

```
class test {
    constructor(obj){
        this.obj = this;
    }
    printThis(){
        console.log(this);
    }
}

myTest = new test;

myTest.printThis(); // test {}
```



- ##### 객체 내부객체에서의 this

```
const obj = {
    func : function() {
        if(obj === this){
            console.log('obj');
        }
    },
    
    objobj : {
        func2 : function(){
            if(obj.objobj === this){
                console.log('objobj');
            }   
        }
    }
}

obj.func();
obj.objobj.func2();
```

```
//obj
//objobj
```

---

### this 는 메소드가 호출된 객체를 가르킨다





### reference

- <https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Operators/this>

- <https://blueshw.github.io/2018/03/12/this/>
- <https://opentutorials.org/course/743/6571>

