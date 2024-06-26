# 함수
* 참조 자료형에 속하며 모든 함수느 Function object

## 참조 자료형
* Objects(Object, Array, Function)
* 객체의 주소가 저장되는 자료형(가변, 주소가 복사)

## 함수 정의
### 함수 구조
* function 키워드
* 함수의 이름
* 함수의 매개변수
* 함수의 body를 구성하는 statements
* return 값이 없다면 undefined를 반환
![함수 구조](../%EC%9D%B4%EB%AF%B8%EC%A7%80/240418/%ED%95%A8%EC%88%98%EA%B5%AC%EC%A1%B0.PNG)

### 함수 정의방법
1. 선언식
![선언식](../%EC%9D%B4%EB%AF%B8%EC%A7%80/240418/%EC%84%A0%EC%96%B8%EC%8B%9D.PNG)
![선언식 예시](<../이미지/240418/선언식 예시.PNG>)
2. 표현식
![표현식](../%EC%9D%B4%EB%AF%B8%EC%A7%80/240418/%ED%91%9C%ED%98%84%EC%8B%9D.PNG)
![표현식 예시](<../이미지/240418/표현식 예시.PNG>)

#### 함수 표현식 특징
* 함수 이름이 없는 '익명 함수'를 사용할 수 있음
* 선언식과 달리 표현식으로 정의한 함수는 호이스팅 되지 않으므로 함수를 정의하기 전에 먼저 사용할 수 없음

![함수 정의 정리](<../이미지/240418/함수 정의 정리.PNG>)

## 매개 변수
1. 기본 함수 매개변수
* 전달하는 인자가 없거나 undefined가 전달될 경우 이름 붙은 매개변수를 기본값으로 초기화

![기본 함수 매개변수](<../이미지/240418/기본 함수 매개변수.PNG>)

2. 나머지 매개변수
* 임의의 수의 인자를 '배열'로 혀용하여 가변 인자를 나타내는 방법
* 작성 규칙
    * 함수 정의 시 나머지 매개 변수는 하나만 작성할 수 있음
    * 나머지 매개변수는 함수 정의에서 매개변수 마지막에 위치해야함

![나머지 매개변수](<../이미지/240418/나머지 매개변수.PNG>) 

### 매개변수와 인자 개수가 불일치 할때
* 매개변수 개수 > 인자개수
    * 누락된 인자는 undefined로 할당
    ![매개변수 > 인자개수](<../이미지/240418/매개변수와 인자개수 불일치.PNG>)
* 매개변수 개수 < 인자개수
    * 초과 입력한 인자는 사용하지 않음
    ![매개변수 < 인자개수](<../이미지/240418/매개변수와 인자개수 불일치2.PNG>)

## Spread syntax(전개 구문)
* '...'
* 배열이나 문자열과 같이 반복 가능한 항목을 펼치는 것(확장, 전개)
    * py의 *과 비슷한 역할
* 전개 대상에 따라 역할이 다름
    * 배열이나 객체의 요소를 개별적인 값으로 분리하거나 다른 배열이나 객체의 요소를 현재 배열이나 객체에 추가하는 등

### 전개 구문 활용처
1. 함수와의 사용
    1. **함수 호출 시** 인자 확장

    ![함수 호출 시 인자 확장](<../이미지/240418/함수 호출 시 인자 확장.PNG>)

    2. 나머지 매개변수 (압축)
    * 함수를 정의할 때 사용하면 압축을 의미
    ![나머지 매개변수 입력 시 압축](<../이미지/240418/나머지 인자 압축.PNG>)

# 화살표 함수
* 함수 표현식의 간결한 표현법
* Python에서 lambda함수와 비슷
![화살표 함수](<../이미지/240418/화살표 함수.PNG>)

## 화살표 함수 작성과정
1. function 키워드 제거 후 매개변수와 중괄호 사이에 화살표(=>) 작성

![화살표 함수 작성1](<../이미지/240418/화살표 함수 작성1.PNG>)
2. 함수의 매개 변수가 하나뿐이라면, 매개변수 '()' 제거 가능(단, 생략하지 않는 것을 권장)

![화살표 함수 작성2](<../이미지/240418/화살표 함수 작성2.PNG>)
3. 함수 본문의 표현식이 한줄이라면, '{}'와 'return'제거 가능

