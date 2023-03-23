---
layout: single
title:  "점프투파이썬 4장까지"
categories: coding
tag: [python, blog, jekyll]
toc: true
author_profile: false
---

<head>
  <style>
    table.dataframe {
      white-space: normal;
      width: 100%;
      height: 240px;
      display: block;
      overflow: auto;
      font-family: Arial, sans-serif;
      font-size: 0.9rem;
      line-height: 20px;
      text-align: center;
      border: 0px !important;
    }

    table.dataframe th {
      text-align: center;
      font-weight: bold;
      padding: 8px;
    }

    table.dataframe td {
      text-align: center;
      padding: 8px;
    }

    table.dataframe tr:hover {
      background: #b8d1f3; 
    }

    .output_prompt {
      overflow: auto;
      font-size: 0.9rem;
      line-height: 1.45;
      border-radius: 0.3rem;
      -webkit-overflow-scrolling: touch;
      padding: 0.8rem;
      margin-top: 0;
      margin-bottom: 15px;
      font: 1rem Consolas, "Liberation Mono", Menlo, Courier, monospace;
      color: $code-text-color;
      border: solid 1px $border-color;
      border-radius: 0.3rem;
      word-break: normal;
      white-space: pre;
    }

  .dataframe tbody tr th:only-of-type {
      vertical-align: middle;
  }

  .dataframe tbody tr th {
      vertical-align: top;
  }

  .dataframe thead th {
      text-align: center !important;
      padding: 8px;
  }

  .page__content p {
      margin: 0 0 0px !important;
  }

  .page__content p > strong {
    font-size: 0.8rem !important;
  }

  </style>
</head>



```python
#주피터 단축키 
# esc + m : Markdown
# esc + y : Code
```

# 2장. 파이썬 프로그래밍의 기초, 자료형


## 2-1 숫자형


### 숫자형은 어떻게 만들고 사용할까?


#### (1) 정수형



```python
a = 123
```


```python
a = -178
```


```python
a = 0
```

#### (2) 실수형


##### 일반적인 실수형의 소수점 표현 방식



```python
a= 1.2
```


```python
a = -3.45
```

##### 컴퓨터식 지수 표현 방식(E, e)



```python
# E나 e 중 어느 것을 사용해도 무방
a = 4.24E10
a
```

<pre>
42400000000.0
</pre>

```python
a= 4.24e-10
a
```

<pre>
4.24e-10
</pre>
- 실수형의 소수점 표현 방식



```python
# e와 E 중 어느 것을 사용해도 무방
a = 4.24E10 
b = 4.24e-10
print(a) # 4.24 * 3
print(b)
```

<pre>
42400000000.0
4.24e-10
</pre>

```python
a= 1
print(a)
```

<pre>
1
</pre>
#### (3) 8진수와 16진수



```python
#https://itbeginner2020.tistory.com/17
#8진수 : 0o 또는 0O로 시작
a = 0o177
print(a)
```

<pre>
127
</pre>

```python
#16진수 : 0x로 시작
#a,b,c,d,e,f 는 각각 10,11,12,13,14,15에 해당
a = 0x8ff
print(a)
```

<pre>
2303
</pre>
### 숫자형을 활용하기 위한 연산자


#### (1) 사칙연산



```python
a=3
```


```python
b=4
```


```python
a+b
```

<pre>
7
</pre>

```python
a*b
```

<pre>
12
</pre>

```python
a/b
```

<pre>
0.75
</pre>
#### (2) ** 연산자(제곱)



```python
a = 3
b = 4
a ** b
```

<pre>
81
</pre>
#### (3) % 연산자(나머지 반환)



```python
7%3
```

<pre>
1
</pre>
#### (4) // 연산자(몫 반환)



```python
7/4
7//4
```

<pre>
1
</pre>
- 퀴즈



```python
#14/3 몫, 나머지
print(14//3)
print(14%3)
```

<pre>
4
2
</pre>
## 2-2 문자열 자료형


### 문자열은 어떻게 만들고 사용할까?


#### 1. 큰 따옴표(")로 양쪽 둘러싸기



```python
print("Hello World")
```

<pre>
Hello World
</pre>
#### 2. 작은따옴표(")로 양쪽 둘러싸기



```python
print('Python is fun')
```

<pre>
Python is fun
</pre>
#### 3. 큰따옴표 3개를 연속(""")으로 양쪽



```python
print("""
Life is too short,
You need python
""")
```

<pre>

Life is too short,
You nee python

</pre>
#### 4. 작은따옴표 3개를 연속(''')으로 양쪽



```python
print('''
Life is too short,
You need python
''')
```

<pre>

Life is too short,
You need python

</pre>
### 문자열 안에 작은다옴표나 큰따옴표 포함시키기


#### 1. 문자열에 작은따옴표(') 포함시키기



```python
#큰따옴표로 둘러싼다.
food = "Python's favorite food is perl"
food
```

<pre>
"Python's favorite food is perl"
</pre>

```python
#작은따옴표가 포함된 문자열을 작은따옴표로 둘러싼 경우 -> 오류발생
food = 'Python's favorite food is perl'
```

#### 2. 문자열에 큰따옴표(") 포함시키기



```python
# 작은따옴표로 둘러싼다.
say = '"Python is very easy." he says.'
say
```

<pre>
'"Python is very easy." he says.'
</pre>
#### 3. 백슬래시\를 사용해 작은따옴표와 큰따옴표를 문자열에 포함시키기




```python
food = 'Python\'s favorite food is perl'
print(food)
say = "\"Python is very easy.\" he says."
print(say)
```

<pre>
Python's favorite food is perl
"Python is very easy." he says.
</pre>
### 여러 줄인 문자열을 변수에 대입


#### 1. 줄을 바꾸는 이스케이프 코드'\n' 삽입



```python
multiline = "Life is too short\nYou need python"
```

#### 2. 연속된 작은따옴표 3개(''') 또는 큰따옴표 3개(""") 사용



```python
#작은 따옴표 3개
multiline = '''
Life is too short
you need python
'''
print(multiline)
```

<pre>

Life is too short
you need python

</pre>

```python
#큰따옴표 3개
multiline = """
Life is too short
You need python
"""
print(multiline)
```

<pre>

Life is too short
You need python

</pre>
### 문자열 연산하기


#### 1. 문자열 더해서 연결(Concatenation)



```python
head = "Python"
tail = " is fun!"
head + tail
```

<pre>
'Python is fun!'
</pre>
#### 2. 문자열 곱하기



```python
a = "python"
a*2
```

<pre>
'pythonpython'
</pre>
#### 3. 문자열 길이 구하기(len)



```python
a = "Life is too short"
len(a)
```

<pre>
17
</pre>
- 퀴즈



```python
a = 'You need python'
len(a)
```

<pre>
15
</pre>
### 문자열 인덱싱(Indexing)과 슬라이싱(Slicing)



```python
#~51
```

```

- 인덱싱(indexing) : 가리킨다

- 슬라이싱(slicing) : 잘라낸다

```


#### 문자열 인덱싱이란?



```python
a = "Life is too short, You need Python"
a[3]
```

<pre>
'e'
</pre>
#### 문자열 인덱싱 활용하기



```python
a = "Life is too short, You need Python"
a[0]
```

<pre>
'L'
</pre>

```python
a[12]
```

<pre>
's'
</pre>

```python
a[-1] # 맨 뒤부터 인덱싱은 -1부터 시작
```

<pre>
'n'
</pre>

```python
# a[-0]은 a[0]과 같다!
a[-0]
```

<pre>
'L'
</pre>

```python
a[-2]
```

<pre>
'o'
</pre>
#### 문자열 슬라이싱이란?



```python
a = "Life is too short, You need Python"
b = a[0] + a[1] + a[2] + a[3]
b
```

<pre>
'Life'
</pre>

```python
a = "Life is too short, You need Python"
a[0:4] #끝번호 포함안함
```

<pre>
'Life'
</pre>

```python
a[19:]
```

<pre>
'You need Python'
</pre>

```python
a[:17]
```

<pre>
'Life is too short'
</pre>

```python
a[:]
```

<pre>
'Life is too short, You need Python'
</pre>

```python
a[19:-7] #-8까지 출력
```

<pre>
'You need'
</pre>
#### 슬라이싱으로 문자열 나누기



```python
a = "20010331Rainy"
```


```python
date=a[:8]
```


```python
weather=a[8:]
```


```python
date
```

<pre>
'20010331'
</pre>

```python
weather
```

<pre>
'Rainy'
</pre>
- Pithon이라는 문자열을 Python으로 바꾸려면?



```python
a = "Pithon"
```


```python
a[1]
```

<pre>
'i'
</pre>

```python
a[1] = 'y'
#오류 발생 
#문자열의 요솟값은 바꿀 수 있는 값이 아니다.
#문자열 자료형은 immutable한 자료형
```


```python
a = "Pithon"
```


```python
a[:1]
```

<pre>
'P'
</pre>

```python
a[2:]
```

<pre>
'thon'
</pre>

```python
a[:1] + 'y' + a[2:]
```

<pre>
'Python'
</pre>
### 문자열 포매팅


#### 문자열 포매팅 따라하기


```1. 숫자 바로 대입```



```python
"I eat %d apples." % 3 
```

<pre>
'I eat 3 apples.'
</pre>
```2.문자열 바로 대입```



```python
"I eat %s apples." % "five"
#숫자는 %d, 문자열은 %s
```

<pre>
'I eat five apples.'
</pre>
```3. 숫자 값을 나타내는 변수로 대입```



```python
number = 3
```


```python
"I eat %d apples." % number
```

<pre>
'I eat 3 apples.'
</pre>
```4. 2개 이상의 값 넣기```



```python
number = 10
```


```python
day = "three"
```


