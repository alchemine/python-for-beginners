## Chapter 04 - 연산자

### 학습목표
1. 연산자와 연산자 우선순위에 대하여 설명할 수 있다.

### 연산자
- 연산자 \
변수와 값에 대한 연산을 수행할 수 있다

| 연산자 (위에서부터 높은 우선순위)                                                       | 설명                           |
| ------------------------------------------------------------ | ------------------------------ |
| `[]`、`[:]`                                                 | 인덱스, 슬라이싱                  |
| `**`                                                         | 거듭제곱                             |
| `~`、`+`、`-`                                              | `NOT`(bit), 양수 부호, 음수 부호         |
| `*`、`/`、`%`、`//`                                       | 곱셈, 나눗셈, 나머지, 몫            |
| `+`、`-`                                                    | 덧셈、뺄셈                        |
| `>>`、`<<`                                                  | 오른쪽 이동, 왼쪽 이동(bit 시프트)                    |
| `&`                                                          | `AND`(bit)                         |
| `^`、`\|`                                                   | `XOR`(bit), `OR`(bit)              |
| `<=`、`<`、`>`、`>=`                                      | 작거나 같음, 작음, 큼, 같거나 큼 (비교 연산자) |
| `==`、`!=`                                                   | 값이 같음, 같지 않음                  |
| `is`、`is not`                                               | 객체가 같음, 같지 않음                     |
| `in`、`not in`                                                | 객체 내 값의 포함여부 (멤버 연산자)                     |
| `not`、`or`、`and`                                             | `NOT`, `OR`, `AND` (논리 연산자)                     |
| `=`、`+=`、`-=`、`*=`、`/=`、`%=`、`//=`、`**=`、`&=`、`\|=`、`^=`、`>>=`、`<<=` | 연산 후 값을 할당 (복합 할당 연산자)             |

- 연산자 우선순위
  - 연산자가 실행되는 순서를 결정
  - 괄호를 사용해 직접 지정할 수 있음

### 산술연산자
```python
"""
산술 연산자

Version: 1.0
Author: 骆昊
"""
print(321 + 12)     # 덧셈, 333
print(321 - 12)     # 뺄셈, 309
print(321 * 12)     # 곱셈, 3852
print(321 / 12)     # 나눗셈, 26.75
print(321 // 12)    # 몫, 26
print(321 % 12)     # 나머지, 9
print(321 ** 12)    # 거듭제곱, 1196906950228928915420617322241
```

```python
"""
산술 연산자의 우선순위

Version: 1.0
Author: 骆昊
"""
print(2 + 3 * 5)           # 17
print((2 + 3) * 5)         # 25
print((2 + 3) * 5 ** 2)    # 125
print(((2 + 3) * 5) ** 2)  # 625
```

### 할당 연산자
`=`를 기준으로 오른쪽 **값**을 왼쪽 **변수**에 할당

```python
"""
할당 연산자 및 복합 할당 연산자

Version: 1.0
Author: 骆昊
"""
a = 10
b = 3
a += b        # a = a + b
a *= a + 2    # a = a * (a + 2)
```

### 비교 연산자
값을 비교할 수 있다.

```python
"""
비교 연산자

Version: 1.0
Author: 骆昊
"""
flag0 = 1 == 1
flag1 = 3 > 2
flag2 = 2 < 1
```

### 논리 연산자
`==`를 이용하여 값을 비교할 수 있다.

```python
"""
논리 연산자

Version: 1.0
Author: 骆昊
"""
flag3 = flag1 and flag2
flag4 = flag1 or flag2
flag5 = not flag0
print('flag0 =', flag0)     # flag0 = True
print('flag1 =', flag1)     # flag1 = True
print('flag2 =', flag2)     # flag2 = False
print('flag3 =', flag3)     # flag3 = False
print('flag4 =', flag4)     # flag4 = True
print('flag5 =', flag5)     # flag5 = False
print(flag1 and not flag2)  # True
print(1 > 2 or 2 == 3)      # False
```

### 예제
#### 예제 1: 화씨 → 섭씨 변환

$\small{C = (F - 32) / 1.8}$
- $F$: 화씨 온도
- $C$: 섭씨 온도

```python
"""
화씨 → 섭씨 변환

Version: 1.0
Author: alchemine
"""
f = float(input('화씨 온도를 입력하세요: '))
c = (f - 32) / 1.8
print(f'{f:.1f}화씨 = {c:.1f}섭씨')  # .1f: 부동소수점값을 소수점 1자리까지 표시
```

#### 예제 2: 원의 원주와 면적 계산
```python
"""
원의 원주와 면적 계산

Version: 1.0
Author: alchemine
"""
from math import pi

radius = float(input('원의 반지름을 입력하세요: '))
perimeter = 2 * 3.14 * radius  # 2 * pi * radius
area = 3.14 * radius * radius  # pi * radius**2
print(f'원주: {perimeter:.2f}')
print(f'면적: {area:.2f}')
```

#### 예제 3: 윤년 결정
윤년의 조건
1. 400의 배수
2. 100의 배수가 아닌 4의 배수

```python
"""
연도를 입력받아 윤년인 경우 True, 평년인 경우 False를 출력

Version: 1.0
Author: alchemine
"""
year = int(input('연도를 입력하세요(1582년 이후): '))
cond_400 = year % 400 == 0
cond_100 = year % 100 != 0
cond_4 = year % 4 == 0
is_leap = cond_400 or cond_100 and cond_4
print(f'{is_leap = }')
```