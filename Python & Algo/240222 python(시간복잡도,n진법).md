# SW 문제해결 역량
* 프로그램을 하기위한 많은 제약 조건과 요구사항을 이해하고 최선의 방법을 찾아내는 능력
* 프로그래머가 사용하는 언어나 라이브러리, 자료구조, 알고리즘에 대한 지식을 적재적소에 퍼즐을 배치하듯 이들을 연결하여 큰 그림을 만드는 능력
## 문제해결과정
1) 문제를 읽고 이해 (주석이나 메모로 표기, 자신이 다루는 data가 어떤 데이터인지 확인)
2) 문제를 익수한 용어로 재정의
3) 어떻게 해결할지 계획
4) 계획 검증
5) 구현
6) 디버깅을 통해 개선방법 도출 및 해결


# 복잡도 분석
* 알고리즘 : 유한한 단계를 통해 문제를 해결하기 위한 절차나 방법, 주로 컴퓨터 용어로 쓰이며, 컴퓨터가 어떤일을 수행하기 위한 단계적 방법
## 알고리즘의 효율
* 공간적 효율성과 시간적 효율성
- 공간적 효율성은 연산량 대비 얼마나 적은 메모리 공간을 요하는 가를 의미
- 시간적 효율성은 연산량 대비 얼마나 적은 시간을 요하는 가를 의미(반복문을 얼마나 많이 썼는가)
- 효율성을 뒤집어 표현하면 복잡도(Complexity)가 됨. 복잡도가 높을수록 효율성은 저하된다.

* 리스트 컴프리헨션을 사용시 for문을 사용해서 리스트를 형성하는 것보다 2배 정도 빠름


* 10억개의 숫자를 정렬시 O(n\*\*2)은 300여년 걸리지만, O(nlogn)은 5분 걸리므로 효율적인 알고리즘이 필요하다

* 표기법
    - O(Big-Oh) 표기 = 최악의 경우
    - Ω(Big-Omega) 표기 = 최선의 경우
    - Θ(Big-Theta) 표기 = 평균

* 알고리즘은 최악의 경우를 고려해서 짜는게 좋음

### O(Big-Oh) 표기
* O-표기는 복잡도의 점근적 상한을 나타냄
* 복잡도가 f(n)=2n\*\*2+7\*n+4이라면, f(n)의 O-표기는 O(n**2)
* 단수화된 함수 n\*\*2에 임의의 상수 c를 곱한 cn\*\*2이 n이 증가함에 따라 f(n)의 상한이 됨

![bigO](../%EC%9D%B4%EB%AF%B8%EC%A7%80/240222/bigO.PNG)

* n이 증가함에 따라 O(g(n))이 점근적 상한(g(n)이 n0보다 큰 모든 n에 대해서 항상 f(n)보다 크다)

![bigO2](../%EC%9D%B4%EB%AF%B8%EC%A7%80/240222/bigO2.PNG)

* 상수를 강조하고 싶을 때, O(5N)이런식의 표기도 가능함

#### 자주 사용하는 O 표기
|O표기|설명|예시|
|---|---|---|
|O(1)|상수 시간(Constant Time)|popleft()|
|O(logn)|로그(대수) 시간(Logarithmic Time)|이진탐색|
|O(n)|선형 시간(Linear Time)|pop(0)|
|O(nlogn)|로그 선형 시간(Log-linear Time)|sort|
|O(n**2)|제곱 시간(Quadratic Time)|
|O(n**3)|세제곱 시간(Cubic Time)|

* 알고리즘의 시간복잡도에서 log의 밑은 2
* O(logN)은 O(1)보다 느리지만 유사한 성능을 보이고, O(NlogN)은 O(N)보다는 느리지만 유사함

* pop(0)은 O(N) : 0번의 index를 제거하고 모두의 index를 한칸씩 땡겨와야하기 때문에 오래걸림
* popleft()는 : O(1)

### Ω(Big-Omega) 표기
* 복잡도의 점근적 하한을 의미
* f(n)=2n\*\*2+7\*n+4이라면, n이 증가함에 따라 2*n\*\*2-7*n+4가 cn**2보다 작을수 없다 라는 의미
* O-표기와 마찬가지로, Ω표기도 복잡도 다항식의 최고차항만 계수없이 취하면 됨
* 최소한 이만큼의 시간이 걸린다는 걸 나타냄

### Θ(Big-Theta) 표기
* O표기와 Ω표기가 같은 경우에 사용
* 복잡도가 f(n)=2n\*\*2+8\*n+3 = O(n\*\*2)=Ω(n\*\*2)이므로, f(n)=Θ(n**2)
* f(n)이 증가함에 따라 n\*\*2과 동일한 증가율을 가진다라는 의미
![bigtheta](../%EC%9D%B4%EB%AF%B8%EC%A7%80/240222/bigtheta.PNG)




# 표준 입출력
* Python3의 표준 입출력
    * 입력
    - Raw 값의 입력 : input()
        * 받은 입력값을 문자열로 취급
    - Evaluated된 값 입력 : eval(input())
        * 받은 입력 값을 평가된 데이터 형으로 취급
    * 출력
    - print()
        * 표준 출력 함수.출력값의 마지막에 개행 문자 포함
    - print('text',end='')
        * 출력시 마지막에 개행문자 제외할 시
    - print('%d'%number)
        * Formatting 된 출력

```py
import sys
sys.stdin = open('input.txt','r')
sys.stdout = open('output.txt','w')
```

# 진법 변환
왜 16진수의 데이터를 사용하는가??
* 컴퓨터는 2진수 사용하지만 10진법으로 바꾸는 경우 연산의 속도가 느림 하지만 16진수로 바꾼다면 연산의 속도를 올리면서 데이터 효율도 같이 증가시킬 수 있으므로 사용

## 10진수-> 타 진수로 변환하는법
* 원하는 타진법의 수로 나눈뒤 나머지를 거꾸로 읽음

## 16진수 <-> 2진수
* 진수표를 암기하는 것을 권장
|2진수|10진수|16진수|
|---|---|---|
|0000|0|0|
|0001|1|1|
|0010|2|2|
|0011|3|3|
|0100|4|4|
|0101|5|5|
|0110|6|6|
|0111|7|7|
|1000|8|8|
|1001|9|9|
|1010|10|a|
|1011|11|b|
|1100|12|c|
|1101|13|d|
|1110|14|e|
|1111|15|f|

* 0xF9 16진수를 2진수로 변환하기
(11111001)

* 2진수 1100101111를 16 진수로 변환
    * 11|0010|1111처럼 오른쪽 끝에서 부터 4자리씩 자르고
    * 각 자리에 맞는 16진수를 대입(0x32F)