# 🐍 Python 문법 총정리 

> 💡 기본 구조, 빠른 입출력, 자주 쓰는 문법 패턴 위주  

> 💡 시간복잡도, 자료구조 활용, 예외 상황 처리까지 고려

---

## 📥 1. 입출력

### 🔹 기본 입력

```python
n = int(input())                       # 한 줄에 하나의 숫자 입력
arr = list(map(int, input().split()))  # 공백으로 구분된 여러 숫자 입력
```

#### ✅ 예제 1: 하나의 정수 입력받아 출력

```python
# 입출력
5

입력값은 5입니다.

n = int(input())
print(f"입력값은 {n}입니다.")
```

#### ✅ 예제 2: 공백 구분된 정수 리스트 입력

```python
# 입출력
1 2 3 4 5

리스트의 합: 15

arr = list(map(int, input().split()))
print("리스트의 합:", sum(arr))
```

---

### 🔹 빠른 입력 (많이 쓰임)

```python
import sys
input = sys.stdin.readline
n = int(input().strip())
```

#### ✅ 예제 3: 빠른 입력으로 여러 줄 입력

```python
# 입출력
3
10
20
30

합계: 60

import sys
input = sys.stdin.readline
n = int(input().strip())
total = 0
for _ in range(n):
    total += int(input().strip())
print("합계:", total)
```

---

### 🔹 여러 줄 입력

```python
for _ in range(n):
    a, b = map(int, input().split())
```

#### ✅ 예제 4: 두 수 입력받아 합 출력 (여러 줄)

```python
# 입출력
3
1 2
3 4
5 6

3
7
11

n = int(input())
for _ in range(n):
    a, b = map(int, input().split())
    print(a + b)
```

### 🔹 기본 입력

```python
n = int(input())
arr = list(map(int, input().split()))
```

### 🔹 빠른 입력 (많이 쓰임)

```python
import sys
input = sys.stdin.readline
n = int(input().strip())
```

### 🔹 여러 줄 입력

```python
for _ in range(n):
    a, b = map(int, input().split())
```

---

## 🧾 2. 조건문 & 반복문

### 🔹 조건문

```python
if a > b:
    ...
elif a == b:
    ...
else:
    ...
```

#### ✅ 예제 1: 두 수 비교하기

```python
# 입출력
3 5

B가 더 큽니다.

a, b = map(int, input().split())
if a > b:
    print("A가 더 큽니다.")
elif a < b:
    print("B가 더 큽니다.")
else:
    print("같습니다.")
```

---

### 🔹 반복문

```python
for i in range(n):  # 0 ~ n-1
    ...

while condition:
    ...
```

#### ✅ 예제 2: 1부터 N까지 출력

```python
# 입출력
5

1 2 3 4 5

n = int(input())
for i in range(1, n+1):
    print(i, end=' ')
```

#### ✅ 예제 3: 입력받은 수들의 합 구하기 (while)

```python
# 입출력
10
20
30
-1

합계: 60

total = 0
while True:
    x = int(input())
    if x == -1:
        break
    total += x
print("합계:", total)
```

---

### 🔹 반복 제어

```python
break       # 반복 중단
continue    # 다음 반복으로 skip
```

#### ✅ 예제 4: 짝수만 출력 (continue)

```python
# 입출력
1 2 3 4 5

2 4

arr = list(map(int, input().split()))
for num in arr:
    if num % 2 != 0:
        continue
    print(num, end=' ')
```

### 🔹 조건문

```python
if a > b:
    ...
elif a == b:
    ...
else:
    ...
```

### 🔹 반복문

```python
for i in range(n):  # 0 ~ n-1
    ...

while condition:
    ...
```

### 🔹 반복 제어

```python
break       # 반복 중단
continue    # 다음 반복으로 skip
```

---

## 🧰 3. 리스트(List)

### 🔹 생성 & 슬라이싱

```python
arr = [1, 2, 3]
arr[1:3]      # [2, 3]
arr[::-1]     # 뒤집기
```

#### ✅ 예제 1: 리스트 뒤집기

```python
# 입출력
1 2 3 4 5

5 4 3 2 1

arr = list(map(int, input().split()))
arr = arr[::-1]
print(*arr)
```

### 🔹 함수

```python
arr.append(x)
arr.pop()
arr.sort()
arr.reverse()
arr.remove(x)
arr.index(x)
```

#### ✅ 예제 2: 정렬된 리스트에서 최대값과 최소값 출력