![화살표 함수 작성3](<../이미지/240418/화살표 함수 작성3.PNG>)

## 화살표 함수 심화
* 명시도가 낮기 때문에 권장하지 않음
![화살표 함수 심화](<../이미지/240418/화살표 함수 심화.PNG>)

# 객체
* 키로 구분된 데이터 집합을 저장하는 자료형 != OOP 객체

## 구조 및 속성
### 객체 구조
* 중괄호 '{}'를 이용해 작성
* 중괄호 안에는 key:value 쌍으로 구성된 속성(property)를 여러개 작성 가능
* key는 문자형만 허용
* value는 모든 자료형 허용
![객체 구조](<../이미지/240418/객체 구조.PNG>)

### 속성 참조
* 점('.', chaining operator)또는 대괄호('[]')로 객체 요소 접근
* key 이름에 띄어쓰기 같은 구분자가 있으면 대괄호 접근만 가능
![속성 CR](<../이미지/240418/속성 참조.PNG>)
![속성 UD](<../이미지/240418/속성 참조2.PNG>)
### in 연산자
* 속성이 객체에 존재하는지 여부를 확인
* python에서의 in은 JS에서는 include함수를 활용
![in 연산자](<../이미지/240418/in 연산자.PNG>)

# 객체와 함수
## Method
* 객체 속성에 정의된 함수
### 사용 예시
* object.method() 방식으로 호출
* 메서드는 객체를 '행동'할 수 있게 함
![method 사용예시](../%EC%9D%B4%EB%AF%B8%EC%A7%80/240418/method.PNG)

## this
* this 키워드를 사용해 객체에 대한 특정한 작업을 수행할 수 있음

## 'this' keyword
* 함수나 메서드를 호출한 객체를 가리키는 키워드
* 함수 내에서 객체의 속성 및 메서드에 접근하기 위해 사용

### Method & this 사용예시
![method&this](<../이미지/240418/method & this.PNG>)
* 이 경우에서는 본인을 호출한 객체를 가르킴 == 여기서는 person을 가르킴(person이 greeting을 호출했기 때문)

### JavaScript에서는 this는 함수를 '호출하는 방법'에 따라 가리키는 대상이 다름
|호출 방법|대상|
|---|---|
|단순 호출|전역 객체|
|메서드 호출|메서드를 호출한 객체|

1. 단순 호출시 this
* 가리키는 대상 => 전역 객체
* 브라우저의 전역객체는 window
![단순 호출 this](<../이미지/240418/단순 호출 시 this.PNG>)

2. 메서드 호출 시 this
* 가리키는 대상 => 메서드를 호출한 객체

![메서드 호출 시 this](<../이미지/240418/메서드 호출 시 this.PNG>)

* 중첩된 함수에서의 this 문제점
    * 여기서는 메서드로 호출하느냐 일반호출하느냐로 판단하면됨

    * forEach의 인자로 작성된 함수는 일반적인 함수 호출이기 때문에 this가 전역 객체를 가리킴(window를 가르킴)
![Alt text](<../이미지/240418/중첩된 this.PNG>)
    * 화살표 함수는 자신 만의 this를 가지지 않기 때문에 외부 함수(myFunc)에서의 this 값을 가져옴
    * 화살표함수는 간결함만을 위한 표기법이 아니라 외부함수의 this를 가져올 수 있는 역할을 해줌
![Alt text](<../이미지/240418/중첩된 this 해결.PNG>)

### JavaScript의 'this'
* JavaScript의 함수는 호출될 때 this를 암묵적으로 전달 받음
* JavaScript에서 this는 함수가 '호출되는 방식'에 따라 결정 되는 현재 객체를 나타냄
* Python의 self와 Java의 this가 선언 시 이미 값이 정해지는 것에 비해 JavaScript의 this는 함수가 호출되기 전까지 값이 할당되지 않고 호출 시에 결정됨(동적 할당)

* this가 미리 정해지지 않고 호출 방식에 의해 결정되는 것은 장단점이 있음
    * 장점 : 함수(메서드)를 하나만 만들어 여러 객체에서 재사용할 수 있다는 것
    * 단점 : 이런 유연함이 실수로 이어질 수 있다는 것
* 개발자는 this의 동작 방식을 충분히 이해하고 장점을 취하면서 실수를 피하는 데에 집중

