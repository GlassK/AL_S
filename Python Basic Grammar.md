## 변수와 출력함수

```python
'''
변수명 정하기
1) 영문과 숫자, _로 이루어진다
2) 대소문자를 구분한다
3) 문자나 , _ 로 시작한다
4) 특수문자를 사용하면 안된다(&, % 등)
5) 키워드를 사용하면 안된다(if, for 등)
'''
a = 1
A = 2
c = 5
A1 = 3
# 2b = 4
_b = 4
print(a, A, c)  # 1 2 5
print(a, A, A1, _b)  # 1 2 3

a, b, c = 3, 2, 1
print(a, b, c)  # 3 2 1

# 값 교환
a, b = 10, 20
print(a, b)  # 10 20
a, b = b, a
print(a, b)  # 20 10

# 변수 타입
a = 12345
print(a)  # 12345
print(type(a))  # <class 'int'>
a = 12.123456789123456789  # 실수형은 8바이트까지만 저장 가능
print(a)  # 12.123456789123457
print(type(a))  # <class 'float'>
a = 'student'
print(a)  # student
print(type(a))  # <class 'str'>

# 출력방식
print("number")
a, b, c = 1, 2, 3
print(a, b, c)  # 1 2 3
print("number : ", a, b, c)  # number :  1 2 3
print(a, b, c, sep=', ')  # 1, 2, 3
print(a, b, c, sep=',')  # 1,2,3
print(a, b, c, sep='\n')  # 한 줄에 하나씩 출력.
print(a, end=' ')  # print()에는 개행이 기본으로 포함되어 있음. 없애려면 end=' '
print(b, end=' ')
print(c, end=' ')
```



## 변수입력과 연산자

```python
a = input("숫자를 입력하세요 : ")
print(a)

a, b = input("숫자를 입력하세요 : ").split()  # ex. 2 3
print(type(a))  # <class 'str'>
c = a + b
print(type(c))  # <class 'str'>
print(c)  # 23

a, b = input("숫자를 입력하세요 : ").split()  # ex. 2 3
a = int(a)
b = int(b)
print(type(a))  # <class 'int'>
print(a + b)  # 5

a, b = map(int, input("숫자를 입력하세요 : ").split())  # ex. 2 3 / int는 내장함수이고 map(함수, data) 형태로 사용한다
print(a + b)  # 5
print(a - b)  # -1
print(a * b)  # 6
print(a / b)  # 0.6666666666666666
print(a // b)  # 0
print(a % b)  # 2
print(a ** b)  # 8

a = 4.3
b = 5
c = a + b
print(type(c))  # <class 'float'> 범위상 실수에 정수가 포함됨
print(c)  # 9.3
```



## 조건문 (if분기문, 다중if문)

```python
x = 7
if x == 7:  # == 대신 !=을 넣으면 아래의 문장 실행 안 됨
    print("Lucky")
    print("ㅋㅋ")

x = 15  # x = 12이면 내부 if문에서 거짓이므로 출력 안 됨
if x >= 10:
    if x % 2 == 1:
        print("10 이상의 홀수")

x = 9  # x = 10이면 내부 if문에서 거짓이므로 출력 안 됨
if x > 0:
    if x < 10:
        print("10보다 작은 자연수")

x = 7
if x > 0 and x < 10:
    print("10보다 작은 자연수")

x = 7
if 0 < x < 10:
    print("10보다 작은 자연수")

# 분기문
x = 10  # x = -3이면 else로
if x > 0:
    print("양수")
else:
    print("음수")

# 다중 분기문 (하나의 문장)
x = 93
if x >= 90:
    print('A')  # A
elif x >= 80:
    print('B')
elif x >= 70:
    print("C")
elif x >= 60:
    print("D")
else:
    print("F")

# 별개의 여러 문장
x = 93
if x >= 90:
    print('A')  # A
if x >= 80:
    print('B')  # B
if x >= 70:
    print("C")  # C
```



## 반복문(for, while, break, continue)

```python
a = range(10)
print(list(a))  # [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
a = range(1, 11)
print(list(a))  # [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

for i in range(10):
    print("hello")  # hello 10줄 출력
    print(i)  # 0부터 9까지 출력

for i in range(10, 0, -1):
    print(i)  # 10부터 1씩 감소하며 1까지 출력
for i in range(10, 0, -2):
    print(i)  # 10부터 2씩 감소하며 1까지 출력

i = 1
while i <= 10:
    print(i)  # 1부터 1씩 증가하며 10까지 출력
    i = i + 1
i = 10
while i >= 1:
    print(i)  # 10부터 1씩 감소하며 1까지 출력
    i = i - 1

i = 1
while True:  # 무한 반복
    print(i)
    if i == 10:  # 무한 반복을 방지하는 장치
        break
    i += 1  # i = i + 1과 같음

for i in range(1, 11):
    if i % 2 == 0:
        continue  # 위의 조건을 만족할 때는 이후의 코드를 실행하지 않고 다음 반복 바로 실행
    print(i)

# for-else문 (모르고 있던 거!)
for i in range(1, 11):
    print(i)
    if i == 5:
        break
else:  # for문이 끝까지 실행(정상 종료)된 뒤에만 else문 실행
    print(11)
```



