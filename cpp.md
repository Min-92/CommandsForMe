# C++ commands

## #include
- include문은 '#include Directive"라고 한다.
- 이후에 올 파일을 포함하라는 의미
- '#' = 전처리 명령
~~~
#include <iostream> // input output stream
~~~

## <iostream>
- input/output stream
- cin, cout, cerr, clog 등을 포함
~~~
#include <iostream> 
// cin, cout, cerr, clog 등을 포함
~~~

## using namespace std
- 표준 네임스페이스 사용
~~~
using namespace std;
~~~

## cin cout
- 입력받기
- 출력하기
~~~
#include <iostream> 
int main(){
    using namespace std;
    int a

    cin >> a; //a에 입력받은 값을 저장
    cout << a; 
    return 0;
}
~~~

## 반복문
### for
~~~
for(int i =0; i < N; i++){
    a++;
}
~~~

## min, max
- 최소값, 최대값
~~~
min(1,2) // 1
max(1,2) // 2
~~~



## 함수

##### 선언

~~~
int functionName(int n, int k){
    
    return 0;
}
~~~



## 벡터

##### 선언

~~~
vector<int> name();
vector<int> name(n);
vector<int> name(n,x);
vector<int> name(b,e); //반복자 구간 b,e 로 초기화된 원소 가짐


~~~

###### 크기

~~~
v.size();
~~~

###### 반복자

~~~
b = v.begin();
e = v.begin();
~~~



## 형변환

~~~
string str = to_string(n); // int to string
int number = atoi()
~~~

