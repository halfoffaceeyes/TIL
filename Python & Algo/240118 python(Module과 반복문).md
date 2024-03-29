# Module
## 개요
* 과학자, 수학자가 모든 이론을 새로 만들거나 증명하지 않는 것처럼 개발자 또한 프로그램 전체를 모두 혼자 힘으로 작성하는 것은 드문일
* 다른 프로그래머가 이미 작성해 놓은 수천, 수백만 줄의 코드를 사용하는 것은 생산성에서 매우 중요한 일
> 모듈은 하나의 파일

>한 파일로 묶인 변수와 함수의 모음. 특정한 기능을 하는 코득 작성된 파이썬 파일(.py)

### 모듈 예시
* 파이썬의 math 모듈
* 파이썬이 미리 작성해 둔 수학 관련 변수와 함수가 작성된 모듈
```python
import math
print(math.pi)  # 3.141592653589793

print(math.sqrt(4)) # 2.0
```

## 모듈 활용하기
### 모듈 가져오기
* 모듈 내 변수와 함수에 접근하려면 import문이 필요
* 내장함수 help를 사용해 모듈에 무엇이 들어있는지 확인 가능 (우선 import를 먼저 사용)

```python
import math
help(math)
```
>이때 설명이 많이 나오는데 엔터를 통해 추가 출력내용을 확인할수 있고 q를 눌러 출력을 멈출 수 있음

* '.(dot)'은 "점의 왼쪽 객체에서 점의 오른쪽 이름을 찾아라"라는 의미의 연산자

### 모듈을 import하는 다른 방법(사용하고 싶은 것만 불러옴)
* **from**절을 활용해 특정 모듈을 미리 참조하고 어떤 요소를 import할지 명시
```python
import math

print(math.pi)
print(math.sqrt)

from math import pi, sqrt

print(pi)
print(sqrt(4))

# 덜 쓰면 명시성이 떨어짐
# but이 경우는 위의 케이스가 더 명시적인것임
# 왜냐면 import절은 나중에 코드를 짜면 위에 안보이기 때문에 어떤 모듈을 사용하는 것인지 알기가 어려움. 따라서 math.pi이런식으로 표기되면 해석하기가 용이
```
### 모듈의 주의사항
> 만약 서로 다른 모듈이 같은 이름의 함수를 제공하는 경우 문제 발생
* 이 경우 마지막에 import된 이름으로 대체됨
```python
from math import pi, sqrt
from my_math import sqrt
# 이경우 이름이 겹쳐서 my_math모듈만 import
#from 절을 안썼으면 겹칠일이 없었음 import를 쓰기 때문
# 같은 이유로 from 모듈 import *은 권장하지 않음
```

## 사용자 정의 모듈
### 직접 정의한 모듈 사용하기
1. 모듈 my_math.py작성
2. 두수의 합을 구하는 add 함수 작성
3. my_math 모듈을 import후 add 함수 호출

```python
def add(x,y):
    return x + y
    # 파일명 : my_math.py
```
```python
import my_math

print(my_math.add(1,2))
```

# 파이썬 표준 라이브러리
변수와 함수가 너무 많아져서 묶기위해 공통점을 찾아 모듈을 형성 -> 모듈이 너무 많아져서 공통점을 찾아 패키지를 만듦 -> 패키지와 모듈들의 전체를 아우르는 것을 라이브러리라고 함
* 모듈<패키지<라이브러리
## 파이썬 표준 라이브러리(PSL)
파이썬 언어와 함께 제공되는 다양한 모듈과 패키지의 모음

## 패키지
관련된 모듈들을 하나의 디렉토리에 모아 놓은 것

### 패키지 사용하기(1/2)
* 아래와 같은 디렉토리 구조로 작성
* 패키지 3개 : my_package, math, statistics
* 모듈 2개 : my_math(add 함수), tools(mod함수)
--------
파일 경로

sample.py

my_package(폴더)
- math(폴더) - mymath.py
- statistics(폴더) - tools.py
----------

```python
# sample.py

from my_package.math import my_math
from my_package.statistics import tools

print(my_math.add(1,2)) #3
print(tools.mod(1,2)) #1
```

### PSL 내부 패키지 vs 외부 패키지
* PSL 내부 패키지 : 설치 없이 바로 import하여 사용
* 외부 패키지 : 개발환경에서 제일 많이 활용할 것, pip를 사용하여 설치 후 import필요

### pip
외부 패키지들을 설치하도록 도와주는 파이썬의 패키지 관리 시스템
* PyPI(Python Package Index)에 저장된 외부 패키지들을 설치
* https://pypi.org # 사람들이 업로드한 package를 받아올수 있는 공간

#### 패키지 설치
```python
$ pip install sompackage
$ pip install sompackage==1.0.5
$ pip install sompackage>=1.0.4
#terminal에서 실행

```
request 라이브러리
외부의 데이터를 받아서 처리할 때 사용하는 라이브러리