## 반복문을 이용한 문제 풀이

```python
'''
반복문을 이용한 문제풀이
    1) 1부터 N까지 홀수 출력하기
    2) 1부터 N까지의 합 구하기
    3) N의 약수 출력하기
'''
# 1번
n = int(input())
for i in range(1, n+1):
    print(i)

n = int(input())
for i in range(1, n+1):
    if i % 2 == 1:
        print(i)

# 2번
n = int(input())
sum = 0
for i in range(1, n+1):
    sum = sum + i
else:
    print(sum)

# 3번
n = int(input())
for i in range(1, n+1):
    if n % i == 0:
        print(i, end=' ')  # 줄바꿈 없이 출력
```



## 중첩반복문(2중 for문)

```python
for i in range(5):
    for j in range(5):
        print(j, end=' ')
    print()  # 줄바꿈

for i in range(5):
    print('i:', i, sep='', end=' ')
    for j in range(5):
        print('j:', j, sep='', end=' ')
    print()

for i in range(5):
    for j in range(5):
        print("*", end=' ')
    print()

for i in range(5):
    for j in range(i+1):
        print("*", end=' ')
    print()

for i in range(5):
    for j in range(5-i):
        print("*", end=' ')
    print()
```



## 문자열과 내장함수

```python
msg = "It is Time"
print(msg.upper())  # 모두 대문자로
print(msg.lower())  # 모두 소문자로
print(msg)  # 원래 값은 그대로 유지됨

tmp = msg.upper()  # 모두 대문자로 변환 후 저장
print(tmp)
print(tmp.find('T'))  # T와 일치하는 맨 처음 것의 인덱스 번호 리턴
print(tmp.count('T'))  # T와 일치하는 것의 개수 리턴

print(msg[:2])  # 슬라이스 (인덱스 0과 1만 출력)
print(msg[3:5])   # 슬라이스 (인덱스 3과 4만 출력)
print(len(msg))  # 문자열의 길이

# 문자열 출력하는 방법 1
for i in range(len(msg)):
    print(msg[i], end=' ')
print()

# 문자열 출력하는 방법 2
for x in msg:
    print(x, end=' ')
print()

for x in msg:
    if x.isupper():  # 대문자이면 참
        print(x, end=' ')
print()

for x in msg:
    if x.islower():  # 소문자이면 참
        print(x, end=' ')
print()

for x in msg:
    if x.isalpha():  # 알파벳이면 참 (공백은 제외)
        print(x, end=' ')
print()

tmp = 'AZ'
for x in tmp:
    print(ord(x))  # ASCII number 구하기 (대문자)

tmp = 'az'
for x in tmp:
    print(ord(x))  # ASCII number 구하기 (소문자)

tmp = 65
print(chr(tmp))  # 대응되는 ASCII number에 대한 문자
```



## 리스트와 내장함수

```python
import random as r

a = []  # 빈 리스트 생성 1
print(a)
b = list()  # 빈 리스트 생성 2
print(b)

a = [1, 2, 3, 4, 5]
print(a)  # [1, 2, 3, 4, 5]
print(a[0])  # 1

b = list(range(1, 11))  # 1부터 10까지 리스트 초기화
print(b)

c = a + b  # [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
print(c)  # [1, 2, 3, 4, 5, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

print(a)  # [1, 2, 3, 4, 5]
a.append(6)  # 리스트 요소 추가
print(a)  # [1, 2, 3, 4, 5, 6]

a.insert(3, 7)  # 3번 인덱스에 7 추가 (기존 3번 인덱스의 값부터는 한 칸씩 밀려남)
print(a)  # [1, 2, 3, 7, 4, 5, 6]

a.pop()  # 맨 뒤의 요소 삭제
print(a)  # [1, 2, 3, 7, 4, 5]
a.pop(3)  # 특정 인덱스 요소 삭제
print(a)  # [1, 2, 3, 4, 5]

a.remove(4)  # 특정 요소 삭제
print(a)  # [1, 2, 3, 5]

print(a.index(5))  # 특정 요소의 인덱스 리턴


a = list(range(1, 11))
print(a)
print(sum(a))  # 리스트의 모든 요소 합 리턴
print(max(a))  # 리스트의 요소 중 가장 큰 값 리턴
print(min(a))  # 리스트의 요소 중 가장 작은 값 리턴
print(min(7, 5))  # 5 (인자 값 중 가장 작은 값 리턴)
print(min(7, 3, 5))  # 3

print(a)
r.shuffle(a)  # random 모듈 활용. 무작위로 리스트 요소 섞음
print(a)  # ex. [4, 10, 1, 3, 5, 9, 6, 7, 2, 8]

a.sort(reverse=True)  # 내림차순 정렬
print(a)  # [10, 9, 8, 7, 6, 5, 4, 3, 2, 1]
a.sort()  # 오름차순 정렬
print(a)  # [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

a.clear()  # 모든 요소 삭제
print(a)  # []
```