```python
# 입출력
50 20 70 10

최소값: 10, 최대값: 70

arr = list(map(int, input().split()))
print("최소값:", min(arr), ", 최대값:", max(arr))
```

### 🔹 리스트 컴프리헨션

```python
[x*x for x in range(5) if x%2 == 0]
```

#### ✅ 예제 3: 짝수 제곱 리스트 만들기

```python
# 입출력
5

[0, 4, 16]

n = int(input())
print([x*x for x in range(n) if x%2 == 0])
```

### 🔹 생성 & 슬라이싱

```python
arr = [1, 2, 3]
arr[1:3]      # [2, 3]
arr[::-1]     # 뒤집기
```

### 🔹 함수

```python
arr.append(x)
arr.pop()
arr.sort()
arr.reverse()
arr.remove(x)
arr.index(x)
```

### 🔹 리스트 컴프리헨션

```python
[x*x for x in range(5) if x%2 == 0]
```

---

## 🧵 4. 문자열(String)

```python
s = "hello"
s[0], s[-1]
s.upper(), s.lower()
s.count("l")
s.replace("l", "x")
"abc" in s       # 포함 여부
```

#### ✅ 예제 1: 대소문자 변환

```python
# 입출력
HeLLo

소문자: hello, 대문자: HELLO

s = input()
print("소문자:", s.lower(), ", 대문자:", s.upper())
```

#### ✅ 예제 2: 문자 개수 세기

```python
# 입출력
banana

'a'는 3번 등장

s = input()
print("'a'는", s.count('a'), "번 등장")
```

#### ✅ 예제 3: 문자열 뒤집기

```python
# 입출력
Python

nohtyP

s = input()
print(s[::-1])
```

### 🔹 문자열 리스트화

```python
list("abc")        # ['a', 'b', 'c']
''.join(arr)       # 리스트 → 문자열
```

#### ✅ 예제 4: 리스트 문자 합치기

```python
# 입출력
a b c

abc

arr = input().split()
print(''.join(arr))
```

```python
s = "hello"
s[0], s[-1]
s.upper(), s.lower()
s.count("l")
s.replace("l", "x")
"abc" in s       # 포함 여부
```

### 🔹 문자열 리스트화

```python
list("abc")        # ['a', 'b', 'c']
''.join(arr)       # 리스트 → 문자열
```

---

## 📦 5. 튜플, 딕셔너리, 집합

### 🔹 튜플

```python
a = (1, 2)
```

#### ✅ 예제 1: 튜플 언패킹

```python
a, b = (10, 20)
print(a + b)  # 출력: 30
```

### 🔹 딕셔너리

```python
d = {'a': 1}
d['a']         # 1
d.get('b', 0)  # 없는 키 기본값 반환
d.keys(), d.values()
```

#### ✅ 예제 2: 딕셔너리 값 조회

```python
# 입출력
apple

해당 키는 존재하지 않습니다.

d = {'banana': 3, 'grape': 7}
s = input()
if s in d:
    print("개수:", d[s])
else:
    print("해당 키는 존재하지 않습니다.")
```

### 🔹 집합

```python
s1 = set([1,2,3])
s2 = set([2,3,4])
s1 | s2  # 합집합
s1 & s2  # 교집합
s1 - s2  # 차집합
```

#### ✅ 예제 3: 두 집합의 교집합 출력

```python
# 입출력
1 2 3 4
3 4 5 6

공통 원소: {3, 4}

s1 = set(map(int, input().split()))
s2 = set(map(int, input().split()))
print("공통 원소:", s1 & s2)
```

### 🔹 튜플

```python
a = (1, 2)
```

### 🔹 딕셔너리

```python
d = {'a': 1}
d['a']         # 1
d.get('b', 0)  # 없는 키 기본값 반환
d.keys(), d.values()
```

### 🔹 집합

```python
s1 = set([1,2,3])
s2 = set([2,3,4])
s1 | s2  # 합집합
s1 & s2  # 교집합
s1 - s2  # 차집합
```

---

## 🔢 6. 수학 관련

```python
abs(x)
max(a, b)
min(a, b)
sum(arr)
pow(a, b)      # a^b
divmod(a, b)   # 몫, 나머지 튜플로
round(x, 2)    # 소수 둘째 반올림
```

#### ✅ 예제 1: 절댓값과 제곱 출력