```python
$ pip install requests #terminal에서 실행

import requests

url = 'https://random-data-api.com/api/v2/users'
response= requests.get(url).json()

print(response)
```
### 패키지 사용목적
모듈들의 이름 공간을 구분하여 충돌을 방지
모듈들을 효율적으로 관리하고 재사용할 수 있도록 돕는 역할

# 제어문 - 핵심 내용!
코드의 실행 흐름을 제어하는 데 사용되는 구문 **조건**에 따라 코드 블록을 실행하거나 **반복**적으로 코드를 실행

## 조건문
주어진 조건식을 평가하여 해당 조건이 참(True)인 경우에만 코드 블록을 실행하거나 건너뜀
### if / elif / else
파이썬 조건문에 사용되는 키워드
#### if statement의 기본 구조
```python
if 표현식:
    코드 블록
elif 표현식:
    코드 블록
else:
    코드 블록
```

### 조건문 예시
```python
a =5
if a >3:
    print('3 초과')
else:
    print('3 이하')

print(a)
```
#### 복수 조건문 예시
```python
dust = 35
if dust > 150:
    print('매우 나쁨')
elif dust > 80:
    print('나쁨')
elif dust > 30:
    print('보통')
else:
    print('좋음')
# 조건문은 조건식을 동시에 검사하는 것이 아니라 항상 순차적으로 비교를 한 후에 값을 결정
```
#### 중첩 조건문 예시
```python
dust = 35
if dust > 150:
    print('매우 나쁨')
    if dust >300:
        print('위험해요!') # 조건문안에 조건문을 중첩조건문이라고 함
elif dust > 80:
    print('나쁨')
elif dust > 30:
    print('보통')
else:
    print('좋음')
# 조건문은 조건식을 동시에 검사하는 것이 아니라 항상 순차적으로 비교를 한 후에 값을 결정
```

# 반복문(Loop Statement)
주어진 코드 블록을 여러 번 반복해서 실행하는 구문
* for - 특정 작업을 반복적으로 수행(제한된 작업량이 있음)
* while - 주어진 조건이 참인 동안 반복해서 실행(제한된 작업량이 없지만 조건이 False가 될때까지 작업)

## for
임의의 시퀀스의 항목들을 그 시퀀스에 들어있는 순서대로 반복(시퀀스의 요소의 양에 따라 정해짐)
```python
for 변수 in 반복 가능한 객체: # 시퀀스, dict set도 반복 가능
    코드블록
```
#### 반복가능한 객체
반복문에서 순회할 수 있는 객체(시퀀스 객체 뿐만 아니라 dict, set등도 포함)

#### for 문 원리
* 리스트 내 첫 항목미 반복 변수에 할당되고 코드 블록이 실행
* 다음으로 반복 변수에 리스트의 2번째 항목이 할당되고 코드 블록이 다시 실행
* ... 마지막으로 반복 변수에 리스트의 마지막 요소가 할당되고 코드블록의 실행

```python
items = ['apple', 'banana', 'coconut']
# 코드의 가독성을 위해 변수명을 지을때 단수형 복수형을 같이 고려해서 짓자!
for item in items:
    print(item)

'''
apple
banana
coconut
'''
```

```python
# 문자열도 시퀀스이기 때문에 for문이 가능함
country = 'Korea'
for char in country:
    print(char)

'''
K
o
r
e
a
'''
```

```python
# range도 시퀀스이기 때문에 순회가 가능함
for i in range(5):
    print(i)

'''
0
1
2
3
4
'''
```
```python
# dict 순회
my_dict = {
    'x' : 10,
    'y' : 20,
    'z' : 30,
}

for key in my_dict:
    print(key)
    print(my_dict[key])

'''
x
10
y
20
z
30
'''
# dict 순회시 키값이 출력됨
```

```python
# 인덱스로 순회
numbers = [4,6,10,-8,5]
for i in range(len(numbers)):
    numbers[i] = numbers[i] *2
print(numbers)
```
#### 중첩된 반복문
```python
outers = ['a','b']
inners = ['c','d']
for outer in outers:
    for inner in inners:
        print(outer, inner)

'''
a c
a d
b c
b d
'''
```
print가 호출되는 횟수 = len(outers) * len(inners)

#### 중첩리스트 순회
* 안쪽 리스트 요소에 접근하려면 바깥 리스트를 순회하면서 중첩 반복을 사용해 각 안쪽 반복을 순회 - IM test기준

```python
elements = [['a','b'],['c','d']]
for elem in elements:
    for item in elem:
        print(item)
'''
[
    ['a', 'b'],
    ['c', 'd']
]
위처럼 행렬로 생각하는 습관을 가지자
'''
```

