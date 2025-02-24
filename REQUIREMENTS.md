## 📌 요구사항

- [ ] 2개의 숫자에 대해 덧셈이 가능하다.
- [ ] 2개의 숫자에 대해 뺄셈이 가능하다.
- [ ] 2개의 숫자에 대해 곱셈이 가능하다.
- [ ] 2개의 숫자에 대해 나눗셈이 가능하다.
- [ ] AC(All Clear)버튼을 누르면 0으로 초기화 한다.
- [ ] 숫자는 한번에 최대 3자리 수까지 입력 가능하다.
- [ ] 계산 결과를 표현할 때 소수점 이하는 버림한다.
- [ ] 연산의 결과값이 `Infinity`일 경우 `오류`라는 문자열을 보여준다. (아이폰 참고)


## 📄 구현 방향성

### 계산기 기능 커스텀 훅 구현

계산기의 핵심 기능인 연산기능을 수행하는 커스텀 훅을 구현한다.
해당 커스텀 훅은 display 값, 연산자 등록, 숫자 입력, 계산 수행, 초기화 함수를 반환하여 컴포넌트에서 사용가능하도록 구현한다.

1. 숫자 입력

   인자로 string을 전달 받은 후 내부 연산식 state에 전달받은 string을 합쳐서 업데이트한다.

- [x] 초기 상태에서 숫자 입력 함수를 실행하면 0에서 해당 숫자로 수정된다.
- [x] 3자리보다 많은 숫자를 입력하면 "숫자는 3자리까지만 입력 가능합니다." 라는 alert가 발생한다.
- [ ] 연산자 입력 후 3자리보다 많은 숫자를 입력하면 "숫자는 3자리까지만 입력 가능합니다." 라는 alert가 발생한다.
- [x] 연산자가 입력 되었을때 숫자를 입력하면 display에 해당 숫자가 추가된다.
- [ ] 연산식의 상태가 Infinity , -Infinity 또는 NaN 일때 숫자를 입력하면 display에 오류 메세지가 없어지고 클릭한 숫자가 표시된다.


2. 연산자 입력

   인자로 string을 전달 받은 후 내부 연산식 state에 해당 string을 업데이트한다.

- [ ] 마지막 입력이 숫자인 경우 연산자를 클릭하면 display에 표시된 연산자가 추가된다.
- [ ] 입력 가능한 연산자가 이미 입력되어 있을때 연산자를 클릭하면 마지막으로 입력한 연산자가 수정된다.


3. 연산 실행 함수
   
   내부 연산식 state를 계산하여 연산식 state를 업데이트 한다.

- [ ] "=" 버튼을 클릭하면 연산식을 계산하여 display에 결과값이 표시된다.
- [ ] 연산자가 없이 숫자만 입력되어 있을 때 "=" 버튼을 클릭하면 숫자가 유지된다.
- [ ] Infinity, NaN 의 결과값을 display에 표시한다.
- [ ] 마지막 입력값이 연산자인 경우 "=" 버튼을 클릭하면 "숫자를 입력해주세요." 라는 alert가 발생한다.

4. 초기화 함수

- [ ] "AC" 버튼을 클릭하면 display에 0이 표시된다.(연산식 state가 초기화 된다.)


### 연산식 표현 컴포넌트 구현

계산기 기능 커스텀 훅의 연산식 state를 전달받아 화면에 표시한다.

### 계산기 action 버튼 구현

각 역할에 맞게 onClick Event에 계산기 기능 커스텀 훅의 함수를 연결한다.