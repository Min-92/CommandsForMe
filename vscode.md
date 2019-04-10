# vscode-nodejs debugging

- 공식 홈페이지 디버깅 방법 공부해보기

## 디버그 단축키

- Ctrl + Shift + D : 디버그 view 열기
- F5 : 디버그 시작
- Ctrl + F5 : 디버깅 없이 디버그(run)
- F5 : continue/pause
- F10 : Step Over
- F11 : Step Into
- shift + F11 : Step Out
- shilft+F5 : Stop

### Step over, into, out

1. Step Over
   - 해당 함수 내에서 한줄씩 실행
2. Step Into
   - 한줄씩 실행
   - 호출되는 함수가 있으면 호출되는 함수로 이동
3. Step Out
   - 현재 함수를 실행하고 호출 전 함수로 이동

## Break point

- F9로 브레이크 포인트 추가
- 빨간 점 : 브레이크포인트
- 회색 점 : 사용안하는 브레이크 포인트

## Advanced breakpoint

### 조건부 breakpoint = Conditional breakpoint

1. Expression condition
   - 조건 설정이 가능
   - true 인 경우 동작
2. Hit count
   - 정해준 숫자만큼 포인트에 도달 후에 동작
   - ex) 10 -> 10번 도달 다음부터 멈춤 (11번째)

### Inline breakpoint

- 코드 내부에 포인트 지정 가능
- Shift + F9

### Function breakpoint

- 함수 이름을 알고있는경우 해당 함수를 breakpoint 로 지정

## Log point

- 중단되지 않고 대신에 콘솔에 메세지를 기록하는 중단점
- 서버같이 중지할수 없는 디버깅떄 유용
- {} 를 이용해서 표현가능
- 빨간 다이아몬드모양 아이콘

## 데이터 확인하기

- 디버그 view - 변수에서 데이터 값 확인 가능
- 소스에 마우스 올려도 확인 가능

## 조사식 Watch section

- 직접 확인하고 싶은 변수를 설정, 확인 가능
- 표현식도 사용 가능 // i*3
- *주의사항* i = i*3 이런식으로 작성하면 코드에 반영됨

## Call stack

- 함수의 호출 흐름을 볼 수 있다
- 규모가 큰프로그램에서 큰 효과
- 실행 중인 함수만 스택에서 확인가능
- 함수가 종료되면 스택에서 빠져나감