```python
a = [23, 12, 36, 53, 19]
print(a[:3])  # [23, 12, 36]
print(a[1:4])  # [12, 36, 53]
print(len(a))  # 5

for i in range(len(a)):
    print(a[i], end=' ')
print()

# 더 선호하는 방법
for x in a:
    print(x, end=' ')
print()

for x in a:
    if x % 2 == 1:
        print(x, end=' ')
print()

for x in enumerate(a):  # 인덱스와 원소 값을 tuple 형태로 리턴
    print(x)
print()
'''
(0, 23)
(1, 12)
(2, 36)
(3, 53)
(4, 19)
'''

b = (1, 2, 3, 4, 5)
print(b[0])  # 1
# b[0] = 7  #값 변경 불가능(리스트와의 차이점)

for x in enumerate(a):
    print(x[0], x[1])
print()
'''
0 23
1 12
2 36
3 53
4 19
'''

# 주로 이용하는 방법 (선호)
for index, value in enumerate(a):
    print(index, value)
print()

if all(60 > x for x in a):  # 반복문 돌면서 모두 참일 경우에만 all()의 결과는 참
    print("YES")
else:
    print("NO")

if any(15 > x for x in a):  # 반복문 돌면서 하나라도 참이면 any()의 결과는 참
    print("YES")
else:
    print("NO")
```



## 2차원 리스트 생성과 접근

```python
# 1차원 리스트
a = [0] * 3
print(a)  # [0, 0, 0]

# 2차원 리스트 (문제 해결할 때는 표의 개념으로 접근하면 좋다)
a = [[0] * 3 for _ in range(3)]
print(a)  # [[0, 0, 0], [0, 0, 0], [0, 0, 0]]
a[0][1] = 1  # 리스트[행 인덱스][열 인덱스]
print(a)
a[1][1] = 2
print(a)

# 표 형태로 출력
for x in a:
    print(x)
'''
[0, 1, 0]
[0, 2, 0]
[0, 0, 0]
'''

# 표 형태(괄호 제거)로 출력
for x in a:
    for y in x:
        print(y, end=' ')
    print()
'''
0 1 0 
0 2 0 
0 0 0 
'''
```



## 함수 만들기

```python
def add(a, b):
    c = a + b
    print(c)

add(3, 2)
add(5, 7)


def add(a, b):
    c = a + b
    return c  # 함수 종료

x = add(3, 2)
print(x)
print(add(3, 2))


def add(a, b):
    c = a + b
    d = a - b
    return c, d  # 여러 값을 tuple 형태로 함께 리턴할 수 있다

print(add(3, 2))  # (5, 1)


# 소수인지 판별하는 함수
def isPrime(x):
    for i in range(2, x):
        if x % i == 0:
            return False
    return True

a = [12, 13, 7, 9, 19]
for y in a:
    if isPrime(y):
        print(y, end=' ')  # 13 7 19
```



## 람다함수

```python
# 일반 함수
def plus_one(x):
    return x + 1

print(plus_one(1))  # 2

# 람다 함수 (표현식의 일종) - 내장함수의 인자로 사용하기에 편리하다
plus_two = lambda x: x + 2
print(plus_two(1))  # 3

def plus_one(x):
    return x + 1
    
a = [1, 2, 3]
print(list(map(plus_one, a)))  # [2, 3, 4]
# 람다 함수
print(list(map(lambda x: x + 1, a)))  # [2, 3, 4]
```



## 최솟값 구하기

```python
arr = [5, 3, 7, 9, 2, 5, 2, 6]
arr_min = float('inf')  # python에서 가장 큰 값 (무한) / arr[0]로 초기화해도 됨
# 첫번째 방법
for i in range(len(arr)):
    print(arr[i])  # 한 줄에 원소 하나씩 출력
    if arr[i] < arr_min:  # 무한대로 초기화되어 있으므로 무조건 처음에는 True
        arr_min = arr[i]
print(arr_min)  # 2

# 두번째 방법
for x in arr:
    if x < arr_min:
        arr_min = x
print(arr_min)  # 2
```



## 재귀함수와 스택

재귀함수: 자기 자신을 호출하는 함수. 스택을 사용하여 작동된다. 반복문의 대체재.