## 추가 객체 문법
1. 단축 속성
* 키 이름과 값으로 쓰이는 변수의 이름이 같은 경우 단축 구문을 사용할 수 있음
![단축 속성](<../이미지/240418/단축 속성.PNG>)
2. 단축 메서드
* 메서드 선언시 function 키워드 생략 가능
![단축 메서드](<../이미지/240418/단축 메서드.PNG>)
3. 계산된 속성(computed property name)
* 키가 대괄호([])로 둘러싸여 있는 속성
* 고정된 값이 아닌 변수 값을 사용할 수 있음
![계산된 속성](<../이미지/240418/계산된 속성.PNG>)

4. 구조 분해 할당(destructiong assignment)
* 배열 또는 객체를 분해하여 객체 속성을 변수에 쉽게 할당할 수 있는 문법
    * 한번에 여러개의 변수에 할당 가능
![구조 분해 할당](<../이미지/240418/구조 분해 할당.PNG>)
* '함수의 매개변수'로 객체구조 분해 할당 활용 가능
![구조분해할당 활용](../%EC%9D%B4%EB%AF%B8%EC%A7%80/240418/%EA%B5%AC%EC%A1%B0%EB%B6%84%ED%95%B4%ED%95%A0%EB%8B%B9%ED%99%9C%EC%9A%A9.PNG)

5. Object with '전개 구문'
* 객체 복사 : 객체 내부에서 객체 전개
* 얕은 복사에 활용 가능
![object with 전개 구문](<../이미지/240418/object with 전개 구문.PNG>)

6. 유용한 객체 메서드
* Object.keys()
* Object.values()
![유용한 객체 메서드](<../이미지/240418/유용한 객체 메서드.PNG>)

7. Optional chaining('?.')
* 속성이 없는 중첩 객체를 에러 없이 접근할 수 있는 방법
* 만약 참조 대상이 null 또는 undefined라면 에러가 발생하는 것 대신 평가를 멈추고 undefined를 반환
![optional chaining](<../이미지/240418/optional chaining.PNG>)
* 만약 Optional chaining을 사용하지 않는다면 다음과 같이 '&&' 연산자를 사용해야 함
![Alt text](<../이미지/240418/optional chaining2.PNG>)

* Optional chaining 장점
    * 참조가 누락될 가능성이 있는 경우 연결된 속성으로 접근할 때 더 짧고 간단한 표현식을 작성할 수 있음
    * 어떤 속성이 필요한지에 대한보증이 확실하지 않는 경우에 객체의 내용을 보다 편리하게 탐색할 수 있음

* Optional chaining 주의 사항
    1. Optional chaining은 존재하지 않아도 괜찮은 대상에만 사용해야 함(남용X)
        - 왼쪽 평가대상이 없어도 괜찮은 경우에만 선택적으로 사용
        - 중첩 객체를 에러 없이 접근하는 것이 사용 목적이기 때문
![optional chaining 주의사항1](<../이미지/240418/optional chaining 주의사항.PNG>)
    2. Optional Chaining 앞의 변수는 반드시 선언되어 있어야 함
![optional chaining 주의사항2](<../이미지/240418/optional chaining 주의사항2.PNG>)

* Optional chaining 정리
1. obj?.prop
    * obj가 존재하면 obj.prop을 반환하고, 그렇지 않으면 undefined를 반환
2. obj?.[prop]
    * obj가 존재하면 obj[prop]을 반환하고, 그렇지 않으면 undefined를 반환
3. obj?.method()
    - obj가 존재하면 obj.method()를 호출하고, 그렇지 않으면 undefined를 반환

# JSON
* JavaScript Object Notation
* Key-Value형태로 이루어진 자료 표기법
* JavaScript의 Object와 유사한 구조를 가지고 있지만 JSON은 형식이 있는 '문자열'
* JavaScript에서 JSON을 사용하기 위해서는 Object 자료형으로 변경해야함

* object를 JSON으로 변환

![object를 JSON으로 변환](<../이미지/240418/object를 JSON으로 변환.PNG>)

# new 연산자
* JS에서 객체를 생성하려면 하나의 객체를 선언하고 생성하고
* 동일한 형태의 객체를 또 만들기 위해서 또 다른 객체를 선언하여 생성해야 함
![new필요예시](<../이미지/240418/new 1.PNG>)

