# Variables(변수)
![Alt text](<웹 1920 – 1-1.png>)
정의
- 하나의 값을 저장하기 위해 확보한 메모리 공간 자체 또는 그메모리 공간을 
	식별하기 위해 붙인 이름.
- 값의 위치를 가르키는 상징적인 이름.

### 컴퓨터 구조와 연관하여 변수 이해하기 


![Alt text](<Web 1920 – 1.png>)

- 컴퓨터는 CPU를 사용해 연산하고, 메모리를 사용해 데이터를 기억.
- 컴퓨터는 모든 데이터(메모리에 저장되는 데이터는 데이터 종류와 상관없이)를 2진수로 처리. 
	
- 메모리
	- 데이터를 저장할 수 있는 메모리 셀의 집합체.
	
- 메모리 셀 
	- 하나의 크기는 1바이트(8비트).
	- 1바이트 단위로 데이터를 저장하거나 읽어들임.
	- 고유의 메모리 주소를 갖음.

- 메모리 주소
	- 메모리 공간의 위치를 나타내며, 0부터 시작하여 메모리 크기만큼 메모리 크기만큼 주소를 갖음.

아래와 같은 코드가 있다.
```js
10 + 20
```
각각 메모리 셀에 저장되어 있고 그걸 CPU를 통해 연산한 30라는 값을 다시 메모리 셀에 저장할텐데 어떻게 30이라는 값을 갖고 올수 있을까? 
메모리 주소로 직접 접근할 경우 치명적인 오류(운영체제 값을 건드려 시스템 멈추는 오류)나 제어를 한다해도 값이 저장될 메모리 주소는 코드가 실행될때 임의로 결정되어 동일한 코드를 실행 한다 하더라도 실행 될때마다 값이 저장될 메모리 주소가 변경된다. 

프로그래밍 언어는 기억하고 싶은 값을 메모리에 저장하고 저장된 값을 읽어 들여
`변수`라는 매커니즘을 이용한다.

### 요약 
변수를 통해서 값이 저장된 메모리 공간 주소를 변경해 값에 접근한다.

```js
let result = 10 + 20
console.log(result) // 30
```
위와 같은 코드처럼 result라는 변수를 통해 30이라는 값에 접근한다.

### 변수명

#### 정의
- 메모리 공간에 저장된 값을 식별할 수 있는 고유한 이름(코드에서는 result).

### 변수값

#### 정의
- 변수에 저장된 값(코드에서 콘솔로그에 찍힌 값 30).

### 할당 (assignment)

#### 정의 
- 변수애 값을 저장하는 것(저장, 대입). 

#### 값을 할당방법 

```js
let firstName // 변수 선언 
firstName = 'seon-mi' // 값의 할당
```

'**=** 할당 연산자를 이용하여 우변의 값을 좌변에는 변수를 할당
#### 실행 시점
- 런타임에 실행됨( = 소스코드가 순차적으로 실행되는 시점)
### 참조(reference)

#### 정의
- 변수에 저장된 값을 읽어들이는 것.

### 식별자 

#### 정의
- 변수 이름을 식별자라고 함(메모리 주소를 기억함).
- 어떤 값을 구별해서 식별할 수 있는 고유한 이름(변수, 함수, 클래스).

#### 식별자의 존재를 알리는 방법
- 선언에 의해 식별자 존재를 알림.

### 변수 선언
#### 정의
- 변수를 생성하는 것.
- 값을 저장하기 위한 메모리 공간을 확보하고 변수 이름과 메모리 공간의 주소를 연결해서 값을 저장할 수 있게 준비하는 것 

`변수를 사용하려면 반드시 선언이 필요`
#### 실행시점
- 런타임 이전에 먼저 실행
#### 선언방법
- 변수 선언 키워드인 **var**(사용 지양), **let**, **const** 사용하여 선언. 

#### 자바스크립트 엔진은 변수 선언 수행 2단계
- 선언 단계: 변수 이름을 등록해 자바스크립트 엔진에 변수의 존재를 알림.
- 초기화 단계: 값을 저장하기 위한 메모리 공간을 확보하고 암묵적으로 undefined를 할당해 초기화 한다. 

### 초기화
#### 정의
- 변수가 선언된 이후 최초로 값을 할당하는 것
- 변수는 undefined로 암묵적인 초기화가 자동 수행(var)

### ReferenceError(참조 에러)

- 선언하지 않은 식별자에 접근할 경우 참조에러 발생.

### 변수 선언 실행 시점
```js
console.log(name) // undefined
var name
```
변수 선언이 소스코드가 한 줄씩 순차적으로 실행되는 시점(런타임)이 아니라 그 이전 단계에서 먼저 실행.

### 변수 호이스팅
#### 정의
- 변수 선언 실행 시점에 따라 변수 선언문이 코드의 선두로 끌어 올려진 것처럼 동작하는 자바스크립트의 고유 특징. (키워드를 사용해서 선언하는 모든 식별자는 호이스팅이된다.)

## **var** Vs **let** Vs **const**

|선언특징/키워드|var|let|const|
|-----|-----|-----|---------|
|선언|O|O|X|
|재할당|O|O|X|
|선언시 할당|O|O|O|

이 표처럼 `const` 단한번만 할당 할수 있는 변수키워드다 변하지 않은 변수를 `상수` 라고 한다.