```python
def DFS(x):
    if x > 0:
        DFS(x-1)
        print(x, end=' ')


if __name__ == "__main__":
    n = int(input())
    DFS(n)
```

- 3이 입력되면 1부터 3까지 출력하는 함수

- main 함수와 재귀 함수 구분

  - 스크립트가 실행되면 main부터 실행된다

- 재귀함수 DFS(깊이우선탐색, Deapth-First Search)

  - `x > 0` : 조건을 지정하지 않으면 무한 반복 실행된다

  - 스택을 사용하여 작동한다

    |    DFS | 스택 프레임                             |
    | -----: | :-------------------------------------- |
    | DFS(0) | 매개변수 x=0<br />복귀주소 DFS(1)의 2줄 |
    | DFS(1) | 매개변수 x=1<br />복귀주소 DFS(2)의 2줄 |
    | DFS(2) | 매개변수 x=2<br />복귀주소 DFS(3)의 2줄 |
    | DFS(3) | 매개변수 x=3<br />복귀주소 main의 2줄   |

    - DFS가 호출되는 순간 DFS의 핵심 내용이 **메모리에 기록**(할당)된다

      - **매개변수, 지역변수, 복귀 주소**(반환되어야 할 주소)

        ex. DFS(3) 호출 -> 매개변수(x=3), 복귀 주소(main의 두 번째 줄)

      - 각 매개변수 x는 모두 다른 x이다

    - 맨 아래에서 위쪽 방향으로 스택에 저장(push)

    - **스택 프레임**: 각 함수에 대한 매개변수, 지역 변수, 복귀 주소 묶음(2열의 각 칸)

    - DFS(0)의 스택 프레임 저장 후 종료, 스택에서 메모리 해제 및 삭제
      - 복귀 주소를 참조하여 복귀한다 (ex. DFS(1)로)
      - 복귀한 후 다음 라인(ex. DFS(1)의 3줄)부터 실행한다
      - 나머지에 대해서도 모두 동일하게 적용된다
        - 위에서 아래 방향으로 스택에서 제거(pop)



## 전역변수와 지역변수

```python
def DFS1():
    #cnt = 3
    print(cnt)


def DFS2():
    #global cnt
    if cnt == 5:
        #cnt = cnt + 1
        print(cnt)


if __name__ == "__main__":
    cnt = 5
    DFS1()
    DFS2()
    print(cnt)
```

- 전역변수
  - main 내부에서 선언한 변수
  - 모든 함수가 접근하고 값을 변경할 수 있는 변수
- `cnt = 5`는 1) 변수를 생성하는 것과 동시에 2) 변수에 값을 할당하는 것이다.
- 모든 코드는 실제로 실행되기 전에 번역(해석)을 먼저 거친다

- `DFS1()` 함수 실행

  - 먼저 `cnt`가 지역변수인지 확인
    - 지역변수라면 해당 함수 내에서 할당된 값으로 진행
    - 지역변수가 아니면 전역변수인지 확인 (전역변수도 아니면 에러)
  - 즉, 지역 변수로서의 값이 더 우선된다

  - 만약 `cnt = 3` 이라는 코드가 들어가게 된다면 (주석 자리에)
    - `cnt`는 `DFS1()`의 지역변수로서 3이 된다

- `DFS2()` 함수 실행

  - 만약 `cnt = cnt + 1` 이라는 코드가 들어가게 된다면 (주석 자리에)
    - **변수 `cnt`를 새로 생성하고 값을 할당한 것이므로 `cnt`는 지역 변수이다.**
    - 그래서 if문을 실행할 때는 아직 할당되지 않은 변수라고 에러가 뜬다!

  - cnt를 지역변수가 아닌 **전역변수로 작동시키려면 `global cnt`**를 if문 전에 작성하면 된다!

```python
def DFS():
    #global a
    #a = a + [4]
    #a = [7, 8]
    a[0] = 7
    print(a)

if __name__ =="__main__":
    a = [1, 2, 3]
    DFS()
    print(a)
```

위의 경우와 달리 `a[0] = 7`을 했는데도 리스트 a가 새로 생성되지 않고 전역변수로 쓸 수 있는지?

- `a[0] = 7`은 새로운 리스트를 생성한 게 아니라, 리스트 a의 인덱스 0번 값을 변경하는 것 뿐이다
- 만약 `a = [7, 8]` (주석 참고) 처럼 리스트 a를 새로 생성하고 할당하면 a는 지역변수가 된다 

- `a = a + [4]` 의 경우 a를 지역변수로 새로 생성 및 할당하지만(`a = ~`) 리스트 [4]와 더할 a가 없으므로 에러가 발생한다
  - 만약 전역 변수인 리스트 a를 사용하려면 `global a`라고 명시해야 한다