## while 문
주어진 조건식이 참(True)인 동안 코드를 반복해서 실행

== 조건식이 거짓(False)가 될 때까지 반복
```python
while 조건식:
    코드블록
```
### while문 예시
```python
a=0
while a<3:
    print(a)
    a +=1
print('끝')

'''
0
1
2
끝
'''
```
#### 사용자 입력에 따른 반복
```python
number = int(input('양의 정수를 입력해주세요.: '))
while number <= 0:
    if number < 0:
        print('음수를 입력했습니다.')
    else:
        print('0은 양의 정수가 아닙니다.')
    number = int(input('양의 정수를 입력해주세요.: '))
print('잘했습니다!')
```
while문은 종료조건(False)가 반드시 필요!

### 적절한 반복문 활용하기
* for
    * 반복 횟수가 명확하게 정해져 있는 경우에 유용
    * 예를 들어 리스트, 튜플, 문자열 등과 같은 시퀀스 형식의 데이터를 처리할 때
* while
    * 반복 횟수가 불명확하거나 조건에 따라 반복을 종료해야 할 때 유용
    * 예를 들어 사용자의 입력을 받아서 특정 조건이 충족될 때까지 반복할 때

## 반복 제어
for문과 while은 매 반복마다 본문 내 모든 코드를 실행하지만 때때로 일부만 실행하는 것이 필요할 때가 있음
* break : 반복을 즉시 중지
* continue : 다음 반복으로 건너뜀

### break 예시
```python
number = int(input('양의 정수를 입력해주세요.: '))
while number <= 0:
    if number == -9999:
        print('프로그램을 종료합니다.')
        break
    '''
    양의 정수를 입력해주세요. : -9999
    프로그램을 종료합니다.
    잘했습니다!
    '''
    if number < 0:
        print('음수를 입력했습니다.')
    else:
        print('0은 양의 정수가 아닙니다.')
    number = int(input('양의 정수를 입력해주세요.: '))
print('잘했습니다!')
```
#### break 예시 2
리스트에서 첫번째 짝수만 찾은 후 반복 종료
```python
numbers = [1, 3, 5, 6, 7, 9, 10, 11]
found_even = False
for num in numbers:
    if num % 2 == 0:
        print('첫 번째 짝수를 찾았습니다:', num)
        found_even = True
        break
if not found_even:
    print('짝수를 찾지 못했습니다') # if not 조건문 : 조건문이 False이면 아래를 실행
"""
첫 번째 짝수를 찾았습니다: 6
"""
```
### continue 예시
* 리스트에서 홀수만 출력하기
(현재 반복문의 남은 코드를 건너뛰고 다음 반복으로 넘어감)
```py
numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
for num in numbers:
    if num % 2 == 0:
        continue
    print(num)
'''
1
3
5
7
9
'''
```
### break와 continue의 주의사항


# List Comprehesion
간결하고 효율적인 리스트 생성 방법
## 구조
[expression for 변수 in iterable if 조건식]
list와 많이 사용됨
list(expression for 변수 in iterable if 조건식)
! for 변수 in iterable if 조건식을 먼저 작성후 expression을 작성(변수를 나타내는 임시변수)

## 활용 예제
```py
# 적용 안했을때
numbers = [1, 2, 3, 4, 5]
squared_numbers = []

for num in numbers:
    squared_numbers.append(num**2)

print(squared_numbers)  # [1, 4, 9, 16, 25]
```
```py
# List comprehension
numbers = [1, 2, 3, 4, 5]
squared_numbers = [num**2 for num in numbers]

print(squared_numbers)  # [1, 4, 9, 16, 25]
```
list comprehension을 먼저 사용하려고 하지말고 for문 사용하고 변환하는 연습

가독성은 나쁘지만 속도는 빠름!


# 참고
## pass
> 아무런 동작도 수행하지 않고 넘어가는 역할
문법적으로 문장이 필요하지만 프로그램 실행에는 영향을 주지 않아야할 때 사용

1. 지금 당장 에러가 날수 있는 미완성 코드를 그냥 넘기는 역할로 많이 사용
2. 조건문에서 아무런 동작을 수행하지 않아야 할 때 사용
3. 무한 루프에서 조건이 충족되지 않을 때 pass를 사용하여 루프를 계속진행하는 방법

## enumerate(iterable, start =0)
iterable 객체의 각 요소에 대해 인덱스와 함께 반환하는 내장함수
```py
fruits = ['apple', 'banana', 'cherry']

for index, fruit in enumerate(fruits):
    print(f'인덱스 {index}: {fruit}')

print(enumerate(fruits))  # <enumerate object at 0x000002133DA99700>
print(list(enumerate(fruits)))  # [(0, 'apple'), (1, 'banana'), (2, 'cherry')]
# 인덱스와 값을 같이 출력할 수 있음

```

