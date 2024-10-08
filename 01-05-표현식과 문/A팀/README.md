# 05장 표현식과 문

### 1. 값

> 값(value)은 표현식(expression)이 평가(evaluate)되어 생성된 결과를 말한다.

- 모든 값은 데이터 타입을 가지며 메모리에 2진수(bit의 나열)로 저장된다.
- 메모리에 저장된 값은 데이터 타입에 따라 다르게 해석될 수 있다. (ex. 메모리 저장값 0100 0001 === number: 65 === string: 'A')

### 2. 리터럴

> 리터럴(literal)은 사람이 이해할 수 있는 문자 또는 약속된 기호를 사용해 값을 생성하는 표기법을 말한다.

- 자바스크립트 엔진은 코드가 실행되는 시점인 런타임에 리터럴을 평가해 값을 생성한다.

### 3. 표현식

> 표현식(expression)은 값으로 평가될 수 있는 문(statement)이다. 즉, 표현식이 평가되면 새로운 값을 생성하거나 기존 값을 참조한다.

- 앞에서 살펴본 리터럴은 값으로 평가된다. 따라서 리터럴도 표현식이다.

```js
var score = 100;
```

위 문장에서 100은 리터럴이다. 리터럴 100은 자바스크립트 엔진에 의해 평가되어 값을 생성하므로 리터럴은 그 자체로 표현식이다.

```js
var score = 50 + 50;
```

50 + 50은 리터럴과 연산자로 이루어져 있다. 하지만 식이 평가되어 숫자 값 100을 생성하므로 표현식이다.

```js
score; // 100
```

변수 식별자를 참조해보면 변수에 할당된 값으로 평가된다. 식별자 참조는 값을 생성하지는 않지만 값으로 평가되므로 표현식이다.

> 값으로 평가될 수 있는 문은 모두 표현식이다.

### 4. 문

앞으로 자바스크립트의 설명에서 "문(statement)"과 "표현식(expression)"이라는 용어가 자주 등장할 것이다. 문과 표현식을 구별하고 해석할 수 있다면 자바스크립트 엔진의 입장에서 코드를 읽을 수 있고 실행 결과를 예측하는 데 도움이 된다.

- 문(statement)은 프로그램을 구성하는 기본 단위이자 최소 실행 단위다.
- 문의 집합으로 이루어진 것이 프로그램이며, 문을 작성하고 순서에 맞게 나열하는 것이 프로그래밍이다.
- 문은 여러 토큰으로 구성된다.
- 키워드, 식별자, 연산자, 리터럴, 세미콜론(;)이나 마침표(.) 등의 특수 기호는 문법적인 의미를 가진다.
- 토큰(token)이란 문법적인 의미를 가지며, 문법적으로 나눌 수 없는 코드의 기본 요소를 의미한다.
- 문을 명령문이라고도 부른다. 문이 실행되면 명령이 실행되고 무슨일인가가 일어나게 된다.
- 문은 선언문, 할당문, 조건문, 반복문 등으로 구분할 수 있다.

### 5. 세미콜론과 세미콜론 자동 삽입 기능

- 세미콜론(;)은 문의 종료를 나타낸다.
- 자바스크립트 엔진은 세미콜론으로 문이 종료한 위치를 파악하고 순차적으로 하나씩 문을 실행한다.
  - 단, 0개 이상의 문을 중괄호로 묶은 코드 블록({ ... }) 뒤에는 세미콜론을 붙이지 않는다. (ex. if문, for문, 함수 등)
  - 이러한 코드 블록은 언제나 문의 종료를 의미하는 자체 종결성을 갖는다.
- 세미콜론은 옵션이다. 생략하면 자바스크립트 엔진이 알잘딱 붙혀준다.

### 6. 표현식인 문과 표현식이 아닌 문

> 표현식은 문의 일부일 수도 있고 그 자체로 문이 될 수도 있다.

- 표현식인 문과 표현식이 아닌 문을 구별하는 가낭 간단하고 명료한 방법은 변수에 할당해 보는 것이다.
- 표현식인 문은 값으로 평가되므로 변수에 할당할 수 있다.
- 하지만 표현식이 아닌 문은 값으로 평가할 수 없으므로 변수에 할당하면 에러가 발생한다.

> ##### 완료 값
>
> 표현식이 아닌 문을 실행하면 언제나 undefined를 출력한다. 이를 완료 값이라고 한다.
> 완료값은 표현식의 평가 결과가 아니다. 따라서 다른 값과 같이 변수에 할당할 수 없고 참조할 수도 없다.
