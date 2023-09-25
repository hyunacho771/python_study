# Session 2

## 실행 흐름 제어

1. for문

for 문의 기본 구조:

```python
for 변수 in 리스트(또는 튜플, 문자열)
	수행할 문장1
	수행할 문장2

#example
test_list=['one', 'two', 'three']
for i in test_list:
	print(i)

#출력값
one
two
three
```

1. while 문

```python
while 조건문:
    수행할_문장1
    수행할_문장2
    수행할_문장3
```

조건문 안에가 false 가 될때까지 계속 반복

강제로 빠져나가고 싶을 때? ⇒ break 사용

while 문의 맨 처음으로 돌아가고 싶을 때: continue 사용

```python
a=0
while a<10:
	a=a+1
	if a%2==0: continue
	print(a)

#실행 결과
1
3
5
7
9
```

1. if 문

if문의 기본 구조:

```python
if 조건문:
	실행할 문장 1
	실행할 문장 2
else:
	실행할 문장 1
	실행할 문장 2
```

파이썬에서는 들여쓰기가 매우 중요!! 안 하면 오류 남

언제나 같은 깊이로 들여쓰기 해야 함

### 조건문이란

참과 거짓을 판단하는 문장

파이썬에서는 비교연산자와 관계연산자를 사용

관계연산자는 영어 그대로 사용함 and, or, not

in, not in 도 사용 가능

조건문에서 아무 일도 일어나고 싶지 않다면? pass를 사용

else if: 조건을 판단하는 부분이 두 개 이상일 때 사용

```python
pocket=['paper', 'cellphone']
card=True
if 'money' in pocket:
	print("택시")
elif card:
	print("택시")
else:
	print("걸어감")
```

개수에 제한 없이 사용할 수 있음

조건부 표현식: 변수 = 조건문이_참인_경우의_값 if 조건문 else 조건문이_거짓인_경우의_값 → 의 형태를 가지고있음

---

1. 함수

함수를 사용하는 이유: 반복되는 코드를 최소화하기 위해서!

함수의 구조:

```python
def 함수_이름(매개변수):
	수행할 문장 1
	수행할 문장 2
```

매개변수: 함수에 입력으로 전달된 값을 받는 인수

인수: 함수를 호출할 때 전달하는 입력값

1) 입력값이 없는 함수

```python
def say():
	return "hi"
```

2) 리턴값이 없는 함수

```python
def add(a, b):
	printf("%d, %d의 합은 %d 입니다.", %(a, b, a+b))
```

3) 둘 다 없는 함수

```python
def say():
	printf("Hi")
```

입력값이 몇 개인지 모를 때는??

```python
def 함수_이름(*매개변수):
	수행할_문장

#예시
def add(*args):
	result=0
	for i in args:
			result=result+i
	return result
```

키워드 매개변수

dict 형태로 packing 하여 인수를 받아옴

```python
#예시
def print_kwargs(**kwargs):
	print(kwargs)

print_kwargs(name='foo', age=3)
{'age': 3, 'name': 'foo'}
```

함수의 리턴값은 언제나 하나!!!

함수 안에서 선언한 변수의 효력 범위: 함수 안에서만 적용

만약 밖에서 쓰고 싶을 때는?

1) return 사용

2) global 명령어 사용

lambda 예약어: def와 동일한 역할

```python
add = lambda a, b: a+b
print(add(1, 3)) => 4
```