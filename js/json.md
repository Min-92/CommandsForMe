# JSON (JavaScript Object Notation)

Javascript 객체 문법으로 구조화된 데이터를 표현하기 위한 문자 기반의 표준 포맷

json엔  되도록 주석을 사용하지 않는 것이 좋다


- #### Parsing(파싱) 
  - 문자열(JSON) -> 객체(Object) 

- #### Stringification(문자열화)

  - 객체(Object) -> 문자열(JSON)



### JSON.stringfy()

javaScript 값이나 객체를 json 문자열로 변환한다.

```javascript
JSON.stringify(value[, replacer[, space]])
```

- value 
  - JSON 문자열로 변환 할 값
- replacer (optional)
  - JSON 문자열에 포함 될 값 객체의 속성들을 선택하기 위해 사용되는 배열
- space (optional)
  - 가독성을 목적으로 공백을 삽입하는데 사용되는 string or number



###### replacer

```javascript
function replacer(key, value) {
  if (typeof value === "string") {
    return undefined;
  }
  return value;
}

var foo = {foundation: "Mozilla", model: "box", week: 45, transport: "car", min : {name : "Min"}, month: 7};
var jsonString = JSON.stringify(foo, replacer);
//{"week":45,"min" : {}, month":7}
```

replacer 탐색 순서 (BFS)

|    key     |      value      |
| :--------: | :-------------: |
|    " "     | object  === foo |
| foundation |    "Mozilla"    |
|   model    |      "box"      |
|    week    |       45        |
| transprot  |      "car"      |
|    min     |    object{}     |
|    name    |      "Min"      |
|   month    |        7        |

따라서 맨처음 object 가 return 이 되지 않으면 내부 속성을 탐색 하지 않는다.  

배열

```javascript
JSON.stringify(foo, ['week', 'month']);  
// '{"week":45,"month":7}' key 값만 대응
```



### JSON.parse()

JSON 의 문자열의 구문을 분석하고 JavaScript값이나 객체를 생성

reviver 함수를 인수로 전달 할 경우 결과를 반환하기 전에 변형 가능

```javascript
JSON.parse(text[, reviver])
```

- text
  - JSON에서 변환할 문자열
- reviver (optional)
  - 함수라면, 변환 결과를 반환하기 전에 이 인수에 전달해서 변형

###### reviver 

```javascript
const reviver = (key, value) => {
    // console.log(key, value);
    if (typeof value === 'number') {
        return undefined;
    }
    return value;
}

const parse2 = JSON.parse('{"1": 1, "2": "b", "3": {"4": "d", "5": {"6": 6}}}',reviver);
// { '2': 'b', '3': { '4': 'd', '5': {} } }
```

reviver 탐색 순서 (DFS)

| key  |                 value                 |
| :--: | :-----------------------------------: |
|  1   |                   1                   |
|  2   |                   b                   |
|  4   |                   d                   |
|  6   |                   6                   |
|  5   |                {6: 6}                 |
|  3   |           {4: 4, 5: {6: 6}}           |
| " "  | {1 : 1, 2 : 2, 3: { 4: 4, 5: {6: 6}}} |





### reference

- <https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/JSON/stringify>
- <https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/JSON/parse>