* new를 활용하면 같은 형태의 객체를 여러 개 생성 가능
![new활용](<../이미지/240418/new 연산자 예시.PNG>)

![new 연산자](<../이미지/240418/new 객체.PNG>)
* 사용자 정의 객체 타입을 생성
* 매개변수
    * constructor : 객체 인스턴스의 타입을 기술(명세)하는 함수
    * arguments : constructor와 함께 호출될 값 목록

# 배열(Array)
* 순서가 있는 데이터 집합을 저장하는 자료 구조
## 배열 구조
* 대괄호'[]'를 이용해 작성
* 요소 자료형 : 제약 없음
* length 속성을 사용해 배열에 담긴 요소가 몇개 인지 알 수 있음
![배열 구조](<../이미지/240418/배열 구조.PNG>)

## 배열 메서드
* 주요 메서드
|메서드|역할|
|---|---|
|push/pop|배열 끝 요소를 추가/제거|
|unshift/shift|배열 앞 요소를 추가/제거|
### push()
* 배열 끝에 요소를 추가
![push](../%EC%9D%B4%EB%AF%B8%EC%A7%80/240418/push.PNG)

### pop()
* 배열 끝 요소를 제거하고, 제거한 요소를 반환
![pop](../%EC%9D%B4%EB%AF%B8%EC%A7%80/240418/pop.PNG)

### unshift()
* 배열 앞에 요소를 추가
![unshift](../%EC%9D%B4%EB%AF%B8%EC%A7%80/240418/unshift.PNG)
### shift()
* 배열 앞 요소를 제거하고, 제거한 요소를 반환
![shift](../%EC%9D%B4%EB%AF%B8%EC%A7%80/240418/shift.PNG)

## Array helper method
* 배열 조작을 보다 쉽게 수행할 수 있는 특별한 메서드 모음
* ES6에 도입
* 배열의 각 요소를 순회하며 각 요소에 대해 함수(콜백함수)를 호출
    - forEach(), map(), filter(), every(), some(), reduce()등
    - 메서드 호출 시 인자로 함수(콜백함수)를 받는 것이 특징

### 콜백 함수(Callback function)
* 다른 함수에 인자로 전달되는 함수
* 외부 함수 내에서 호출되어 일종의 루틴이나 특정 작업을 진행
* 함수 밖으로 빼서도 작성 가능
![콜백 함수](<../이미지/240418/callback function.PNG>)

### 주요 Array Helper Methods
|메서드|역할|
|---|---|
|forEach|배열 내의 모든 요소 각각에 대해 함수(콜백함수)를 호출, 반환값 없음|
|map|배열 내의 모든 요소 각각에 대해 함수(콜백함수)를 호출, 함수 호출 결과를 모아 새로운 배열을 반환|

#### forEach()
* 배열의 각 요소를 반복하며 모든 요소에 대해 콜백함수를 호출
##### forEach의 구조
![forEach callback](<../이미지/240418/forEach 구조 callback.PNG>)

* 콜백함수는 3가지 매개변수로 구성
1. item: 처리할 배열의 요소
2. index : 처리할 배열 요소의 인덱스(선택인자)
3. array : forEach를 호출한 배열(선택인자)
* 반환값 : undefined
![forEach 구조](<../이미지/240418/forEach 구조.PNG>)
##### forEach의 예시
![forEach예시](<../이미지/240418/forEach 예시.PNG>)

* 출력 결과
```
Alice
Bella
Cathy

Alice
Bella
Cathy
```

##### forEach 활용
![forEach 활용](<../이미지/240418/forEach 활용.PNG>)
```
Alice / 0 / Alice, Bella, Cathy
Bella / 1 / Alice, Bella, Cathy
Cathy / 2 / Alice, Bella, Cathy
```

#### map()
* 배열의 모든 요소에 대해 콜백함수를 호출하고, 반환된 호출 결과 값을 모아 새로운 배열을 반환

##### map 구조
![map callback](<../이미지/240418/map callback.PNG>)
* forEach의 매개변수와 동일
* 반환 값
    - 배열의 각 요소에 대해 실행한 'callback의 결과를 모은 새로운 배열'
    * forEach 동작 원리와 같지만 forEach와 달리 새로운 배열을 반환함
![map 구조](<../이미지/240418/map 구조 예시.PNG>)

