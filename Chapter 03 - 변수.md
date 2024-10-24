## Chapter 03 - 변수

### 학습목표
1. 변수와 데이터 타입에 대하여 설명할 수 있다.
2. 변수를 정의할 수 있다.

### 두 가지 질문
프로그래밍의 본격적인 시작을 위해 두 가지 질문을 생각해보자. \
이들에 대한 답이 이번에 살펴볼 변수와 이후 내용들을 우리가 왜 알아야하는지 설명해준다.

1. (컴퓨터) 프로그램이 무엇인가? \
[프로그램](https://en.wikipedia.org/wiki/Computer_program)은 **데이터(data)**와 **명령(instructions)**이 나열(sequence)된 것이다.
2. (컴퓨터) 프로그램을 작성하여 무엇을 할 수 있는가? \
**데이터**와 **명령**을 사용하여 원하는 작업을 수행하도록 컴퓨터를 제어할 수 있다.

### 데이터와 명령
- **데이터(data)**: 정보나 값으로, 메모리(RAM)에 저장되며 CPU가 이를 읽고 처리한다.
- **명령(instruction)**: 데이터를 처리하기 위한 작업 지시로, CPU가 이를 해석하고 실행하여 프로그램이 의도한 대로 동작하도록 한다.

### 변수와 데이터 타입
#### 변수(Variable)
데이터 타입(정수, 실수, 문자열 등)의 값을 담는 컨테이너 \
(실제로는, 데이터를 저장하는데 사용되는 메모리 공간을 가리킨다)

#### 데이터 타입(Data type)
1. 정수(`int`, integer): 모든 크기의 정수를 처리
    ```Python
    print(0b100)  # 2진법(binary)
    print(0o100)  # 8진법(octal)
    print(100)    # 10진법(decimal)
    print(0x100)  # 16진법(hexadecimal)
    ```
2. [부동소수점](https://ko.wikipedia.org/wiki/%EB%B6%80%EB%8F%99%EC%86%8C%EC%88%98%EC%A0%90)(`float`, float): 소수점을 포함한 숫자를 표현
    ```Python
    print(123.456)    # mathematical
    print(1.23456e2)  # scientific
    ```
3. 문자열(`str`, string): 작은 따옴표, 큰따옴표로 묶인 문자열
    ```Python
    print("abcd")
    print('abcd')
    print("""ab
    cd""")
    print('''ab
    cd''')
    ```
4. 부울(`bool`, boolean): 참/거짓 등 두 가지 상태를 나타내는 데 사용
    ```python
    print(True)
    print(False)
    ```

### 변수 명명
Python에서 변수의 이름은 기본적으로 다음과 같은 규칙에 따라 지어야 한다.

1. 문자, 숫자, 밑줄로 구성되며 숫자로 시작할 수 없음
   - `12_abc_34`: X
2. 대소문자를 구분
3. Python 키워드와 동일한 이름을 가져서는 안 되며, Python 예약어는 가능한 한 피해야 함
    - 키워드: Python 프로그램에서 특별한 의미를 가지는 단어 (`is`, `if`, `for`, `while`, `True` 등)
    - 예약어: Python 언어의 내장 함수 및 내장 모듈의 이름 (`int`, `print`, `str`, `os` 등)
4. 일반적으로, 변수의 이름은 영어 소문자를 사용하고 단어 사이를 밑줄로 연결함 (snake case)
    - Naming convention
      <img src="https://preview.redd.it/bncs74w0fxk61.png?auto=webp&s=fe03e69ebd02800384cc5a75fe6e3de11bebb8df">

### 변수의 사용
```Python
"""
변수를 사용하여 데이터를 저장하고 사칙연산을 수행

Version: 1.0
Author: 骆昊
"""
a = 45        # 변수 a에 45를 할당
b = 12        # 변수 b에 12를 할당
print(a, b)   # 45 12
print(a + b)  # 57
print(a - b)  # 33
print(a * b)  # 540
print(a / b)  # 3.75
```

#### `type()`: 변수의 데이터 타입 확인
```Python
"""
type()을 사용하여 변수의 데이터 타입을 확인

Version: 1.0
Author: 骆昊
"""
a = 100
b = 123.45
c = 'hello, world'
d = True
print(type(a))  # <class 'int'>
print(type(b))  # <class 'float'>
print(type(c))  # <class 'str'>
print(type(d))  # <class 'bool'>
```

#### 데이터 타입 변환
- `int()`: 숫자 값이나 문자열을 정수로 변환하고 기수를 지정할 수 있음
- `float()`:문자열(가능한 경우)을 부동 소수점 숫자로 변환
- `str()`: 지정한 객체를 문자열 형태로 변환하고, 인코딩 방식을 지정할 수 있음
- `chr()`: 정수([문자 인코딩](https://ko.wikipedia.org/wiki/ASCII))를 해당(1문자) 문자열로 변환
- `ord()`: (한 문자) 문자열을 해당 정수([문자 인코딩](https://ko.wikipedia.org/wiki/ASCII))로 변환

```Python
"""
변수형 변환 작업

Version: 1.0
Author: 骆昊
"""
a = 100
b = 123.45
c = '123'
d = '100'
e = '123.45'
f = 'hello, world'
g = True
print(float(a))         # 100    -> 100.0
print(int(b))           # 123.45 -> 123
print(int(c))           # '123' -> 123
print(int(c, base=16))  # '123' -> 291
print(int(d, base=2))   # '100' -> 4
print(float(e))         # '123.45' -> 123.45
print(bool(f))          # 'hello, world' -> True
print(int(g))           # True -> 1
print(chr(a))           # 100 -> 'd'
print(ord('d'))         # 'd' -> 100
```