```python
"I ate %d apples. so I was sick for %s days." %(number, day)
```

<pre>
'I ate 10 apples. so I was sick for three days.'
</pre>
- 문자열 포맷 코드



```python
"I have %s apples" % 3
```

<pre>
'I have 3 apples'
</pre>

```python
"rate is %s" % 3.324
#%s는 자동으로 % 뒤에 있는 값을 문자열로 바꾼다.
```

<pre>
'rate is 3.324'
</pre>
- 포매팅 연산자 %d와 %를 같이 쓸 때는 %%를 쓴다.



```python
"Error is %d%" % 98
```


```python
#%d와 %가 같은 문자열 안에 존재하는 경우, %를 나타내려면 반드시 %%로 써야 한다.
"Error is %d%%" % 98
```

<pre>
'Error is 98%'
</pre>
#### 포맷 코드와 숫자 함께 사용하기


```1. 정렬과 공백```



```python
"%10s" % "hi" 
# %10s는 전체 길이가 10개인 문자열 공간에서 대입되는 값을 오른쪽을 정렬하고 그 앞의 나머지는 공백으로 남겨두라는 의미.
#전체 길이 10개 = 왼쪽 공백 8개 + "hi" 문자열 길이 2개
```

<pre>
'        hi'
</pre>

```python
"%-10sjane" % 'hi' 
#hi가 왼쪽 정렬됨
```

<pre>
'hi        jane'
</pre>
```2. 소수점 표현하기```



```python
"%0.4f" % 3.42134234
#'.'의 의미는 소수점 포인트이고 그 뒤의 숫자 4는 소수점 뒤에 나올 숫자의 개수
```

<pre>
'3.4213'
</pre>

```python
"%10.4f" % 3.42134234
# 소수점 네 번째 자리까지만 표시하고 전체 길이가 10인 문자열 공간에서 오른쪽 정렬
```

<pre>
'    3.4213'
</pre>
#### format 함수를 사용한 포매팅


```숫자 바로 대입하기```



```python
"I eat {0} apples".format(3)
```

<pre>
'I eat 3 apples'
</pre>
```문자열 바로 대입하기```



```python
"I eat {0} apples".format("five")
```

<pre>
'I eat five apples'
</pre>
```숫자 값을 가진 변수로 대입하기```



```python
number = 3
```


```python
"I eat {0} apples".format(number)
```

<pre>
'I eat 3 apples'
</pre>
```2개 이상의 값 넣기```



```python
number = 10
```


```python
day = "three"
```


```python
"I ate {0} apples. so I was sick for {1} days".format(number, day)
```

<pre>
'I ate 10 apples. so I was sick for three days'
</pre>
```이름으로 넣기```



```python
"I ate {number} apples. so I was sick for {day} days.".format(number=10, day=3) 
```

<pre>
'I ate 10 apples. so I was sick for 3 days.'
</pre>
```인덱스와 이름을 혼용해서 넣기```



```python
"I ate {0} apples. so I was sick for {day} days.".format(10, day=3)
```

<pre>
'I ate 10 apples. so I was sick for 3 days.'
</pre>
```소수점 표현하기```



```python
y = 3.42134234
```


```python
"{0:0.4f}".format(y)
```

<pre>
'3.4213'
</pre>

```python
"{0:10.4f}".format(y)
```

<pre>
'    3.4213'
</pre>
```{또는} 문자 표현하기```



```python
"{{ and }}".format()
```

<pre>
'{ and }'
</pre>

```python
"{{ and }}".format()
```

<pre>
'{ and }'
</pre>
#### f 문자열 포매팅



```python
name = '홍길동'
```


```python
age = 30
```


```python
f'나의 이름은 {name}입니다. 나이는 {age}입니다.'
```

<pre>
'나의 이름은 홍길동입니다. 나이는 30입니다.'
</pre>

```python
age = 30
```


```python
f'나는 내년이면 {age+1}살이 된다.'
```

<pre>
'나는 내년이면 31살이 된다.'
</pre>

```python
d = {'name':'홍길동', 'age':30}
```


```python
f'나의 이름은 {d["name"]}입니다. 나이는 {d["age"]}입니다.'
```

<pre>
'나의 이름은 홍길동입니다. 나이는 30입니다.'
</pre>

```python
y = 3.42134234
```


```python
f'{y:0.4f}' #소수점 4자리까지만 표현
```

<pre>
'3.4213'
</pre>

```python
f'{y:10.4f}' #소수점 4자리까지 표현하고 총 자릿수를 10으로 맞춤
```

<pre>
'    3.4213'
</pre>

```python
f'{{ and }}'
```

<pre>
'{ and }'
</pre>
### 문자열 관련 함수

- 문자열 내장 함수 : 문자열 자료형이 자체적으로 가진 함수


- 사용법



```python
문자열변수이름.함수이름
```

#### 문자 개수 세기(count)



```python
a = "hobby"
```


```python
a.count('b')
```

<pre>
2
</pre>
문자열 중 문자 b의 개수를 돌려줌


#### 위치 알려주기1(find)



```python
a = "Python is the best choice"
a.find('b') # 문자열에서 b가 처음 나온 위치
```

<pre>
14
</pre>
문자열 중 문자 b가 처음으로 나온 위치 반환<br>



```python
a.find('k') 
```

<pre>
-1
</pre>
찾는 문자나 문자열이 존재하지 않는다면 -1 반환


#### 위치 알려주기2(index)



```python
a = "Life is too short"
```


```python
a.index('t') 
```

<pre>
8
</pre>
문자열 중 t가 맨 처음으로 나온 위치 반환



```python
a.index('k') 
```

찾는 문자나 문자열이 존재하지 않는다면 오류 발생 -> 앞의 find 함수와 다른 점


#### 문자열 삽입(join)

- '구분자'.join(리스트)

- join  함수는 문자열뿐만 아니라 리스트나 튜플도 입력으로 사용 가능



```python
",".join('abcd')
```

<pre>
'a,b,c,d'
</pre>
abcd 문자열의 각각의 문자  사이에 ','를 삽입<br>


- join 함수의 입력으로 리스트 사용하기



```python
",".join(['a','b','c','d'])
```

<pre>
'a,b,c,d'
</pre>

```python
" ".join(['park','800905-1049118','kim','700905-1059119'])
```

<pre>
'park 800905-1049118 kim 700905-1059119'
</pre>
#### 소문자를 대문자로 바꾸기(upper)



```python
a = "hi"
```


```python
a.upper()
```

<pre>
'HI'
</pre>
#### 대문자를 소문자로 바꾸기(lower)



```python
a = "HI"
```


```python
a.lower()
```

<pre>
'hi'
</pre>
#### 왼쪽 공백 지우기(lstrip)



```python
a = " hi"
```


```python
a.lstrip()
```

<pre>
'hi'
</pre>
#### 오른족 공백 지우기(rstrip)



```python
a = "hi "
```


```python
a.rstrip()
```

<pre>
'hi'
</pre>
#### 양쪽 공백 지우기(strip)



```python
a = " hi "
```


```python
a.strip()
```

<pre>
'hi'
</pre>
#### 문자열 바꾸기(replace)


- 형식



```python
replace(바뀌게 될 문자열, 바꿀 문자열)
```


```python
a = "Life is too short"
```


```python
a.replace("Life", "Your leg")
```

<pre>
'Your leg is too short'
</pre>
#### 문자열 나누기(split)

- a.split()처럼 괄호 안에 아무 값도 넣어 주지 않은 경우 : 공백(스페이스, 탭, 엔터 등)을 기준으로 문자열을 나누어 줌

- b.split(':')처럼 괄호 안에 특정 값이 있을 경우 : 괄호 안의 값을 구분자로 해서 문자열을 나누어 줌

- 이렇게 나눈 값은 리스트에 하나씩 들어감



```python
a = "Life is too short"
```


```python
a.split() # 괄호 안에 아무 값도 넣어주지 않으면 공백을 기준으로 문자열 나눔
```

<pre>
['Life', 'is', 'too', 'short']
</pre>

```python
b = "a:b:c:d"
```


```python
b.split(':') # :기호를 기준으로 문자열 나눔
```

<pre>
['a', 'b', 'c', 'd']
</pre>
## 3/9 추가학습


### 변수 타입 구하기



```python
a = 1
type(a)
```

<pre>
int
</pre>
### sqrt(제곱근) 함수



```python
import math
```


```python
math.sqrt(4)
```

<pre>
2.0
</pre>

```python
pi
```


```python
math.pi
```

<pre>
3.141592653589793
</pre>

```python
import numpy as np
```


```python
pip install numpy
```

<pre>
Requirement already satisfied: numpy in c:\users\user\appdata\local\programs\python\python310\lib\site-packages (1.24.2)
Note: you may need to restart the kernel to use updated packages.
</pre>

```python
np.sqrt(4)
```

<pre>
2.0
</pre>

```python
np.pi
```

<pre>
3.141592653589793
</pre>

```python
np.cos(0)
```

<pre>
1.0
</pre>

```python
np.cos(2*np.pi)
```

<pre>
1.0
</pre>

```python
math.factorial(10)
```

<pre>
3628800
</pre>
### linspace



```python
np.linspace?
```