##### map 예시
* 배열을 순회하며 각 객체의 name 속성 값을 추출하기(for...of와 비교)

![map 활용](<../이미지/240418/map 활용.PNG>)
![map 활용2](<../이미지/240418/map 활용2.PNG>)

##### python에서의 map함수와 비교
* python의 map에 square 함수를 인자로 넘겨 numbers 배열의 각요소를 square함수 인자로 사용
![python map](<../이미지/240418/python map.PNG>)

* map 메서드에 callBackFunc 함수를 인자로 넘겨 numbers 배열의 각 요소를 callBackFunc함수의 인자로 사용
![JS map](<../이미지/240418/JS map.PNG>)

## 배열 순회 종합
![배열 순회 종합](<../이미지/240418/배열 순회 종합.PNG>)

|방식|특징|
|---|---|
|for loop|배열의 인덱스를 이용하여 각 요소에 접근, break, continue사용가능|
|for...of|배열 요소에 바로 접근 가능,break, continue사용가능|
|forEach|간결하고 가독성이 높음, callback함수를 이용하여 각 요소를 조작하기 용이,
break, continue 불가능|

## 기타 Array Helper Method
|메서드|역할|
|---|---|
|filter|콜백 함수의 반환 값이 참인 요소들만 모아서 새로운 배열을 반환|
|find|콜백 함수의 반환 값이 참이면 해당 요소를 반환|
|some|배열의 요소 중 적어도 하나라도 콜백 함수를 통과하면 true를 반환하며 즉시 배열 순회 중지, 반면에 모두 통과하지 못하면 false를 반환|
|every|배열의 모든 요소가 콜백 함수를 통과하면 true를 반환, 반면에 하나라도 통과하지 못하면 즉시 false를 반환하고 배열 순회 중지|

## 추가 배열 문법
* Array with '전개 구문'
    * 배열복사

![배열복사](../%EC%9D%B4%EB%AF%B8%EC%A7%80/240418/%EB%B0%B0%EC%97%B4%EB%B3%B5%EC%82%AC.PNG)

# 참고
## 콜백 함수 구조를 사용하는 이유
1. 함수의 재사용성 측면
* 함수를 호출하는 코드에서 콜백 함수의 동작을 자유롭게 변경할 수 있음
* 예를 들어, map 함수는 콜백함수를 인자로 받아 배열의 각 요소를 순회하며 콜백 함수를 실행
* 이 때, 콜백 함수는 각 요소를 변환하는 로직을 담당하므로, map함수를 호출하는 코드는 간결하고 가독성이 높아짐

2. 비동기적 처리 측면
* setTimeout 함수는 콜백 함수를 인자로 받아 일정 시간이 지난 후에 실행됨
* 이 때, setTimeout 함수는 비동기적으로 콜백 함수르 실행하므로, 다른 코드의 실행을 방해하지 않음
![비동기적 측면](<../이미지/240418/비동기적 측면.PNG>)
```
a
c
b
```

## forEach에서 break하는 대안
* forEach에서는 break 키워드를 사용할 수 없음
* 대신 some과 every의 특징을 활용해 마치 break를 사용하는 것처럼 활용할 수 있음
![forEach break 대안](<../이미지/240418/forEach에서의 break.PNG>)

* some을 활용한 예시
    - 콜백 함수가 true를 반환하면 즉시 순회를 중단하는 특징을 활용

![some을 이용한 forEach break](<../이미지/240418/some을 이용한 forEach break.PNG>)

* every를 활용한 예시
    - 콜백 함수가 false를 반환하면 즉시 순회를 중단하는 특징을 활용

![every 활용 forEach break](<../이미지/240418/every 활용 forEach break.PNG>)

## 배열은 객체다
* 배열도 키와 속성들을 담고 있는 참조 타입의 객체
* 배열의 요소를 대괄호 접근법을 사용해 접근하는 건 객체 문법과 같음
    - 배열의 키는 숫자
* 숫자형 키를 사용함으로써 배열은 객체 기본 기능 이에외도 '순서가 있는 컬렉션'을 제어하게 해주는 특별한 메서드를 제공하는 것
* 배열은 인덱스를 키로 가지며 length 속성을 갖는 특수한 객체
![배열은 객체다](<../이미지/240418/배열은 객체다.PNG>)