```python
# 입출력
-4

절댓값: 4, 제곱: 16

x = int(input())
print("절댓값:", abs(x), ", 제곱:", pow(x, 2))
```

### 🔹 math 모듈

```python
import math
math.gcd(a, b)
math.lcm(a, b)
math.sqrt(x)
math.factorial(n)
```

#### ✅ 예제 2: 두 수의 최대공약수 & 최소공배수

```python
# 입출력
12 18

GCD: 6, LCM: 36

import math
a, b = map(int, input().split())
print("GCD:", math.gcd(a, b))
print("LCM:", math.lcm(a, b))
```

```python
abs(x)
max(a, b)
min(a, b)
sum(arr)
pow(a, b)      # a^b
divmod(a, b)   # 몫, 나머지 튜플로
round(x, 2)    # 소수 둘째 반올림
```

### 🔹 math 모듈

```python
import math
math.gcd(a, b)
math.lcm(a, b)
math.sqrt(x)
math.factorial(n)
```

---

## 🎲 7. 람다 & 정렬 key

```python
arr.sort(key=lambda x: (x[0], -x[1]))
```

#### ✅ 예제: 튜플 리스트 정렬하기

```python
# 입출력
3
1 2
3 4
1 5

(1, 5)
(1, 2)
(3, 4)

arr = [tuple(map(int, input().split())) for _ in range(int(input()))]
arr.sort(key=lambda x: (x[0], -x[1]))
for a in arr:
    print(a)
```

```python
arr.sort(key=lambda x: (x[0], -x[1]))
```

---

## 🧮 8. 2차원 리스트

```python
arr = [[0]*m for _ in range(n)]
arr[1][2] = 5
```

#### ✅ 예제: 3x3 배열에 값 채우기

```python
# 입출력
1 2 3
4 5 6
7 8 9

[[1, 2, 3], [4, 5, 6], [7, 8, 9]]

arr = [list(map(int, input().split())) for _ in range(3)]
print(arr)
```

```python
arr = [[0]*m for _ in range(n)]
arr[1][2] = 5
```

---

## 🧭 9. 방향 이동 (델타탐색)

```python
dx = [-1, 1, 0, 0]
dy = [0, 0, -1, 1]
for i in range(4):
    nx = x + dx[i]
    ny = y + dy[i]
```

#### ✅ 예제: 상하좌우 이동한 좌표 출력

```python
# 입출력
2 2

(1,2) (3,2) (2,1) (2,3)

x, y = map(int, input().split())
dx = [-1, 1, 0, 0]
dy = [0, 0, -1, 1]
for i in range(4):
    nx = x + dx[i]
    ny = y + dy[i]
    print(f"({nx},{ny})", end=' ')
```

```python
dx = [-1, 1, 0, 0]
dy = [0, 0, -1, 1]
for i in range(4):
    nx = x + dx[i]
    ny = y + dy[i]
```

---

## ⏲️ 10. 시간 측정 (테스트용)

```python
import time
start = time.time()
# 작업
print(time.time() - start)
```

#### ✅ 예제: for문 실행 시간 측정

```python
import time
start = time.time()
for i in range(1000000):
    pass
end = time.time()
print("수행 시간:", end - start, "초")
```

```python
import time
start = time.time()
# 작업
print(time.time() - start)
```

---

## 🚨 11. 예외 처리 & 종료

```python
try:
    ...
except:
    ...
exit()  # 조기 종료
```

#### ✅ 예제: 0으로 나누기 예외 처리

```python
try:
    a, b = map(int, input().split())
    print(a / b)
except ZeroDivisionError:
    print("0으로 나눌 수 없습니다.")
```

```python
try:
    ...
except:
    ...
exit()  # 조기 종료
```

---

## 📌 12. 기타

* 리스트 깊은 복사: `copy.deepcopy(arr)`
* input이 빈 줄일 경우 체크: `if not line.strip(): break`
* 최대 재귀 깊이 설정 (DFS용)

```python
import sys
sys.setrecursionlimit(10**6)
```

#### ✅ 예제: 빈 줄 입력 종료 처리

```python
while True:
    line = input()
    if not line.strip():
        break
    print("입력:", line)
```

* 리스트 깊은 복사: `copy.deepcopy(arr)`
* input이 빈 줄일 경우 체크: `if not line.strip(): break`
* 최대 재귀 깊이 설정 (DFS용)

```python
import sys
sys.setrecursionlimit(10**6)
```