<pre>
[1;31mSignature:[0m
[0mnp[0m[1;33m.[0m[0mlinspace[0m[1;33m([0m[1;33m
[0m    [0mstart[0m[1;33m,[0m[1;33m
[0m    [0mstop[0m[1;33m,[0m[1;33m
[0m    [0mnum[0m[1;33m=[0m[1;36m50[0m[1;33m,[0m[1;33m
[0m    [0mendpoint[0m[1;33m=[0m[1;32mTrue[0m[1;33m,[0m[1;33m
[0m    [0mretstep[0m[1;33m=[0m[1;32mFalse[0m[1;33m,[0m[1;33m
[0m    [0mdtype[0m[1;33m=[0m[1;32mNone[0m[1;33m,[0m[1;33m
[0m    [0maxis[0m[1;33m=[0m[1;36m0[0m[1;33m,[0m[1;33m
[0m[1;33m)[0m[1;33m[0m[1;33m[0m[0m
[1;31mDocstring:[0m
Return evenly spaced numbers over a specified interval.

Returns `num` evenly spaced samples, calculated over the
interval [`start`, `stop`].

The endpoint of the interval can optionally be excluded.

.. versionchanged:: 1.16.0
    Non-scalar `start` and `stop` are now supported.

.. versionchanged:: 1.20.0
    Values are rounded towards ``-inf`` instead of ``0`` when an
    integer ``dtype`` is specified. The old behavior can
    still be obtained with ``np.linspace(start, stop, num).astype(int)``

Parameters
----------
start : array_like
    The starting value of the sequence.
stop : array_like
    The end value of the sequence, unless `endpoint` is set to False.
    In that case, the sequence consists of all but the last of ``num + 1``
    evenly spaced samples, so that `stop` is excluded.  Note that the step
    size changes when `endpoint` is False.
num : int, optional
    Number of samples to generate. Default is 50. Must be non-negative.
endpoint : bool, optional
    If True, `stop` is the last sample. Otherwise, it is not included.
    Default is True.
retstep : bool, optional
    If True, return (`samples`, `step`), where `step` is the spacing
    between samples.
dtype : dtype, optional
    The type of the output array.  If `dtype` is not given, the data type
    is inferred from `start` and `stop`. The inferred dtype will never be
    an integer; `float` is chosen even if the arguments would produce an
    array of integers.

    .. versionadded:: 1.9.0

axis : int, optional
    The axis in the result to store the samples.  Relevant only if start
    or stop are array-like.  By default (0), the samples will be along a
    new axis inserted at the beginning. Use -1 to get an axis at the end.

    .. versionadded:: 1.16.0

Returns
-------
samples : ndarray
    There are `num` equally spaced samples in the closed interval
    ``[start, stop]`` or the half-open interval ``[start, stop)``
    (depending on whether `endpoint` is True or False).
step : float, optional
    Only returned if `retstep` is True

    Size of spacing between samples.


See Also
--------
arange : Similar to `linspace`, but uses a step size (instead of the
         number of samples).
geomspace : Similar to `linspace`, but with numbers spaced evenly on a log
            scale (a geometric progression).
logspace : Similar to `geomspace`, but with the end points specified as
           logarithms.
:ref:`how-to-partition`

Examples
--------
>>> np.linspace(2.0, 3.0, num=5)
array([2.  , 2.25, 2.5 , 2.75, 3.  ])
>>> np.linspace(2.0, 3.0, num=5, endpoint=False)
array([2. ,  2.2,  2.4,  2.6,  2.8])
>>> np.linspace(2.0, 3.0, num=5, retstep=True)
(array([2.  ,  2.25,  2.5 ,  2.75,  3.  ]), 0.25)

Graphical illustration:

>>> import matplotlib.pyplot as plt
>>> N = 8
>>> y = np.zeros(N)
>>> x1 = np.linspace(0, 10, N, endpoint=True)
>>> x2 = np.linspace(0, 10, N, endpoint=False)
>>> plt.plot(x1, y, 'o')
[<matplotlib.lines.Line2D object at 0x...>]
>>> plt.plot(x2, y + 0.5, 'o')
[<matplotlib.lines.Line2D object at 0x...>]
>>> plt.ylim([-0.5, 1])
(-0.5, 1)
>>> plt.show()
[1;31mFile:[0m      c:\users\user\appdata\local\programs\python\python310\lib\site-packages\numpy\core\function_base.py
[1;31mType:[0m      function
</pre>

```python
np.linspace(1,10,10) #(배열의 시작값, 배열의 끝값, 몇개의 일정한 간격으로 만들것인가)
```

<pre>
array([ 1.,  2.,  3.,  4.,  5.,  6.,  7.,  8.,  9., 10.])
</pre>

```python
import numpy
import numpy as np
from numpy import sqrt
from numpy import *
```

### 반올림, 버림, 내림



```python
round(3.4567,2) #지정한 자릿수로 반올림
```

<pre>
3.46
</pre>

```python
np.floor(3.4567) #버림
```

<pre>
3.0
</pre>

```python
np.ceil(3.4567) #올림
```

<pre>
4.0
</pre>
### input() 함수



```python
input()
```

<pre>
 1
</pre>
<pre>
'1'
</pre>

```python
input("숫자를 입력하세요: ")
```

<pre>
숫자를 입력하세요:  3
</pre>
<pre>
'3'
</pre>

```python
name = input("숫자를 입력하세요: ")
age = input("나이를 입력하세요: ")
```

<pre>
숫자를 입력하세요:  35
나이를 입력하세요:  57
</pre>

```python
a = input("숫자를 입력하세요: ")
b = input("숫자를 입력하세요: ")
a = int(a)
b = int(b)
a+b
```

<pre>
숫자를 입력하세요:  3
숫자를 입력하세요:  6
</pre>
<pre>
9
</pre>

```python
a = int(input("숫자를 입력하세요: "))
b = int(input("숫자를 입력하세요: "))
a+b
```

<pre>
숫자를 입력하세요:  30
숫자를 입력하세요:  50
</pre>
<pre>
80
</pre>

```python
#입력받은 숫자를 2배해서 출력
a = int(input("숫자를 입력하세요: "))
a*2
```

<pre>
숫자를 입력하세요:  6
</pre>
<pre>
12
</pre>

```python
#name, age 변수에 값을 받아서

"나의 이름은 000이고 나이는 00살입니다."
name = str(input("이름을 입력하세요: "))
age = int(input("나이를 입력하세요: "))

print(f"나의 이름은 {name}이고 나이는 {age}살입니다.")
```

<pre>
이름을 입력하세요:  잰
나이를 입력하세요:  20
</pre>
<pre>
나의 이름은 잰이고 나이는 20살입니다.
</pre>

```python
age1 = int(input("어머니의 나이를 입력하세요: "))
age2 = int(input("나의 나이를 입력하세요: "))
age_total = age1 + age2
print(f"어머니의 나이는 {age1}살이고 나의 나이는 {age2}살이고, 합은 {age_total}살입니다.")
```

<pre>
어머니의 나이를 입력하세요:  50
나의 나이를 입력하세요:  24
</pre>
<pre>
어머니의 나이는 50살이고 나의 나이는 24살이고, 합은 74살입니다.
</pre>

```python
pi = 3.141592

print(f"pi값은 {pi:0.4f}입니다")
print(f"pi값은 {pi:10.4f}입니다")
```

<pre>
pi값은 3.1416입니다
pi값은     3.1416입니다
</pre>
- 3월 10일 복습


## 2-3 리스트 자료형


### 리스트는 어떻게 만들고 사용할까?



```python
a = []
```


```python
b = [1,2,3]
```


```python
c = ['Life', 'is', 'too', 'short']
```


```python
d = [1, 2, 'Life', 'is']
```


```python
e = [1,2,['Life', 'is']]
```

### 리스트의 인덱싱과 슬라이싱


#### 리스트의 인덱싱



```python
a = [1,2,3]
```


```python
a
```

<pre>
[1, 2, 3]
</pre>

```python
a[0]
```

<pre>
1
</pre>

```python
a[0] + a[2]
```

<pre>
4
</pre>

```python
a[-1]
```

<pre>
3
</pre>

```python
a = [1,2,3,['a','b','c']]
```


```python
a[0]
```

<pre>
1
</pre>

```python
a[-1]
```

<pre>
['a', 'b', 'c']
</pre>

```python
a[3]
```

<pre>
['a', 'b', 'c']
</pre>

```python
a[-1][0]
```

<pre>
'a'
</pre>

```python
a[-1][1]
```

<pre>
'b'
</pre>

```python
a[-1][2]
```

<pre>
'c'
</pre>
#### 삼중 리스트에서 인덱싱하기



```python
a = [1,2,['a','b',['Life','is']]]
```


```python
a[2][2][0]
```

<pre>
'Life'
</pre>
#### 리스트의 슬라이싱



```python
a = [1,2,3,4,5]
```


```python
a[0:2]
```

<pre>
[1, 2]
</pre>

```python
a = "12345"
```


```python
a[0:2]
```

<pre>
'12'
</pre>

```python
a=[1,2,3,4,5]
```


```python
b=a[:2]
```


```python
c=a[2:]
```


```python
b
```

<pre>
[1, 2]
</pre>

```python
c
```

<pre>
[3, 4, 5]
</pre>
- 퀴즈



```python
A = [1,2,3,4,5]
```


```python
A[1:3]
```

<pre>
[2, 3]
</pre>
#### 중첩된 리스트에서 슬라이싱



```python
a = [1,2,3,['a','b','c'],4,5]
```


```python
a[2:5]
```

<pre>
[3, ['a', 'b', 'c'], 4]
</pre>

```python
a[3][:2]
```

<pre>
['a', 'b']
</pre>
### 리스트 연산하기


#### 1. 리스트 더하기(+)



```python
a = [1,2,3]
```


```python
b = [4,5,6]
```


```python
a + b
```

<pre>
[1, 2, 3, 4, 5, 6]
</pre>
#### 2. 리스트 반복하기(*)



```python
a = [1,2,3]
```


```python
a*3
```

<pre>
[1, 2, 3, 1, 2, 3, 1, 2, 3]
</pre>
#### 3. 리스트 길이 구하기



```python
a = [1,2,3]
```


```python
len(a)
```

<pre>
3
</pre>
#### 초보자가 실수하기 쉬운 리스트 연산 오류



```python
a = [1,2,3]
a[2] + "hi"
#형 오류(TypeError) 발생
#a[2]에 저장된 값은 3이라는 정수인데 "hi"는 문자열이다. 정수와 문자열은 서로 더할 수 없기 때문에 형 오류 발생
```


```python
str(a[2]) + "hi"
```

<pre>
'3hi'
</pre>
### 리스트의 수정과 삭제


#### 리스트에서 값 수정



```python
a = [1,2,3]
```


```python
a[2] = 4
```


```python
a
```

<pre>
[1, 2, 4]
</pre>
#### 리스트 요소 삭제(del 함수)



```python
a = [1,2,3]
```


```python
del a[1]
```


```python
a
```

<pre>
[1, 3]
</pre>

```python
a = [1,2,3,4,5]
```


```python
del a[2:]
```


```python
a
```

<pre>
[1, 2]
</pre>
### 리스트 관련 함수


#### 리스트에 요소 추가(append)

- 리스트의 맨 마지막에 x 추가



```python
a = [1,2,3]
```


```python
a.append(4) # 리스트의 맨 마지막에 4 추가
```


```python
a
```

<pre>
[1, 2, 3, 4]
</pre>
- 리스트에 리스트 추가



```python
a.append([5,6]) # 리스트의 맨 마지막에 [5,6] 추가
```


```python
a
```

<pre>
[1, 2, 3, 4, [5, 6]]
</pre>
#### 리스트 정렬(sort)

- 리스트의 요소를 순서대로 정렬



```python
a = [1,4,3,2]
```


```python
a.sort()
```


```python
a
```

<pre>
[1, 2, 3, 4]
</pre>

```python
a = ['a','c','b']
```


```python
a.sort()
```


```python
a
```

<pre>
['a', 'b', 'c']
</pre>
#### 리스트 뒤집기(reverse)

- 리스트를 역순으로 뒤집는다.

- 리스트 요소들을 순서대로 정렬한 다음 다시 역순으로 정렬하는 것이 아니라<br>

그저 현재의 리스트를 그대로 거꾸로 뒤집는다.



```python
a = ['a','c','b']
```


```python
a.reverse()
```


```python
a
# 계속 뒤집기 가능
```

<pre>
['b', 'c', 'a']
</pre>
#### 위치 반환(index)

- index(x) 함수는 리스트에 x 값이 있으면 x의 위치 값을 돌려줌



```python
a = [1,2,3]
```


```python
a.index(3) #3은 리스트 a의 세 번째(a[2])요소
```

<pre>
2
</pre>

```python
a.index(1) #1은 리스트 a의 첫 번째(a[0])요소
```

<pre>
0
</pre>

```python
a.index(0)
#값 0은 a 리스트에 존재하지 않기 때문에 값 오류(ValueError) 발생
```

#### 리스트에 요소 삽입(insert)

- insert(a,b)는 a번째 위치에 b를 삽입



```python
a = [1,2,3]
```

- 0번째 자리, 즉 첫 번째 요소(a[0]) 위치에 값 4 삽입



```python
a.insert(0,4) 
```


```python
a
```

<pre>
[4, 1, 2, 3]
</pre>
- 4번째 자리, 즉 세 번째 요소(a[3]) 자리에 값 5 삽입



```python
a.insert(3, 5)
```


```python
a
```

<pre>
[4, 1, 2, 5, 3]
</pre>
#### 리스트 요소 제거(remove)

- remove(x)는 리스트에서 첫 번째로 나오는 x를 삭제



```python
a = [1,2,3,1,2,3]
```


```python
a.remove(3)
a
```

<pre>
[1, 2, 1, 2, 3]
</pre>
a가 3이라는 값을 2개 가지고 있을 경우 첫 번째 3만 제거



```python
a.remove(3)
a
```

<pre>
[1, 2, 1, 2]
</pre>
remove(3)을 한 번 더 실행하면 다시 3이 삭제


#### 리스트 요소 끄집어내기(pop)

- pop()은 리스트의 맨 마지막 요소를 돌려주고 그 요소는 삭제



```python
a = [1,2,3]
a.pop()
```

<pre>
3
</pre>

```python
a
```

<pre>
[1, 2]
</pre>
a 리스트 [1,2,3]에서 3을 끄집어내고 최종적으로 [1,2]만 남음



```python
a= [1,2,3]
a.pop(1)
```

<pre>
2
</pre>
- pop(x)는 리스트의 x번재 요소를 돌려주고 그 요소는 삭제



```python
a
```

<pre>
[1, 3]
</pre>
a.pop(1)은 a[1]의 값을 끄집어낸다. 다시 a를 출력하면 끄집어낸 값이 삭제된 것을 확인 가능


#### 리스트에 포함된 요소 x의 개수 세기(count)

- count(x)는 리스트 안에 x가 몇 개 있는지 조사해 그 개수를 돌려줌



```python
a = [1,2,3,1]
```


```python
a.count(1)
```

<pre>
2
</pre>
1이라는 값이 리스트 a에 2개 들어 있으므로 2를 돌려줌


#### 리스트 확장(extend)

- extend(x)에서 x에는 리스트만 올 수 있으며 원래의 a 리스트에 x리스트를 더하게 된다.

- a.extend([4,5])는 a += [4,5]와 동일하다.



```python
a = [1,2,3]
```


```python
a.extend([4,5])
```


```python
a
```

<pre>
[1, 2, 3, 4, 5]
</pre>

```python
b = [6,7]
```


```python
a.extend(b)
```


```python
a
```

<pre>
[1, 2, 3, 4, 5, 6, 7]
</pre>
## 2-4 튜플 자료형

튜플(tuple)은 몇 가지 점을 제외하곤 리스트와 거의 비슷하며 리스트와 다른 점은 다음과 같다.

- 리스트는 []로 둘러싸지만 튜플은 ()로 둘러싼다.

- 리스트는 그 값의 생성, 삭제, 수정이 가능하지만 튜플은 그 값을 바꿀 수 없다.




```python
t1 = ()
```


```python
t2 = (1,) # 단지 한 개의 요소만을 가질 대는 요소 뒤에 콤마(,)를 반드시 붙여야 한다.
```


```python
t3 = (1,2,3)
```


```python
t4 = 1,2,3 # 괄호를 생략해도 무방
```


```python
t5 = ('a', 'b', ('ab', 'cd'))
```

### 튜플의 요솟값을 지우거나 변경하려고 하면 어떻게 될까?


#### 1. 튜플 요솟값을 삭제하려 할 때



```python
t1 = (1,2,'a','b')
del t1[10] # 형 오류(Type Error) 발생
```

#### 2. 튜플 요솟값을 변경하려 할 때



```python
t1 = (1,2,'a','b')
```


```python
t1[0] = 'c' # 형 오류 발생
```

### 튜플 다루기


#### 1. 인덱싱하기



```python
t1 = (1,2,'a','b')
```


```python
t1[0]
```

<pre>
1
</pre>

```python
t1[3]
```

<pre>
'b'
</pre>
#### 2. 슬라이싱하기



```python
t1 = (1,2,'a','b')
```


```python
t1[1:]
```

<pre>
(2, 'a', 'b')
</pre>
#### 3. 튜플 더하기



```python
t2 = (3,4)
```


```python
t1 + t2
```

<pre>
(1, 2, 'a', 'b', 3, 4)
</pre>
#### 4. 튜플 곱하기



```python
t2 * 3
```

<pre>
(3, 4, 3, 4, 3, 4)
</pre>
#### 5. 튜플 길이 구하기



```python
t1  =(1,2,'a','b')
```


```python
len(t1)
```

<pre>
4
</pre>
- 문제



```python
(1,2,3) + (4,)
```

<pre>
(1, 2, 3, 4)
</pre>
## 2-5 딕셔너리 자료형


### 딕셔너리는 어떻게 만들까?

- Key에는 변하지 않는 값을 사용하고, Value에는 변하는 값과 변하지 않는 값 모두 사용 가능



```python
dic = {'name':'pey', 'phone':'0119993323', 'birth':'1118'}
```


```python
a = {1:'hi'}
```


```python
a = {'a':[1,2,3]} # value에 리스트도 넣을 수 있다.
```

### 딕셔너리 쌍 추가, 삭제하기


#### 1. 딕셔너리 쌍 추가하기



```python
a = {1:'a'}
```


```python
a[2] = 'b'
```


```python
a
```

<pre>
{1: 'a', 2: 'b'}
</pre>

```python
a['name'] = 'pey'
```


```python
a
```

<pre>
{1: 'a', 2: 'b', 'name': 'pey'}
</pre>

```python
a[3] = [1,2,3]
```


```python
a
```

<pre>
{1: 'a', 2: 'b', 'name': 'pey', 3: [1, 2, 3]}
</pre>
#### 2. 딕셔너리 요소 삭제하기



```python
del a[1] #key가 1인 key:value 쌍 삭제
```


```python
a
```

<pre>
{2: 'b', 'name': 'pey', 3: [1, 2, 3]}
</pre>
### 딕셔너리를 사용하는 방법


#### 딕셔너리에서 Key 사용해 Value 얻기



```python
grade = {'pey':10, 'juliet':99}
```


```python
grade['pey']
```

<pre>
10
</pre>

```python
grade['juliet']
```

<pre>
99
</pre>

```python
a = {1:'a', 2:'b'}
```


```python
a[1]
```

<pre>
'a'
</pre>

```python
a[2]
```

<pre>
'b'
</pre>

```python
a={'a':1, 'b':2}
```


```python
a['a']
```

<pre>
1
</pre>

```python
a['b']
```

<pre>
2
</pre>

```python
dic = {'name':'pey', 'phone':'0119993323', 'birth':'1118'}
```


```python
dic['name']
```

<pre>
'pey'
</pre>

```python
dic['phone']
```

<pre>
'0119993323'
</pre>

```python
dic['birth']
```

<pre>
'1118'
</pre>
#### 딕셔너리 만들 때 주의할 사항



```python
a = {1:'a', 1:'b'}
a
```

<pre>
{1: 'b'}
</pre>

```python
a = {[1,2]:'hi'}
```

### 딕셔너리 관련 함수


#### Key 리스트 만들기(keys)



```python
a = {'name':'pey', 'phone':'0119993323', 'birth':'1118'}
```


```python
a.keys()
```

<pre>
dict_keys(['name', 'phone', 'birth'])
</pre>
a.keys()는 딕셔너리 a의 Key만을 모아서 dict_keys 객체를 돌려줌



```python
for k in a.keys():
    print(k)
```

<pre>
name
phone
birth
</pre>
dict_keys 객체는 위와 같이 사용<br>

리스트를 사용하는 것과 차이가 없지만, 리스트 고유의 append, insert, pop, remove, sort 함수 수행 불가


- dict_keys 객체를 리스트로 변환하기



```python
list(a.keys())
```

<pre>
['name', 'phone', 'birth']
</pre>
***파이썬 3.0 이후 버전의 keys 함수, 어떻게 달라졌나?***<br>

<hr>

파이썬2.7 버전까지는 a.keys() 함수 호출 시 반환 값으로 dick_keys가 아닌 ***리스트***를 돌려줌<br>

리스트를 돌려주기 위해서는 메모리 낭비가 발생<br>

파이썬 3.0 이후 버전에서는 이러한 메모리 낭비를 줄이기 위해 dict_keys 객체를 돌려줌<br>

다음에 소개할 dict_values, dict_items 역시 파이썬 3.0 이후 버전에서 추가된 것들<br>

만약 3.0 이후 버전에서 반환 값으로 리스트가 필요한 경우 'list(a.keys())' 사용<br>

dict_keys,dict_values, dict_items 등은 리스트로 변환하지 않더라도 기본적인 반복(iterate) 구문(예:for문) 실행 가능


#### Value 리스트 만들기(values)



```python
a.values()
```

<pre>
dict_values(['pey', '0119993323', '1118'])
</pre>
Key를 얻는 것과 마찬가지 방법으로 Value만 얻고 싶다면 value 함수 사용<br>

values 함수를 호출하면 dict_values 객체를 돌려줌


#### Key, Value 쌍 얻기(items)



```python
a.items()
```

<pre>
dict_items([('name', 'pey'), ('phone', '0119993323'), ('birth', '1118')])
</pre>
items 함수는 Key와 Value의 쌍을 튜플로 묶은 값을 dict_items 객체로 돌려줌


#### Key:Value 쌍 모두 지우기(clear)

- clear 함수는 딕셔너리 안의 모든 요소 삭제 <br>

- 빈 리스트를 [], 빈 튜플을 ()로 표현하는 것과 마찬가지로 빈 딕셔너리도 {}로 표현

- 빈 딕셔너리는 a = dict()로 생성 가능



```python
a.clear()
```


```python
a
```

<pre>
{}
</pre>

```python
a = dict()
```


```python
a
```

<pre>
{}
</pre>
#### Key로 Value 얻기(get)

- get(x) 함수는 x라는 Key에 대응되는 Value를 돌려줌<br>

- get('name')과 a['name']은 동일한 결과값을 가짐



```python
a = {'name':'pey', 'phone':'0119993323', 'birth':'1118'}
```


```python
a.get('name')
```

<pre>
'pey'
</pre>

```python
a['name']
```

<pre>
'pey'
</pre>

```python
a.get('phone')
```

<pre>
'0119993323'
</pre>
***a.get('nokey')와 a['nokey']의 차이***

- ***a.get('nokey')*** : None을 돌려줌

- ***a['nokey']*** : Key 오류 발생




```python
print(a.get('nokey'))
```

<pre>
None
</pre>

```python
print(a['nokey'])
```

- ***get(x,'디폴트 값')*** : 찾으려는 key 값이 없을 경우 미리 정해 둔 디폴트 값 대신 가져오기



```python
a.get('foo', 'bar')
```

<pre>
'bar'
</pre>
#### 해당 Key가 딕셔너리 안에 있는지 조사하기(in)



```python
a = {'name':'pey', 'phone':'0119993323', 'birth':'1118'}
```


```python
'name' in a
```

<pre>
True
</pre>

```python
'email' in a
```

<pre>
False
</pre>

```python
'name' 문자열은 a 딕셔너리의 Key 중 하나
따라서 'name' in a를 호출하면 참(True)를 돌려줌
반대로 'email'은 a 딕셔너리 안에 존재하지 않는 Key이므로 거짓(False)를 돌려줌
```

- 나혼자코딩



```python
a = {'name':'홍길동', 'birth':1128, 'age':30}
```

## 2-6 집합 자료형


### 집합 자료형은 어떻게 만들까?



```python
s1 = set([1,2,3])
```


```python
s1
```

<pre>
{1, 2, 3}
</pre>

```python
s2 = set("Hello")
```


```python
s2
```

<pre>
{'H', 'e', 'l', 'o'}
</pre>

```python
#비어 있는 집합 자료형
s = set()
```


```python
s
```

<pre>
set()
</pre>
### 집합 자료형의 특징

- 중복 허용 X

- 순서가 없다

- 인덱싱 지원 X



```python
# set 자료형에 저장된 값을 인덱싱으로 접근하려면 리스트나 튜플로 변환 후 해야한다.
s1 = set([1,2,3])
```


```python
l1 = list(s1)
```


```python
l1
```

<pre>
[1, 2, 3]
</pre>

```python
l1[0]
```

<pre>
1
</pre>

```python
t1 = tuple(s1)
```


```python
t1
```

<pre>
(1, 2, 3)
</pre>

```python
t1[0]
```

<pre>
1
</pre>
### 교집합, 합집합, 차집합 구하기



```python
s1 = set([1,2,3,4,5,6])
s2 = set([4,5,6,7,8,9])
```

#### 교집합



```python
s1 & s2
```

<pre>
{4, 5, 6}
</pre>

```python
s1.intersection(s2)
```

<pre>
{4, 5, 6}
</pre>
#### 합집합



```python
s1 | s2
```

<pre>
{1, 2, 3, 4, 5, 6, 7, 8, 9}
</pre>

```python
s1.union(s2)
```

<pre>
{1, 2, 3, 4, 5, 6, 7, 8, 9}
</pre>
#### 차집합



```python
s1 - s2
```

<pre>
{1, 2, 3}
</pre>

```python
s2 - s1
```

<pre>
{7, 8, 9}
</pre>

```python
s1.difference(s2)
```

<pre>
{1, 2, 3}
</pre>

```python
s2.difference(s1)
```

<pre>
{7, 8, 9}
</pre>
### 집합 자료형 관련 함수


#### 값 1개 추가(add)



```python
s1 = set([1,2,3])
```


```python
s1.add(4)
```


```python
s1
```

<pre>
{1, 2, 3, 4}
</pre>
#### 값 여러 개 추가(update)



```python
s1 = set([1,2,3])
```


```python
s1.update([4,5,6])
```


```python
s1
```

<pre>
{1, 2, 3, 4, 5, 6}
</pre>
#### 특정 값 제거(remove)



```python
s1 = set([1,2,3])
```


```python
s1.remove(2)
```


```python
s1
```

<pre>
{1, 3}
</pre>
## 2-7 불 자료형


### 불 자료형이란?



```python
a = True
```


```python
b = False
```


```python
type(a)
```

<pre>
bool
</pre>

```python
type(b)
```

<pre>
bool
</pre>

```python
1 == 1
```

<pre>
True
</pre>

```python
2>1
```

<pre>
True
</pre>

```python
2<1
```

<pre>
False
</pre>
### 자료형의 참과 거짓



```python
a = [1,2,3,4]
```


```python
while a:
    a.pop()
```

### 불 연산



```python
bool('python')
```

<pre>
True
</pre>

```python
bool('')
```

<pre>
False
</pre>

```python
bool([1,2,3])
```

<pre>
True
</pre>

```python
bool([])
```

<pre>
False
</pre>

```python
bool(0)
```

<pre>
False
</pre>

```python
bool(3)
```

<pre>
True
</pre>
## 자료형의 값을 저장하는 공간, 변수



```python
a = 1
```


```python
b="python"
```


```python
c=[1,2,3]
```

### 변수란?



```python
a = [1,2,3]
```


```python
id(a)
```

<pre>
1523055964160
</pre>
### 리스트를 복사할 때



```python
a = [1,2,3]
```


```python
b =a
```


```python
id(a)
```

<pre>
1523077525440
</pre>

```python
id(b)
```

<pre>
1523077525440
</pre>

```python
a is b
```

<pre>
True
</pre>

```python
a[1] = 4
```


```python
a
```

<pre>
[1, 4, 3]
</pre>

```python
b
```

<pre>
[1, 4, 3]
</pre>
```b 변수를 생성할 때, a 변수의 값을 가져오면서 a와는 다른 주소를 가리키도록 만드는 방법```


#### 1. [:] 사용



```python
a = [1,2,3]
```


```python
b = a[:]
```


```python
a[1] = 4
```


```python
a
```

<pre>
[1, 4, 3]
</pre>

```python
b
```

<pre>
[1, 2, 3]
</pre>
#### 2. copy 모듈 사용



```python
from copy import copy
```


```python
a = [1,2,3]
```


```python
b = copy(a)
```


```python
a
```

<pre>
[1, 2, 3]
</pre>

```python
b
```

<pre>
[1, 2, 3]
</pre>

```python
b is a
```

<pre>
False
</pre>
### 변수를 만드는 여러 가지 방법



```python
a,b = ('python', 'life')
```


```python
(a,b) = 'python', 'life'
#튜플은 괄호 생략 가능
```


```python
#리스트로 변수 만들기
[a,b] = ['python', 'life']
```


```python
a = b = 'python'
```


```python
a = 3
```


```python
b = 5
```


```python
a,b = b,a #a와 b의 값을 바꿈
```


```python
a
```

<pre>
5
</pre>

```python
b
```

<pre>
3
</pre>
- 나혼자코딩



```python
a = [1,2,3]
```


```python
b = [1,2,3]
```


```python
a is b # 변수 a와 b는 서로 다른 메모리를 가리킴
```

<pre>
False
</pre>
# 3장 프로그램의 구조를 쌓는다!제어문


## 3-1 if문


### 조건문이란 무엇인가?



```python
money = True
```


```python
if money:
```

#### 비교 연산자



```python
x =3
```


```python
y=2
```


```python
x>y
```

<pre>
True
</pre>

```python
3<2
```

<pre>
False
</pre>

```python
x == y
```

<pre>
False
</pre>

```python
x!=y
```

<pre>
True
</pre>

```python
money = 2000
if money >= 3000:
    print("택시를 타고 가라")
else:
    print("걸어 가라")
```

<pre>
걸어 가라
</pre>
#### and, or, not



```python
money = 2000
```


```python
card = True
```


```python
if money >= 3000 or card:
    print("택시를 타고 가라")
else:
    print("걸어 가라")
```

<pre>
택시를 타고 가라
</pre>
#### x in s, x not in s



```python
1 in [1,2,3]
```

<pre>
True
</pre>

```python
1 not in [1,2,3]
```

<pre>
False
</pre>

```python
'a' in ('a','b','c')
```

<pre>
True
</pre>

```python
'j' not in 'python'
```

<pre>
True
</pre>

```python
pocket = ['paper', 'cellphone', 'money']
```


```python
if 'money' in pocket:
    print("택시를 타고 가라")
else:
    print("걸어가라")
```

<pre>
택시를 타고 가라
</pre>
- 나혼자코딩



```python
pocket = ['paper', 'cellphone', 'money']
if 'card' in pocket:
    print("버스를 타고 가라")
else:
    print("걸어가라")
```

<pre>
걸어가라
</pre>
#### 조건문에서 아무 일도 하지 않게 설정하고 싶다면?



```python
#pass 사용
pocket = ['paper', 'money', 'cellphone']
if 'money' in pocket:
    pass
else:
    print("카드를 꺼내라")
```

### 다양한 조건을 판단하는 elif



```python
pocket = ['paper', 'cellphone']
```


```python
card = True
```


```python
if 'money' in pocket:
    print("택시를 타고 가라")
elif card:
    print("택시를 타고 가라")
else:
    print("걸어 가라")
```

<pre>
택시를 타고 가라
</pre>
### if문 한줄로 작성하기



```python
pocket = ['paper', 'money', 'cellphone']
```


```python
if 'money' in pocket:pass
else: print("카드를 꺼내라")
```

### 조건부 표현식

- 조건부가 참인 경우 if 조건문 else 조건문이 거짓인 경우



```python
message = "success" if score >= 60 else "failure"
```

## 3-2 while문


### while문의 기본 구조



```python
treeHit = 0
```


```python
while treeHit < 10:
    treeHit = treeHit + 1
    print("나무를 %d번 찍었습니다." % treeHit)
    if treeHit == 10:
        print("나무 넘어갑니다.")
```

<pre>
나무를 2번 찍었습니다.
나무를 3번 찍었습니다.
나무를 4번 찍었습니다.
나무를 5번 찍었습니다.
나무를 6번 찍었습니다.
나무를 7번 찍었습니다.
나무를 8번 찍었습니다.
나무를 9번 찍었습니다.
나무를 10번 찍었습니다.
나무 넘어갑니다.
</pre>
### while문 만들기



```python
prompt = """
1.Add
2.Del
3.List
4.Quit

Enter number:
"""
```


```python
number = 0
```


```python
while number != 4:
    print(prompt)
    number = int(input())
```

<pre>

1.Add
2.Del
3.List
4.Quit

Enter number:

</pre>
<pre>
 1
</pre>
<pre>

1.Add
2.Del
3.List
4.Quit

Enter number:

</pre>
<pre>
 2
</pre>
<pre>

1.Add
2.Del
3.List
4.Quit

Enter number:

</pre>
<pre>
 3
</pre>
<pre>

1.Add
2.Del
3.List
4.Quit

Enter number:

</pre>
<pre>
 4
</pre>
### while문 강제로 빠져나가기



```python
coffee = 10
```


```python
money = 300
```


```python
while money:
    print("돈을 받았으니 커피를 줍니다.")
    coffee = coffee - 1
    print("남은 커피의 양은 %d개입니다." % coffee)
    if coffee == 0:
        print("커피가 다 떨어졌습니다. 판매를 중지합니다.")
        break
```


```python
coffee = 10
while True:
    money = int(input("돈을 넣어 주세요: "))
    if money == 300:
        print("커피를 줍니다.")
        coffee = coffee -1
    elif money > 300:
        print("거스름돈 %d를 주고 커피를 줍니다." % (money - 300))
        coffee = coffee - 1
    else:
        print("돈을 다시 돌려주고 커피를 주지 않습니다.")
        print("남은 커피의 양은 %d개입니다." % coffee)
    if coffee == 0:
        print("커피가 다 떨어졌습니다. 판매를 중지합니다.")
        break
```

### while문의 맨 처음으로 돌아가기



```python
a = 0
```


```python
while a < 10:
    a = a+1
    if a%2 == 0 : continue
    print(a)
```

<pre>
1
3
5
7
9
</pre>
- 나혼자코딩



```python
a = 0
```


```python
while a < 11:
    a += 1
    if a % 3 == 0:continue
    print(a)
```

<pre>
1
2
4
5
7
8
10
11
</pre>
### 무한 루프



```python
while True:
    print("Ctrl+C를 눌러야 while문을 빠져나갈 수 있습니다.")
```

<pre>
IOPub data rate exceeded.
The Jupyter server will temporarily stop sending output
to the client in order to avoid crashing it.
To change this limit, set the config variable
`--ServerApp.iopub_data_rate_limit`.

Current values:
ServerApp.iopub_data_rate_limit=1000000.0 (bytes/sec)
ServerApp.rate_limit_window=3.0 (secs)

</pre>
## 3-3 for문


### for문의 기본 구조


#### 1. 전형적인 for문



```python
test_list = ['one', 'two', 'three']
```


```python
for i in test_list:
    print(i)
```

<pre>
one
two
three
</pre>
#### 2. 다양한 for문의 사용



```python
a = [(1,2), (3,4), (5,6)]
```


```python
for (first, last) in a:
    print(first + last)
```

<pre>
3
7
11
</pre>
#### 3. for문의 응용



```python
marks = [90, 25, 67, 45, 80]
```


```python
marks = [90,25,67,45,80]
number = 0
for mark in marks:
    number += 1
    if mark >= 60:
        print("%d번 학생은 합격입니다." % number)
    else:
        print("%d번 학생은 불합격입니다." % number)
```

<pre>
1번 학생은 합격입니다.
2번 학생은 불합격입니다.
3번 학생은 합격입니다.
4번 학생은 불합격입니다.
5번 학생은 합격입니다.
</pre>
### for문과 continue문



```python
marks = [90,25,67,45,80]
number = 0
for mark in marks:
    number = number + 1
    if mark < 60: continue
    print("%d번 학생 축하합니다. 합격입니다." % number)
```

<pre>
1번 학생 축하합니다. 합격입니다.
3번 학생 축하합니다. 합격입니다.
5번 학생 축하합니다. 합격입니다.
</pre>
### for문과 함께 자주 사용하는 range함수



```python
a = range(10)
```


```python
a
```

<pre>
range(0, 10)
</pre>

```python
a = range(1,11)
```


```python
a
```

<pre>
range(1, 11)
</pre>
#### range함수의 예시 살펴보기



```python
add = 0
```


```python
for i in range(1,11):
    add = add + i
```


```python
print(add)
```

<pre>
55
</pre>

```python
# number = 0~4
marks = [90,25,67,45,80]
for number in range(len(marks)):
    if marks[number] < 60 : continue
    print("%d번 학생 축하합니다. 합격입니다." % (number + 1))
```

<pre>
1번 학생 축하합니다. 합격입니다.
3번 학생 축하합니다. 합격입니다.
5번 학생 축하합니다. 합격입니다.
</pre>
- 나코딩



```python
sum = 0
for i in range(1,101):
    sum += i
sum
```

<pre>
5050
</pre>
#### for과 range를 사용한 구구단



```python
for i in range(2,10):
    for j in range(1,10):
        print(i*j, end = " ")
    print('')
```

<pre>
2 4 6 8 10 12 14 16 18 
3 6 9 12 15 18 21 24 27 
4 8 12 16 20 24 28 32 36 
5 10 15 20 25 30 35 40 45 
6 12 18 24 30 36 42 48 54 
7 14 21 28 35 42 49 56 63 
8 16 24 32 40 48 56 64 72 
9 18 27 36 45 54 63 72 81 
</pre>
### 리스트 내포(List Comprehension)

- [표현식 for 항목 in 반복 가능 객체 if 조건]

- for문을 여러개 사용할 때

```

 [표현식 for 항목1 in 반복 가능 객체1 if 조건1

         for 항목2 in 반복 가능 객체2 if 조건2

         ...

         for 항목n in 반복 가능 객체n if 조건n]

 ```



```python
a = [1,2,3,4]
```


```python
result = []
```


```python
for num in a:
    result.append(num*3)
print(result)
```

<pre>
[3, 6, 9, 12]
</pre>

```python
a = [1,2,3,4]
```


```python
result = [num*3 for num in a if num % 2 == 0]
```


```python
print(result)
```

<pre>
[6, 12]
</pre>

```python
result = [x*y for x in range(2,10)
         for y in range(1,10)]
```


```python
print(result)
```

<pre>
[2, 4, 6, 8, 10, 12, 14, 16, 18, 3, 6, 9, 12, 15, 18, 21, 24, 27, 4, 8, 12, 16, 20, 24, 28, 32, 36, 5, 10, 15, 20, 25, 30, 35, 40, 45, 6, 12, 18, 24, 30, 36, 42, 48, 54, 7, 14, 21, 28, 35, 42, 49, 56, 63, 8, 16, 24, 32, 40, 48, 56, 64, 72, 9, 18, 27, 36, 45, 54, 63, 72, 81]
</pre>
# 4장 프로그램의 입력과 출력은 어떻게 해야 할가?


## 4-1 함수


### 파이썬 함수의 구조



```python
def add(a,b):
    return a+b
```


```python
a =3
```


```python
b=4
```


```python
c = add(a,b)
```


```python
print(c)
```

<pre>
7
</pre>
### 매개변수와 인수

- ***매개변수*** : 함수에 입력으로 전달된 값을 받는 변수

- ***인수*** : 함수를 호출할 때 전달하는 입력값



```python
def add(a,b):
    return a+b # a,b는 매개변수
```


```python
print(add(3,4)) # 3,4는 인수
```

<pre>
7
</pre>
### 입력값과 결괏값에 따른 함수의 형태


#### 일반적인 함수



```python
def add(a,b):
    result = a+ b
    return result
```


```python
a = add(3,4)
```


```python
print(a)
```

<pre>
7
</pre>
#### 입력값이 없는 함수



```python
def say():
    return 'Hi'
```


```python
a = say()
print(a)
```

<pre>
Hi
</pre>
#### 결과값이 없는 함수



```python
def add(a,b):
    print("%d, %d의 합은 %d입니다." % (a, b, a+b))
```


```python
add(3,4)
```

<pre>
3, 4의 합은 7입니다.
</pre>

```python
a = add(3,4)
```

<pre>
3, 4의 합은 7입니다.
</pre>

```python
print(a) #None 출력
```

<pre>
None
</pre>
#### 입력값도 결과값도 없는 함수



```python
def say():
    print('Hi')
```


```python
say()
```

<pre>
Hi
</pre>
### 매개변수 지정하여 호출하기



```python
def add(a,b):
    return a+b
```


```python
result = add(a=3,b=7)
```


```python
print(result)
```

<pre>
10
</pre>

```python
result = add(b=5, a=3)
```


```python
print(result)
```

<pre>
8
</pre>
### 입력값이 몇 개가 될지 모를 때 (*args)

- *args처럼 매개변수 이름 앞에 *를 붙이면 입력값을 전부 모아서 튜플로 만들어준다.



```python
def add_many(*args) :
    result = 0
    for i in args:
        result = result + i
    return result
```


```python
result = add_many(1,2,3)
```


```python
print(result)
```

<pre>
6
</pre>

```python
result = add_many(1,2,3,4,5,6,7,8,9,10)
```


```python
print(result)
```

<pre>
55
</pre>

```python
def add_mul(choice, *args):
    if choice == "add":
        result = 0
        for i in args:
            result = result + i
    elif choice == "mul":
        result = 1
        for i in args:
            result = result * i
    return result

            
```


```python
result = add_mul('add', 1,2,3,4,5)
```


```python
print(result)
```

<pre>
15
</pre>

```python
result = add_mul('mul', 1,2,3,4,5)
```


```python
print(result)
```

<pre>
120
</pre>
### 키워드 파라미터(**kwargs)

- **kwargs처럼 매개변수 이름 앞에 **을 붙이면 매개변수 kwargs는 딕셔너리가 되고 모든 key=value 형태의 결괏값이 그 딕셔너리에 저장된다.



```python
def print_kwargs(**kwargs):
    print(kwargs)
```


```python
print_kwargs(a=1)
```

<pre>
{'a': 1}
</pre>

```python
print_kwargs(name='foo', age=3)
```

<pre>
{'name': 'foo', 'age': 3}
</pre>
### 함수의 결괏값은 언제나 하나이다



```python
#add_and_mul 함수의 결괏값 a+b와 a*b는 튜플값 하나인 (a+b, a*b)로 돌려준다.
def add_and_mul(a,b):
    return a+b, a*b
```


```python
result = add_and_mul(3,4)
```


```python
result
```

<pre>
(7, 12)
</pre>

```python
#하나의 튜플값을 2개의 결괏값처럼 받고 싶을 때
result1, result2 = add_and_mul(3,4)
```


```python
result1
```

<pre>
7
</pre>

```python
result2
```

<pre>
12
</pre>

```python
# return문이 여러개면 첫번째 return문만 실행된다.
def add_and_mul(a,b):
    return a+b
    return a*b
```


```python
result = add_and_mul(2,3)
```


```python
print(result)
```

<pre>
5
</pre>
### return의 또다른 쓰임새



```python
def say_nick(nick):
    if nick == "바보":
        return
    print("나의 별명은 %s입니다." % nick)
```


```python
say_nick('야호')
```

<pre>
나의 별명은 야호입니다.
</pre>

```python
say_nick('바보')
```

### 매개변수에 초깃값 미리 설정하기



```python
def say_myself(name, old, man=True):
    print("나의 이름은 %s입니다." % name)
    print("나이는 %d살입니다." % old)
    if man:
        print("남자입니다.")
    else:
        print("여자입니다.")
```


```python
say_myself("박응용", 27)
```

<pre>
나의 이름은 박응용입니다.
나이는 27살입니다.
남자입니다.
</pre>

```python
say_myself("박응용", 27, True)
```

<pre>
나의 이름은 박응용입니다.
나이는 27살입니다.
남자입니다.
</pre>

```python
say_myself("박응선", 27, False)
```

<pre>
나의 이름은 박응선입니다.
나이는 27살입니다.
여자입니다.
</pre>

```python
# 초기화시키고 싶은 매개변수는 항상 뒤쪽에 놓는다. 아니면 오류 발생
def say_myself(name, man=True, old):
    print("나의 이름은 %s입니다." % name)
    print("나이는 %d살입니다." % old)
    if man:
        print("남자입니다.")
    else:
        print("여자입니다.")
```


```python
say_myself("박응용", 27)
```

<pre>
나의 이름은 박응용입니다.
나이는 27살입니다.
남자입니다.
</pre>
### 함수 안에서 선언한 변수의 효력 범위



```python
# 함수 안에서 새로 만든 매개변수는 함수 안에서만 사용하는 '함수만의 변수'
a = 1
def vartest(a):
    a = a+1

vartest(a)
print(a)
```

<pre>
1
</pre>

```python
# 함수 안에서 사용하는 매개변수는 함수 밖의 변수 이름과는 전혀 상관이 없다
def vartest(hello):
    hello = hello +1
```


```python
del a
```


```python
def vartest(a):
    a = a+1

vartest(3)
print(a)
```

#### 함수 안에서 함수 밖의 변수를 변경하는 방법


##### 1. return 사용하기



```python
a = 1
def vartest(a):
    a = a+1
    return a

a = vartest(a) # vartest(a)의 결괏값을 함수 밖의 변수 a에 대입
print(a)
```

<pre>
2
</pre>
##### 2. global 명령어 사용하기



```python
# global 명령어는 사용하지 않는 것이 좋다
a=1
def vartest():
    global a # 함수 안에서 함수 밖의 a 변수를 직접 사용
    a = a+1
    
vartest()
print(a)
```

<pre>
2
</pre>
### lambda

- lambda 매개변수1, 매개변수2, ...: 매개변수를 사용한 표현식



```python
add = lambda a,b:a+b
```


```python
result = add(3,4)
```


```python
print(result)
```

<pre>
7
</pre>

```python
def add(a,b):
    return a+b
```


```python
result = add(3,4)
```


```python
print(result)
```

<pre>
7
</pre>
## 4-2 사용자 입력과 출력


### 사용자 입력


#### input의 사용



```python
a = input()
```

<pre>
 Life is too short, you need python
</pre>

```python
a
```

<pre>
'Life is too short, you need python'
</pre>
#### 프롬프트 값을 띄워서 사용자 입력받기

- input("질문 내용")



```python
number = input("숫자를 입력하세요: ")
```

<pre>
숫자를 입력하세요:  3
</pre>

```python
print(number)
```

<pre>
3
</pre>
### print 자세히 알기



```python
a = 123
```


```python
print(a)
```

<pre>
123
</pre>

```python
a = "Python"
```


```python
print(a)
```

<pre>
Python
</pre>

```python
a = [1,2,3]
```


```python
print(a)
```

<pre>
[1, 2, 3]
</pre>
#### 큰따옴표(")로 둘러싸인 문자열은 + 연산과 동일하다



```python
# 따옴표로 둘러싸인 문자열을 연속해서 쓰면 + 연산을 한 것과 같다.
print("life" "is" "too short")
```

<pre>
lifeistoo short
</pre>

```python
print("life"+"is"+"too short")
```

<pre>
lifeistoo short
</pre>
#### 문자열 띄어쓰기는 콤마로 한다



```python
# 콤마(,)를 사용하면 문자열 사이에 띄어쓰기 가능
print("life", "is", "too short")
```

<pre>
life is too short
</pre>
#### 한 줄에 결괏값 출력하기(end=)



```python
# 한 줄에 결괏값을 계속 이어서 출력하려면 매개변수 end를 사용해 끝 문자 지정
for i in range(10):
    print(i, end=' ')
```

<pre>
0 1 2 3 4 5 6 7 8 9 
</pre>
## 4-3 파일 읽고 쓰기


### 파일 생성하기


- 새로운 파일 하나 생성하기



```python
f = open("새파일.txt", 'w')
f.close()
```

#### 파이썬 내장 함수 open

- 파일을 생성하기 위해 사용

- 입력값 : '파일 이름', '파일 열기 모드'

- 결괏값: 파일 객체


- 형식



```python
파일 객체 = open(파일 이름, 파일 열기 모드)
```

- 파일 열기 모드


|파일 열기 모드|설명|

|--|---|

|r|읽기 모드 - 파일을 읽기만 할 때 사용|

|w|쓰기 모드 - 파일에 내용을 쓸 때 사용|

|a|추가 모드 - 파일의 마지막에 새로운 내용을 추가할 때 사용|


***파일을 쓰기 모드(w)로 여는 경우****

- 해당 파일이 이미 존재 : 원래 있던 내용이 모두 사라짐

- 해당 파일이 존재 X : 새로운 파일 생성


- 새파일.txt 파일을 C:/doit 디렉토리에 생성하기



```python
f = open("C:/doit/새파일.txt", 'w')
f.close()
```

f.close()는 열려 있는 파일 객체를 닫아 주는 역할<br>

사실 이 문장은 생략해도 된다. 프로그램을 종료할 때 파이썬 프로그램이 열려 있는 파일의 객체를 자동으로 닫아주기 때문<br>

하지만 close()를 사용해 열려 있는 파일을 직접 닫아 주는 것이 좋다.<br>

쓰기 모드로 열었던 파일을 닫지 않고 다시 사용하려고 하면 오류가 발생하기 때문


### 파일을 쓰기 모드로 열어 출력값 적기


- ***파일***에 결괏값 출력하기



```python
f = open("C:/doit/새파일.txt", 'w')
for i in range(1,11):
    data = "%d번째 줄입니다.\n" % i
    f.write(data)
f.close()
```

- 모니터 화면에 결괏값 출렧하기



```python
for i in range(1,11):
    data = "%d번째 줄입니다.\n" % i
    print(data)
```

<pre>
1번째 줄입니다.

2번째 줄입니다.

3번째 줄입니다.

4번째 줄입니다.

5번째 줄입니다.

6번째 줄입니다.

7번째 줄입니다.

8번째 줄입니다.

9번째 줄입니다.

10번째 줄입니다.

</pre>
### 프로그램 외부에 저장된 파일을 읽는 여러 가지 방법


#### 1. readline 함수 사용하기


- 파일의 첫 번째 줄 출력하기



```python
f = open("C:/doit/새파일.txt", 'r')
line = f.readline()
print(line)
f.close()
```

<pre>
1번째 줄입니다.

</pre>
위 예는 f.open("새파일.txt", 'r')로 파일을 읽기 모드로 연 후 readline()을 사용해 파일의 첫 번째 줄을 읽어 출력


- 모든 줄 읽어서 화면에 출력하기



```python
# 파일을 사용한 입력 방법
f = open("C:/doit/새파일.txt", 'r')
while True:
    line = f.readline()
    if not line:break
    print(line)
f.close()
```

<pre>
1번째 줄입니다.

2번째 줄입니다.

3번째 줄입니다.

4번째 줄입니다.

5번째 줄입니다.

6번째 줄입니다.

7번째 줄입니다.

8번째 줄입니다.

9번째 줄입니다.

10번째 줄입니다.

</pre>
즉 while True:무한 루프 안에서 f.readline()을 사용해 파일을 계속해서 한 줄씩 읽어 들인다.<br>

만약 더 이상 읽을 줄이 없으면 break 수행(readline()은 더 이상 읽을 줄이 없을 경우 None 출력)



```python
# 키보드를 이용한 입력 방법
while 1:
    data = input()
    if not data:
        break
    print(data)
```

<pre>
 3
</pre>
<pre>
3
</pre>
<pre>
 4
</pre>
<pre>
4
</pre>
<pre>
 5
</pre>
<pre>
5
</pre>
<pre>
 3
</pre>
<pre>
3
</pre>
<pre>
 4
</pre>
<pre>
4
</pre>
<pre>
 3
</pre>
<pre>
3
</pre>
<pre>
 
</pre>
#### 2. readlines 함수 사용하기



```python
f = open("C:/doit/새파일.txt", 'r')
lines = f.readlines()
for line in lines:
    print(line)
f.close()
```

<pre>
1번째 줄입니다.

2번째 줄입니다.

3번째 줄입니다.

4번째 줄입니다.

5번째 줄입니다.

6번째 줄입니다.

7번째 줄입니다.

8번째 줄입니다.

9번째 줄입니다.

10번째 줄입니다.

</pre>
readlines 함수는 파일의 모든 줄을 읽어서 각각의 줄을 요소로 갖는 리스트로 돌려줌.<br>

따라서 위 예에서 lines는 리스트 ["1 번째 줄입니다.", "2 번째 줄입니다.", ..., "10 번째 줄입니다."]가 된다.


#### 3. read 함수 사용하기



```python
f = open("C:/doit/새파일.txt", 'r')
data = f.read()
print(data)
f.close()
```

<pre>
1번째 줄입니다.
2번째 줄입니다.
3번째 줄입니다.
4번째 줄입니다.
5번째 줄입니다.
6번째 줄입니다.
7번째 줄입니다.
8번째 줄입니다.
9번째 줄입니다.
10번째 줄입니다.

</pre>
f.read()는 파일의 내용 전체를 문자열로 돌려준다. <br>

따라서 위 예의 data는 파일의 전체 내용


### 파일에 새로운 내용 추가하기

- 쓰기 모드('w') : 파일을 열 때 이미 존재하는 파일을 열면 그 파일의 내용이 모두 사라진다.

- 추가 모드('a') : 원래 있던 값을 유지하면서 단지 새로운 값만 추가


- 새파일.txt 파일을 추가 모드('a')로 열고 write를 사용해서 결괏값을 기존 파일에 추가해 적기



```python
f = open("C:/doit/새파일.txt", 'a')
for i in range(11,20):
    data = "%d 번째 줄입니다.\n" % i
    f.write(data)
f.close()
```

### with문과 함께 사용하기

- with문 : 파일을 열고 닫는 것을 f.close() 없이 자동으로 처리

- with문을 사용하면 with 블록을 벗어나는 순간 열린 파일 객체 f가 자동으로 close된다.


지금까지 살펴본 예제를 보면 항상다음과 같은 방식으로 파일을 열고 닫아 왔다.



```python
# f.close() 사용
f = open("foo.txt", 'w')
f.write("Life is too short, you nee python")
f.close()
```

파일을 열면 위와 같이 항상 close해 주는 것이 좋다.<br>

하지만 이렇게 파일을 열고 닫는 것을 자동을 처리할 수 있다면 편리하지 않을까?<br>

파이썬의 with문이 바로 이런 역할을 함



```python
# with문 사용
with open("foo.txt", 'w') as f:
    f.write("Life is too short, you need python")
```

with문을 사용하면 with 블록을 벗어나는 순간 열린 파일 객체 f가 자동으로 close되어 편리함


### sys모듈로 매개변수 주기




```python
#sys1.py
import sys

args = sys.argv[1:]
for i in args:
    print(i)
```

위 예는 입력받은 인수를 for문을 사용해 차례대로 하나씩 출력하는 예<br>

sys 모듈의 argv는 명령 창에서 입력한 인수를 의미<br>

즉 다음과 같이 입력했다면 argv[0]은 파일 이름 sys1.py가 되고 argv[1]부터는 뒤에 따라오는 인수가 차례로 argv의 요소가 됨


- sys 모듈과 매개변수


|sys1.py|aaa|bbb|ccc|

|---|---|---|---|

|argv[0]|argv[1]|argv[2]|argv[3]|


이 프로그램은 C:\doit 디렉터리에 저장 후 매개변수를 함께 주어 실행 시 다음과 같은 결괏값 얻음



```python
C:\doit>python sys1.py aaa bbb ccc
aaa
bbb
ccc
```

- 명령 행에 입력된 소문자를 대문자로 바꾸기



```python
# sys2.py
import sys
args = sys.argv[1:]
for i in args:
    print(i.upper(), end=' ')
```


```python
C:\doit>python sys2.py life is too short, you need python
LIFE IS TOO SHORT, YOU NEED PYTHON
```

# 0314 추가학습


## factorial 구하기



```python
def factorial(n):
    if n == 1: 
        return 1
    
    return n*factorial(n-1)
```


```python
factorial(15)
```

## 피보나치 구하기



```python
1,1,2,3,5,8, 13, 21, 
def fib(n):
    if n == 1 or n==2:
        return 1
    return fib(n-1) + fib(n-2)
```


```python
fib(5)
```

<pre>
5
</pre>

```python
fib(10)
```

<pre>
55
</pre>
## 재귀함수



```python
import time
def Hello():
    print("안녕하세요")
    time.sleep(1)
    Hello()
```


```python
Hello()
```

<pre>
안녕하세요
안녕하세요
안녕하세요
안녕하세요
안녕하세요
안녕하세요
안녕하세요
안녕하세요
안녕하세요
안녕하세요
</pre>

```python
def hello(count):
    if count == 0:
        return
    
    count -= 1
    print("안녕하세요")
    time.sleep(1)
    hello(count)
```


```python
hello(10)
```

<pre>
안녕하세요
안녕하세요
안녕하세요
안녕하세요
안녕하세요
안녕하세요
안녕하세요
안녕하세요
안녕하세요
안녕하세요
</pre>

```python
```
