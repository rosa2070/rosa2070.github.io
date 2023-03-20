---
layout: single
title:  "점프투파이썬 5장까지"
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
#### 위치 알려주기1(find)



```python
a = "Python is the best choice"
a.find('b') # 문자열에서 b가 처음 나온 위치
```

<pre>
14
</pre>

```python
a.find('k') #찾는 문자나 문자열이 존재하지 않는다면 -1 반환
```

<pre>
-1
</pre>
#### 위치 알려주기2(index)



```python
a = "Life is too short"
```


```python
a.index('t') #문자열 중 t가 맨 처음으로 나온 위치 반환
```

<pre>
8
</pre>

```python
a.index('k') #find 함수와 다른 점 : 문자열 안에 존재하지 않는 문자를 찾으면 오류 반환
```

#### 문자열 삽입(join)

- '구분자'.join(리스트)



```python
",".join('abcd')
```

<pre>
'a,b,c,d'
</pre>

```python
",".join(['a','b','c','d'])
```

<pre>
'a,b,c,d'
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



```python
a = [1,2,3]
```


```python
a.append(4)
```


```python
a
```

<pre>
[1, 2, 3, 4]
</pre>

```python
a.append([5,6])
```


```python
a
```

<pre>
[1, 2, 3, 4, [5, 6]]
</pre>
#### 리스트 정렬(sort)



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



```python
a = [1,2,3]
```


```python
a.insert(0,4) # a[0] 위치에 4 삽입
```


```python
a
```

<pre>
[4, 1, 2, 3]
</pre>

```python
a.insert(3, 5) #a[3] 위치에 5 삽입
```


```python
a
```

<pre>
[4, 1, 2, 5, 5, 3]
</pre>
#### 리스트 요소 제거(remove)

- remove(x)는 리스트에서 첫 번째로 나오는 x를 삭제



```python
a = [1,2,3,1,2,3]
```


```python
a.remove(3)
```


```python
a
```

<pre>
[1, 2, 1, 2, 3]
</pre>

```python
a.remove(3)
```


```python
a
```

<pre>
[1, 2, 1, 2]
</pre>
#### 리스트 요소 끄집어내기(pop)

- pop()은 리스트의 맨 마지막 요소를 돌려주고 그 요소는 삭제



```python
a = [1,2,3]
```


```python
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

```python
a= [1,2,3]
```

- pop(x)는 리스트의 x번재 요소를 돌려주고 그 요소는 삭제



```python
a.pop(1)
```

<pre>
2
</pre>

```python
a
```

<pre>
[1, 3]
</pre>
#### 리스트에 포함된 요소 x의 개수 세기(count)



```python
a = [1,2,3,1]
```


```python
a.count(1)
```

<pre>
2
</pre>
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

```python
for k in a.keys():
    print(k)
```

<pre>
name
phone
birth
</pre>

```python
list(a.keys())
```

<pre>
['name', 'phone', 'birth']
</pre>
#### Value 리스트 만들기



```python
a.values()
```

<pre>
dict_values(['pey', '0119993323', '1118'])
</pre>
#### Key, Value 쌍 얻기(items)



```python
a.items()
```

<pre>
dict_items([('name', 'pey'), ('phone', '0119993323'), ('birth', '1118')])
</pre>
#### Key:Value 쌍 모두 지우기(clear)



```python
a.clear()
```


```python
a
```

<pre>
{}
</pre>
#### Key로 Value 얻기(get)



```python
a = {'name':'pey', 'phone':'0119993323', 'birth':'1118'}
```


```python
a.get('name')
#a.get('name')은 a['name']을 사용했을 때와 동일한 결괏값
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

```python
print(a.get('nokey'))
```

<pre>
None
</pre>

```python
print(a['nokey'])
```


```python
#get(x,'디폴트 값') : 찾으려는 key 값이 없을 경우 미리 정해 둔 디폴트 값 대신 가져오기
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


#### 값 1개 추가하기(add)



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
#### 값 여러 개 추가하기(update)



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
#### 특정 값 제거하기(remove)



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

- 매개변수 : 함수에 입력으로 전달된 값을 받는 변수

- 인수 : 함수를 호출할 때 전달하는 입력값



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

- 파일 객체 = open(파일 이름, 파일 열기 모드=(r,w,a))



```python
# 파일을 쓰기 모드(w)로 열면 해당 파일이 이미 존재할 경우 원래 있던 내용이 모두 사라지고,
# 해당 파일이 존재하지 않으면 새로운 파일 생성
f = open("C:/doit/새파일.txt", 'w')
f.close()
```

- 나코딩



```python
f = open("C:/doit/복습.txt", 'w')
f.close()
```

### 파일을 쓰기 모드로 열어 출력값 적기



```python
# 파일에 결괏값 출력
f = open("C:/doit/새파일.txt", 'w')
for i in range(1,11):
    data = "%d번째 줄입니다.\n" % i
    f.write(data)
f.close()
```


```python
# 모니터 화면에 출력
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



```python
# 가장 첫번째줄 출력
f = open("C:/doit/새파일.txt", 'r')
line = f.readline()
print(line)
f.close()
```

<pre>
1번째 줄입니다.

</pre>

```python
# 모든 줄 출력
f = open("C:/doit/새파일.txt", 'r')
while True:
    line = f.readline()
    if not line: break
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

```python
# 키보드를 이용한 입력 방법
while 1:
    data = input()
    if not data: break
    print(data)
```

<pre>
 3
</pre>
<pre>
3
</pre>
<pre>
 7
</pre>
<pre>
7
</pre>
<pre>
 4
</pre>
<pre>
4
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
### 파일에 새로운 내용 추가하기

- 쓰기 모드('w') : 파일을 열 때 이미 존재하는 파일을 열면 그 파일의 내용이 모두 사라진다.

- 추가 모드('a') : 원래 있던 값을 유지하면서 단지 새로운 값만 추가



```python
f = open("C:/doit/새파일.txt", 'a')
for i in range(11, 20):
    data = "%d 번째 줄입니다\n" % i
    f.write(data)
f.close()
```

### with문과 함께 사용하기

- with문 : 파일을 열고 닫는 것을 f.close() 없이 자동으로 처리

- with문을 사용하면 with 블록을 벗어나는 순간 열린 파일 객체 f가 자동으로 close된다.



```python
# f.close() 사용
f = open("foo.txt",'w')
f.write("Life is too short, you need python")
f.close()
```


```python
# with문 사용
with open("foo.txt", "w") as f:
    f.write("Life is too short, you need python")
```

### sys모듈로 매개변수 주기

- 명령 프롬포트 명령어 [인수1 인수2 ...]



```python
```


```python
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
# 5장 파이썬 날개 달기


## 5-1 클래스


### 클래스는 왜 필요한가?



```python
result = 0

def add(num):
    global result
    result += num
    return result

print(add(3))
print(add(4))
```

<pre>
3
7
</pre>

```python
result1 = 0
result2 = 0

#계산기1
def add1(num):
    global result1
    result1 += num
    return result1

#계산기2
def add2(num):
    global result2
    result2 += num
    return result2
```


```python
print(add1(3))
print(add1(4))
print(add2(3))
print(add2(7))
```

<pre>
3
7
3
10
</pre>

```python
#클래스 사용
class Calculator:
    def __init__(self):
        self.result = 0
    
    def add(self, num):
        self.result += num
        return self.result
    
    #빼기 기능 추가
    def sub(self, num):
        self.result -= num
        return self.result
    
cal1 = Calculator()
cal2 = Calculator()
```


```python
print(cal1.add(3))
print(cal1.add(4))
print(cal2.add(3))
print(cal2.add(7))
```

<pre>
3
7
3
10
</pre>
### 클래스와 객체



```python
class Cookie:
    pass
```


```python
a=Cookie()
b=Cookie()
```

### 사칙연산 클래스 만들기


#### 클래스 구조 만들기



```python
class FourCal:
    pass
```


```python
a = FourCal()
```


```python
type(a) # a는 FourCal클래스의 객체
```

<pre>
__main__.FourCal
</pre>
#### 객체에 숫자 지정할 수 있게 만들기



```python
class FourCal:
    def setdata(self, first, second): # 1. 메서드의 매개변수
        self.first = first
        self.second = second #2.매서드의 수행문(first, second)
```

##### 1. setdata 메서드의 매개변수



```python
a = FourCal()
```


```python
# 메서드의 첫 번째 매개변수 self에는 setdata메서드를 호출한 객체 a가 자동으로 전달되기 때문에 first,second만 넣어주면 된다.
a.setdata(4,2)
```

##### 메서드의 또 다른 호출 방법



```python
# '클래스 이름.메서드' : 객체 a를 첫 번째 매개변수 self에 꼭 전달
a = FourCal()
FourCal.setdata(a,4,2) 
```


```python
# '객체.메서드' : self를 반드시 생략해서 호출
a = FourCal()
a.setdata(4,2)
```

##### 2. setdata 메서드의 수행문



```python
def setdata(self, first, second):
    self.first = first
    self.second = second #메서드의 수행문 (first, second)
```

```

a.setdata(4,2)호출하면

first, second에는 각각 값 4와 2가 전달되어

setdata 메서드의 수행문은 다음과 같이 해석

self.first = 4

self.second = 2



self는 전달된 객체 a이므로 다시 다음과 같이 해석

a.first = 4

a.second = 2

```


- a.first = 4 문장 수행 -> a 객체에 객체변수 first 생성 -> 값 4 저장

- a.second = 2 문장 수행 -> a 객체에 객체변수 second 생성 -> 값 2 저장



```python
a = FourCal()
```


```python
a.setdata(4,2)
```


```python
print(a.first)
```

<pre>
4
</pre>

```python
print(a.second)
```

<pre>
2
</pre>

```python
#a,b 객체 만들기
a = FourCal()
b = FourCal()
```


```python
#a객체의 객체변수 first 생성
a.setdata(4,2)
print(a.first)
```

<pre>
4
</pre>

```python
#b객체의 객체변수 first 생성
b.setdata(3,7)
print(b.first)
```

<pre>
3
</pre>

```python
# a 객체의 first 값은 b 객체의 first값에 영향받지 않고 원래 값 유지
print(a.first) 
```

<pre>
4
</pre>
- 클래스로 만든 객체의 객체변수는 다른 객체의 객체변수와 상관없이 독립적인 값 유지!!



```python
# 지금까지 완성된 FourCal 클래스
class FourCal:
    def setdata(self, first, second):
        self.first = first
        self.second = second
```

#### 더하기 기능 만들기



```python
class FourCal:
    def setdata(self, first, second):
        self.first = first
        self.second = second
    def add(self):
        result = self.first + self.second
        return result
```


```python
a = FourCal()
```


```python
a.setdata(4,2)
```


```python
# add 메서드 호출
print(a.add())
```

<pre>
6
</pre>
- add 메서드 자세히 살펴보기



```python
def add(self):
    result = self.first + self.second
    return result
```


```python
# add 메서드의 매개변수는 self, 반환 값은 result
# 반환 값인 result를 계산하는 부분
result = self.first + self.second
```


```python
# a.add()와 같이 a 객체에 의해 add 메서드가 수행되면 add메서드의 self에는 객체 a가 자동입력되므로 위 내용은 다음과 같이 해석
result = a.first + a.second
```


```python
# 위 내용은 a.add() 메서드 호출 전 a.setdata(4,2)가 먼저 호출되어 
# a.first = 4, a.second = 2라고 미리 설정되었기에 다음과 같이 해석
result = 4 + 2
```


```python
print(a.add())
```

<pre>
6
</pre>
#### 곱하기, 빼기 ,나누기 기능 만들기



```python
class FourCal:
    def setdata(self, first, second):
        self.first = first
        self.second = second
    def add(self):
        result = self.first + self.second
        return result
    def mul(self):
        result = self.first * self.second
        return result
    def sub(self):
        result = self.first - self.second
        return result
    def div(self):
        result = self.first / self.second
        return result
        
```


```python
a = FourCal()
```


```python
b = FourCal()
```


```python
a.setdata(4,2)
```


```python
b.setdata(3,8)
```


```python
a.add()
```

<pre>
6
</pre>

```python
a.mul()
```

<pre>
8
</pre>

```python
a.sub()
```

<pre>
2
</pre>

```python
a.div()
```

<pre>
2.0
</pre>

```python
b.add()
```

<pre>
11
</pre>

```python
b.mul()
```

<pre>
24
</pre>

```python
b.sub()
```

<pre>
-5
</pre>

```python
b.div()
```

<pre>
0.375
</pre>
### 생성자(Constructor)



```python
a = FourCal()
```


```python
a.add() # FourCal 클래스의 인스턴스 a에 setdata 메서드를 수행하지 않고  add 메서드를 수행하면 오류 발생
```

- 이렇게 객체에 초깃값을 설정해야 할 필요가 있을 때 : setdata 메서드 호출보다는 '생성자 구현'이 안전!!

- 생성자(Constructor) : 객체가 생성될 때 자동으로 호출되는 메서드

- 파이썬 메서드 이름으로 __init__을 사용하면 이 메서드는 생성자가 된다.



```python
#FourCal 클래스에 생성자 추가
class FourCal:
    def __init__(self, first, second):
        self.first = first
        self.second = second
    def setdata(self, first, second):
        self.first = first
        self.second = second
    def add(self):
        result = self.first + self.second
        return result
    def mul(self):
        result = self.first * self.second
        return result
    def sub(self):
        result = self.first - self.second
        return result
    def div(self):
        result = self.first / self.second
        return result
```


```python
# 새롭게 추가된 생성자 __init__ 메서드만 따로 떼어 내서 살펴보기
def __init__(self, first, second):
    self.first = first
    self.second = second
```

- __init__ 메서드는 setdata 메서드와 이름만 다르고 모든 게 동일. 

- 단 메서드 이름을 __init__으로 했기 때문에 생성자로 인식되어 객체가 생성되는 시점에 자동으로 호출되는 차이



```python
# 생성자 first와 second에 해당하는 값이 전달되지 않아 오류 발생
a = FourCal() 
```


```python
a = FourCal(4,2)
```


```python
a = FourCal(4,2)
```


```python
print(a.first)
```

<pre>
4
</pre>

```python
print(a.second)
```

<pre>
2
</pre>

```python
a = FourCal(4,2)
```


```python
a.add()
```

<pre>
6
</pre>

```python
a.div()
```

<pre>
2.0
</pre>
### 클래스의 상속

- class 클래스 이름(상속할 클래스 이름)



```python
class MoreFourCal(FourCal):
    pass
```


```python
a = MoreFourCal(4,2)
```


```python
a.add()
```

<pre>
6
</pre>

```python
a = MoreFourCal(4,2)
```

- MoreFourCal 클래스는 FourCal 클래스를 상속했으므로 FourCal 클래스의 모든 기능 사용 가능



```python
a.add()
```

<pre>
6
</pre>

```python
a.mul()
```

<pre>
8
</pre>

```python
a.sub()
```

<pre>
2
</pre>

```python
a.div()
```

<pre>
2.0
</pre>

```python
class MoreFourCal(FourCal):
    def pow(self):
        result = self.first ** self.second
        return result
```


```python
a = MoreFourCal(4,2)
```


```python
a.pow()
```

<pre>
16
</pre>
#### 메서드 오버라이딩(Overriding, 덮어쓰기)

- 부모 클래스(상속한 클래스)에 있는 메서드를 동일한 이름으로 다시 만드는 것



```python
a = FourCal(4,0)
```


```python
a.div() #4를 0으로 나누려고 해서 오류 발생
```


```python
class SafeFourCal(FourCal):
    def div(self):
        if self.second == 0: # 나누는 값이 0인 경우 숫자 0을 돌려주도록 수정
            return 0
        else:
            return self.first/ self.second
```


```python
a = SafeFourCal(4,0)
```


```python
a.div()
```

<pre>
0
</pre>

```python
#### 상속과 변수 (super())
https://supermemi.tistory.com/178
```

#### 상속 super()



```python
#예시
class Nintendo:
    def __init__(self,name, character):
        self.country='Japan'
        self.game_name=name
        self.character=character
       
class New(Nintendo):
    def __init__(self,name,character,genre,income):
        super().__init__(name,character)
        self.ceo='Shigeru Miyamoto'
        self.genre=genre
        self.income=income 
        
p1 = New("simono", "warm", "mystery", 100)
print(p1.country, p1.game_name, p1.ceo, p1.income)
```

<pre>
Japan simono Shigeru Miyamoto 100
</pre>
### 클래스 변수

- 클래스이름.클래스변수



```python
class Family:
    lastname = "김" # 클래스 변수
```


```python
print(Family.lastname) 
```

<pre>
김
</pre>

```python
a = Family()
```


```python
b = Family()
```


```python
print(a.lastname)
```

<pre>
김
</pre>

```python
print(b.lastname)
```

<pre>
김
</pre>
- 클래스 변수 값을 변경하면 클래스로 만든 객체의 lastname 값도 모두 변경된다 = 클래스 변수는 클래스로 만든 모든 객체에 공유된다



```python
Family.lastname = "박" #Family.lastname 수정하면?
```


```python
print(a.lastname)
```

<pre>
박
</pre>

```python
print(b.lastname)
```

<pre>
박
</pre>
#### 클래스 변수와 객체 변수


- a.lastname을 변경하면?



```python
a.lastname = "최"
```


```python
print(a.lastname)
```

<pre>
최
</pre>
- 이렇게 하면 Family클래스의 lastname이 바뀌는 것이 아니라 a 객체에 lastname이라는 객체변수가 새롭게 생성

- 즉, 객체변수는 클래스 변수와 동일한 이름으로 생성 가능

- 이제부터 a.lastname은 Family클래스의 lastname이 아닌 객체 a의 객체변수 lastname을 가리킴


- a.lastname의 객체변수를 생성하더라도 Family 클래스의 lastname과는 상관이 없다



```python
print(Family.lastname)
```

<pre>
박
</pre>

```python
print(b.lastname)
```

<pre>
박
</pre>
- Family 클래스의 lastname 값은 변하지 않았다


## 5-2 모듈

- 함수나 변수 또는 클래스를 모아 놓은 파일

- 다른 파이썬 프로그램에서 불러와 사용할 수 있게끔 만든 파이썬 파일


#### 모듈 만들기

- import 모듈 이름(.py 확장자 제외)

- from 모듈 이름 import 모듈 함수


## 5-3 패키지

- 다음에 정리


## 5-4 예외 처리

- 다음에 정리


## 5-5 내장 함수


### abs(x)

- 어떤 숫자를 입력받았을 때, 그 숫자의 절댓값을 돌려주는 함수



```python
abs(3)
```

<pre>
3
</pre>

```python
abs(-3)
```

<pre>
3
</pre>

```python
abs(-1.2)
```

<pre>
1.2
</pre>
### all(x)

- 반복 가능한(iterable) 자료형 x를 입력 인수로 받으며 이 x가 모두 참이면 True, 거짓이 하날도 있으면 False를 돌려줌



```python
all([1,2,3])
```

<pre>
True
</pre>

```python
all([1,2,3,0])
```

<pre>
False
</pre>
### any(x)

- x 중 하나라도 참이 있으면 True를 돌려주고, x가 모두 거짓일 때에만 False를 돌려줌. all(x)의 반대



```python
any([1,2,3,0])
```

<pre>
True
</pre>

```python
any([0,""])
```

<pre>
False
</pre>
### chr(i)

- 아스키(ASCII) 코드 값을 입력받아 그 코드에 해당하는 문자를 출력하는 함수



```python
chr(97)
```

<pre>
'a'
</pre>

```python
chr(48)
```

<pre>
'0'
</pre>
### dir

- 객체가 자체적으로 가지고 있는 변수나 함수를 보여줌

- 다음 예는 리스트와 딕셔너리 객체 관련 함수(메서드)를 보여주는 예



```python
dir([1,2,3])
```

<pre>
['__add__',
 '__class__',
 '__class_getitem__',
 '__contains__',
 '__delattr__',
 '__delitem__',
 '__dir__',
 '__doc__',
 '__eq__',
 '__format__',
 '__ge__',
 '__getattribute__',
 '__getitem__',
 '__gt__',
 '__hash__',
 '__iadd__',
 '__imul__',
 '__init__',
 '__init_subclass__',
 '__iter__',
 '__le__',
 '__len__',
 '__lt__',
 '__mul__',
 '__ne__',
 '__new__',
 '__reduce__',
 '__reduce_ex__',
 '__repr__',
 '__reversed__',
 '__rmul__',
 '__setattr__',
 '__setitem__',
 '__sizeof__',
 '__str__',
 '__subclasshook__',
 'append',
 'clear',
 'copy',
 'count',
 'extend',
 'index',
 'insert',
 'pop',
 'remove',
 'reverse',
 'sort']
</pre>

```python
dir({'1':'a'})
```

<pre>
['__class__',
 '__class_getitem__',
 '__contains__',
 '__delattr__',
 '__delitem__',
 '__dir__',
 '__doc__',
 '__eq__',
 '__format__',
 '__ge__',
 '__getattribute__',
 '__getitem__',
 '__gt__',
 '__hash__',
 '__init__',
 '__init_subclass__',
 '__ior__',
 '__iter__',
 '__le__',
 '__len__',
 '__lt__',
 '__ne__',
 '__new__',
 '__or__',
 '__reduce__',
 '__reduce_ex__',
 '__repr__',
 '__reversed__',
 '__ror__',
 '__setattr__',
 '__setitem__',
 '__sizeof__',
 '__str__',
 '__subclasshook__',
 'clear',
 'copy',
 'fromkeys',
 'get',
 'items',
 'keys',
 'pop',
 'popitem',
 'setdefault',
 'update',
 'values']
</pre>
### divmod(a,b)

- 2개의 숫자를 입력으로 받으며, a를 b로 나눈 몫과 나머지를 튜플 형태로 돌려줌



```python
divmod(7,3) 
```

<pre>
(2, 1)
</pre>

```python
7//3
```

<pre>
2
</pre>

```python
7%3
```

<pre>
1
</pre>
### enumerate

- '열거하다'라는 뜻. 이 함수는 순서가 있는 자료형(리스트, 튜플, 문자열)을 입력으로 받아 인덱스 값을 포함하는 enumerate 객체를 돌려줌.

- for문과 함께 자주 사용



```python
for i, name in enumerate(['body', 'foo', 'bar']):
    print(i, name)
```

<pre>
0 body
1 foo
2 bar
</pre>
### eval(expression) 

- 실행 가능한 문자열(1+2, 'hi'+'a' 같은 것)을 입력으로 받아 문자열을 실행한 결괏값을 돌려주는 함수



```python
eval('1+2')
```

<pre>
3
</pre>

```python
eval("'hi' + 'a'")
```

<pre>
'hia'
</pre>

```python
eval('divmod(4,3)')
```

<pre>
(1, 1)
</pre>
### filter

- 첫 번째 인수: 함수 이름, 두 번째 인수: 그 함수에 차례로 들어가 반복 가능한 자료형



```python
#filter함수 없이
def positive(l):
    result = []
    for i in l:
        if i > 0:
            result.append(i)
    return result

print(positive([1,-3,2,0,-5,6]))
            
```

<pre>
[1, 2, 6]
</pre>

```python
#filter 함수 사용
def positive(x):
    return x > 0

print(list(filter(positive, [1,-3,2,0,-5,6])))
```

<pre>
[1, 2, 6]
</pre>

```python
list(filter(lambda x: x>0, [1,-3,2,0,-5,6]))
```

<pre>
[1, 2, 6]
</pre>
### hex(x)

- 정수 값을 입력받아 16진수(hexadecimal)로 변환하여 돌려주는 함수



```python
hex(234)
```

<pre>
'0xea'
</pre>

```python
hex(3)
```

<pre>
'0x3'
</pre>
### id(object)

- 객체를 입력받아 객체의 고유 주소 값(레퍼런스)을 돌려주는 함수



```python
a=3
```


```python
id(3)
```

<pre>
2093048332592
</pre>

```python
b=a
```


```python
id(b)
```

<pre>
2093048332592
</pre>
- 3, a, b가 모두 같은 객체를 가리킴



```python
id(4) # 다른 고유 주소값
```

<pre>
2093048332624
</pre>
### input([prompt])

- 사용자 입력을 받는 함수



```python
a = input()
```

<pre>
 hi
</pre>

```python
a
```

<pre>
'hi'
</pre>

```python
b = input("Enter: ")
```

<pre>
Enter:  hi
</pre>

```python
b
```

<pre>
'hi'
</pre>
### int(x)

- 문자열 형태의 숫자나 소수점이 있는 숫자 등을 정수 형태로 돌려주는 함수



```python
int('3')
```

<pre>
3
</pre>

```python
int(3.4)
```

<pre>
3
</pre>
- int(x, radix)는 radix 진수로 표현된 문자열 x를 10진수로 변환하여 돌려줌



```python
int('11',2) #2진수로 표현된 11의 10진수 값 구하기
```

<pre>
3
</pre>

```python
int('1A', 16) #16진수로 표현된 1A의 10진수 값 구하기
```

<pre>
26
</pre>
### isinstance(object, class)

- 첫 번째 인수: 인스턴스 , 두 번째 인수: 클래스 이름

- 입력으로 받은 인스턴스가 그 클래스의 인스턴스인지를 판다하여 참이면 True, 거짓이면 False를 돌려줌



```python
class Person:
    pass
```


```python
a = Person()
```


```python
isinstance(a, Person) #a가 Person클래스의 인스턴스인지 확인
```

<pre>
True
</pre>

```python
b=3
```


```python
isinstance(b, Person) #b가 Person클래스의 인스턴스인지 확인
```

<pre>
False
</pre>
### len(s)

- 입력값 s의 길이(요소의 전체 개수)를 돌려주는 함수



```python
len("python")
```

<pre>
6
</pre>

```python
len([1,2,3])
```

<pre>
3
</pre>

```python
len((1,'a'))
```

<pre>
2
</pre>
### list(s)

- 반복 가능한 자료형 s를 입력받아 리스트로 만들어 돌려주는 함수



```python
list("python")
```

<pre>
['p', 'y', 't', 'h', 'o', 'n']
</pre>

```python
list((1,2,3))
```

<pre>
[1, 2, 3]
</pre>
- 리스트 함수에 리스트를 입력으로 주면 똑같은 리스트를 복사해 돌려줌



```python
a = [1,2,3]
```


```python
b = list(a)
```


```python
b
```

<pre>
[1, 2, 3]
</pre>
### map(f, iterable)

- 함수(f)와 반복 가능한(iterable) 자료형을 입력으로 받음

- map은 입력받은 자료형의 각 요소를 함수 f가 수행한 결과를 묶어서 돌려주는 함수



```python
#map 사용 전
def two_times(numberList):
    result = []
    for number in numberList:
        result.append(number*2)
    return result

result = two_times([1,2,3,4])
print(result)
```

<pre>
[2, 4, 6, 8]
</pre>

```python
#map 사용 후
def two_times(x): return x*2
```


```python
list(map(two_times, [1,2,3,4]))
```

<pre>
[2, 4, 6, 8]
</pre>

```python
list(map(lambda a:a*2, [1,2,3,4]))
```

<pre>
[2, 4, 6, 8]
</pre>
### max(iterable)

- 인수로 반복 가능한 자료형을 입력받아 그 최댓값을 돌려주는 함수



```python
max([1,2,3])
```

<pre>
3
</pre>

```python
max("python")
```

<pre>
'y'
</pre>
### min(iterable)

- max함수와 반대로, 인수로 반복 가능한 자료형을 입력받아 그 최솟값을 돌려주는 함수



```python
min([1,2,3])
```

<pre>
1
</pre>

```python
min("python")
```

<pre>
'h'
</pre>
### oct(x)

- 정수 형태의 숫자를 8진수 문자열로 바꾸어 돌려주는 함수



```python
oct(34)
```

<pre>
'0o42'
</pre>

```python
oct(12345)
```

<pre>
'0o30071'
</pre>
### open(filename, [mode])

- '파일 이름'과 '읽기 방법'을 입력받아 파일 객체를 돌려주는 함수

- 읽기 방법(mode)을 생략하면 기본값인 읽기 전용 모드(r)로 파일 객체를 만들어 돌려줌



```python
f = open("binary_file", "rb") #rb는 '바이너리 읽기 모드'
```


```python
# fread와 fread2는 동일한 방법
fread = open("read_mode.txt", 'r')
fread2 = open("read_mode.txt")
```


```python
fappend = open("append_mode.txt", 'a')
```

### ord(c)

- 문자의 아스키 코드 값을 돌려주는 함수



```python
ord('a')
```

<pre>
97
</pre>

```python
ord('0')
```

<pre>
48
</pre>
### pow

- pow(x,y)는 x의 y제곱한 결괏값을 돌려주는 함수



```python
pow(2,4)
```

<pre>
16
</pre>

```python
pow(3,3)
```

<pre>
27
</pre>
### range([start,] stop [,step])

- for문과 함께 자주 사용

- 입력받은 숫자에 해당하는 범위 값을 반복 가능한 객체로 만들어 돌려줌


#### 인수가 하나일 경우



```python
list(range(5))
```

<pre>
[0, 1, 2, 3, 4]
</pre>
#### 인수가 2개일 경우



```python
list(range(5,10))
```

<pre>
[5, 6, 7, 8, 9]
</pre>
#### 인수가 3개일 경우



```python
list(range(1,10,2))
```

<pre>
[1, 3, 5, 7, 9]
</pre>

```python
list(range(9,-10,-1))
```

<pre>
[9, 8, 7, 6, 5, 4, 3, 2, 1, 0, -1, -2, -3, -4, -5, -6, -7, -8, -9]
</pre>
### round(number[,ndigits])

- 숫자를 입력받아 반올림해주는 함수

- round 함수의 두 번째 매개변수는 반올림하여 표시하고 싶은 소수점의 자릿수(ndigits)



```python
round(4.6)
```

<pre>
5
</pre>

```python
round(4.2)
```

<pre>
4
</pre>

```python
round(5.678,2)
```

<pre>
5.68
</pre>
### sorted(iterable)

- 입력값을 정렬한 후 그 결과를 리스트로 돌려주는 함수



```python
sorted([3,1,2])
```

<pre>
[1, 2, 3]
</pre>

```python
sorted(['a','c','b'])
```

<pre>
['a', 'b', 'c']
</pre>

```python
sorted("zero")
```

<pre>
['e', 'o', 'r', 'z']
</pre>

```python
sorted((3,2,1))
```

<pre>
[1, 2, 3]
</pre>
### str(object)

- 문자열 형태로 객체를 변환하여 돌려주는 함수



```python
str(3)
```

<pre>
'3'
</pre>

```python
str('hi')
```

<pre>
'hi'
</pre>

```python
str('hi'.upper())
```

<pre>
'HI'
</pre>
### sum(iterable)

- 입력받은 리스트나 튜플의 모든 요소의 합을 돌려주는 함수



```python
sum([1,2,3])
```

<pre>
6
</pre>

```python
sum([4,5,6])
```

<pre>
15
</pre>
### tuple

- 반복 가능한 자료형을 입력받아 튜플 형태로 바꾸어 돌려주는 함수

- 만약 튜플이 입력을 들어오면 그대로 돌려줌



```python
tuple("abc")
```

<pre>
('a', 'b', 'c')
</pre>

```python
tuple([1,2,3])
```

<pre>
(1, 2, 3)
</pre>

```python
tuple((1,2,3))
```

<pre>
(1, 2, 3)
</pre>
### type(object)

- 입력값의 자료형이 무엇인지 알려주는 함수



```python
type("abc")
```

<pre>
str
</pre>

```python
type([])
```

<pre>
list
</pre>

```python
type(open("test", 'w'))
```

<pre>
_io.TextIOWrapper
</pre>
### zip(*iterable)

- 동일한 개수로 이루어진 자료형을 묶어 주는 역할을 하는 함수

- *iterable : 반복 가능(iter-able)한 자료형 여러 개를 입력할 수 있다는 의미



```python
list(zip([1,2,3], [4,5,6]))
```

<pre>
[(1, 4), (2, 5), (3, 6)]
</pre>

```python
list(zip([1,2,3],[4,5,6],[7,8,9]))
```

<pre>
[(1, 4, 7), (2, 5, 8), (3, 6, 9)]
</pre>

```python
list(zip("abc", "def"))
```

<pre>
[('a', 'd'), ('b', 'e'), ('c', 'f')]
</pre>
## 5-6 라이브러리


### sys

- 파이썬 인터프리터가 제공하는 변수와 함수를 직접 제어할 수 있게 해주는 모듈


#### 명령 행에서 인수 전달 - sys.argvs



```python
# 명령 프롬프트 창에서 다음과 같이 test.py 뒤에 또 다른 값을 함께 넣어주면 sys.argv 리스트에 그 값 추가
C:/User/home> python test.py abc pey guido
```

##### 예제


- argv_test.py 파일은 C:/Users/user/Mymod 디렉터리에 저장했다고 가정



```python
#argv_test.py
import sys
print(sys.argv)
```

명령 프롬프트 창에서 Mymod 디렉토리로 들어간 뒤 다음과 같이 실행



```python
C:/Users/user/Mymod> python argv_test.py you need python
['argv_test.py', 'you', 'need', 'python']
```

python 명령어 뒤의 모든 것들이 공백을 기준으로 나뉘어서 sys.argv 리스트의 요소가 된다.


#### 강제로 스크립트 종료 - sys.exit



```python
>>> sys.exit()
```

#### 자신이 만든 모듈 불러와 사용 - sys.path

- sys.path는 파이썬 모듈들이 저장되어 있는 위치를 나타냄

- 즉, 이 위치에 있는 파이썬 모듈은 경로에 상관없이 어디에서나 불러올 수 있다.



```python
>>> import sys
>>> sys.path
['', 'C:\\Users\\user\\AppData\\Local\\Programs\\Python\\Python310\\python310.zip', 'C:\\Users\\user\\AppData\\Local\\Programs\\Python\\Python310\\DLLs', 'C:\\Users\\user\\AppData\\Local\\Programs\\Python\\Python310\\lib', 'C:\\Users\\user\\AppData\\Local\\Programs\\Python\\Python310', 'C:\\Users\\user\\AppData\\Local\\Programs\\Python\\Python310\\lib\\site-packages', 'C:\\Users\\user\\AppData\\Local\\Programs\\Python\\Python310\\lib\\site-packages\\win32', 'C:\\Users\\user\\AppData\\Local\\Programs\\Python\\Python310\\lib\\site-packages\\win32\\lib', 'C:\\Users\\user\\AppData\\Local\\Programs\\Python\\Python310\\lib\\site-packages\\Pythonwin']
```

위 예에서 ''는 현재 디렉터리를 말한다.



```python
#path_append.py
import sys
sys.path.append("C:/Users/user/Mymod")
```

위와 같이 파이썬 프로그램 파일에서 sys.path.append를 사용해 경로 이름을 추가할 수 있다. 

<br>이렇게 하고 난 후에는 C:/Users/user/Mymod 디렉터리에 있는 파이썬 모듈을 불러와서 사용 가능


### pickle

- 객체의 형태를 그대로 유지하면서 파일에 저장하고 불러올 수 있게 하는 모듈


- pickle 모듈의 dump 함수를 사용해 딕셔너리 객체인 data를 그대로 파일에 저장하는 방법



```python
import pickle
f = open("test.txt", 'wb')
data = {1:'python', 2: 'you need'}
pickle.dump(data, f)
f.close()
```

- pickle.dump로 저장한 파일을 pickle.load를 사용해서 원래 있던 딕셔너리 객체(data) 상태 그대로 불러오기



```python
import pickle
f = open("test.txt", 'rb')
data = pickle.load(f)
print(data)
```

<pre>
[2, 4, 6, 8, 10, 12, 14, 16, 18, 20, 22, 24, 26, 28, 30, 32, 34, 36, 38, 40, 42, 44, 46, 48, 50, 52, 54, 56, 58, 60, 62, 64, 66, 68, 70, 72, 74, 76, 78, 80, 82, 84, 86, 88, 90, 92, 94, 96, 98, 100]
</pre>
위 예에서는 딕셔너리 객체를 사용했지만 어떤 자료형이든 저장하고 불러오기 가능



```python
# 추가
```


```python
my_list = ["a", "b", "c"]
with open("data.pickle", "wb") as f:
    pickle.dump(my_list, f)
```


```python
import pickle 
with open("data2.pickle", "wb") as fw:
    pickle.dump(b, fw)

with open('data2.pickle', 'rb') as fr:
    df = pickle.load(fr)
print(df) 
```

### OS

- OS모듈은 환경 변수나 디렉터리, 파일 등의 OS 자원을 제어할 수 있게 해주는 모듈


#### 내 시스템의 환경 변수 값을 알고 싶을 때 - os.environ

- 시스템은 제각기 다른 환경 변수 값을 가지고 있는데, ***os.environ***은 현재 시스템의 환경 변수 값을 보여줌.



```python
import os
```


```python
os.environ
```

<pre>
environ{'ALLUSERSPROFILE': 'C:\\ProgramData',
        'APPDATA': 'C:\\Users\\user\\AppData\\Roaming',
        'COMMONPROGRAMFILES': 'C:\\Program Files\\Common Files',
        'COMMONPROGRAMFILES(X86)': 'C:\\Program Files (x86)\\Common Files',
        'COMMONPROGRAMW6432': 'C:\\Program Files\\Common Files',
        'COMPUTERNAME': 'DESKTOP-2PGRMF4',
        'COMSPEC': 'C:\\windows\\system32\\cmd.exe',
        'DRIVERDATA': 'C:\\Windows\\System32\\Drivers\\DriverData',
        'FPS_BROWSER_APP_PROFILE_STRING': 'Internet Explorer',
        'FPS_BROWSER_USER_PROFILE_STRING': 'Default',
        'HOMEDRIVE': 'C:',
        'HOMEPATH': '\\Users\\user',
        'JAVA_HOME': 'C:\\Program Files\\Amazon Corretto\\jdk11.0.18_10',
        'LOCALAPPDATA': 'C:\\Users\\user\\AppData\\Local',
        'LOGONSERVER': '\\\\DESKTOP-2PGRMF4',
        'NUMBER_OF_PROCESSORS': '12',
        'ONEDRIVE': 'C:\\Users\\user\\OneDrive',
        'OS': 'Windows_NT',
        'PATH': 'C:\\Program Files\\Amazon Corretto\\jdk11.0.18_10\\bin;C:\\windows\\system32;C:\\windows;C:\\windows\\System32\\Wbem;C:\\windows\\System32\\WindowsPowerShell\\v1.0\\;C:\\windows\\System32\\OpenSSH\\;C:\\Users\\user\\AppData\\Local\\Programs\\Python\\Python310\\Scripts\\;C:\\Users\\user\\AppData\\Local\\Programs\\Python\\Python310\\;C:\\Users\\user\\AppData\\Local\\Microsoft\\WindowsApps;',
        'PATHEXT': '.COM;.EXE;.BAT;.CMD;.VBS;.VBE;.JS;.JSE;.WSF;.WSH;.MSC',
        'PROCESSOR_ARCHITECTURE': 'AMD64',
        'PROCESSOR_IDENTIFIER': 'Intel64 Family 6 Model 167 Stepping 1, GenuineIntel',
        'PROCESSOR_LEVEL': '6',
        'PROCESSOR_REVISION': 'a701',
        'PROGRAMDATA': 'C:\\ProgramData',
        'PROGRAMFILES': 'C:\\Program Files',
        'PROGRAMFILES(X86)': 'C:\\Program Files (x86)',
        'PROGRAMW6432': 'C:\\Program Files',
        'PROMPT': '$P$G',
        'PSMODULEPATH': 'C:\\Program Files\\WindowsPowerShell\\Modules;C:\\windows\\system32\\WindowsPowerShell\\v1.0\\Modules',
        'PUBLIC': 'C:\\Users\\Public',
        'SESSIONNAME': 'Console',
        'SYSTEMDRIVE': 'C:',
        'SYSTEMROOT': 'C:\\windows',
        'TEMP': 'C:\\Users\\user\\AppData\\Local\\Temp',
        'TMP': 'C:\\Users\\user\\AppData\\Local\\Temp',
        'USERDOMAIN': 'DESKTOP-2PGRMF4',
        'USERDOMAIN_ROAMINGPROFILE': 'DESKTOP-2PGRMF4',
        'USERNAME': 'user',
        'USERPROFILE': 'C:\\Users\\user',
        'WINDIR': 'C:\\windows',
        'ZES_ENABLE_SYSMAN': '1',
        'PYDEVD_USE_FRAME_EVAL': 'NO',
        'JPY_SESSION_NAME': 'C:\\Users\\user\\New\\0309review.ipynb',
        'JPY_INTERRUPT_EVENT': '3216',
        'IPY_INTERRUPT_EVENT': '3216',
        'JPY_PARENT_PID': '3236',
        'TERM': 'xterm-color',
        'CLICOLOR': '1',
        'FORCE_COLOR': '1',
        'CLICOLOR_FORCE': '1',
        'PAGER': 'cat',
        'GIT_PAGER': 'cat',
        'MPLBACKEND': 'module://matplotlib_inline.backend_inline'}
</pre>
위 결괏값은 필자의 시스템 정보<br>

***os.environ***은 환경 변수에 대한 정보를 딕셔너리 객체로 돌려줌


돌려받은 객체가 딕셔너리이기 때문에 다음과 같이 호출 가능 <br>

- 필자 시스템의 PATH 환경 변수 내용



```python
os.environ['PATH']
```

<pre>
'C:\\Program Files\\Amazon Corretto\\jdk11.0.18_10\\bin;C:\\windows\\system32;C:\\windows;C:\\windows\\System32\\Wbem;C:\\windows\\System32\\WindowsPowerShell\\v1.0\\;C:\\windows\\System32\\OpenSSH\\;C:\\Users\\user\\AppData\\Local\\Programs\\Python\\Python310\\Scripts\\;C:\\Users\\user\\AppData\\Local\\Programs\\Python\\Python310\\;C:\\Users\\user\\AppData\\Local\\Microsoft\\WindowsApps;'
</pre>
#### 현재 디렉터리 위치 변경 - os.chdir



```python
os.chdir("C:/WINDOWS")
```

#### 현재 디렉터리 위치 돌려받기 - os.getcwd



```python
os.getcwd() 
```

<pre>
'C:\\WINDOWS'
</pre>
#### 시스템 명령어 호출 - os.system

- 시스템 자체의 프로그램이나 기타 명령어를 파이썬에서 호출할 수도 있다.

- os.system("명령어")


- 현재 디렉터리에서 시스템 명령어 dir 실행하기



```python
os.system("dir")
```

<pre>
0
</pre>
#### 실행한 시스템 명령어의 결괏값 돌려받기 - os.popen

- os.popen은 시스템 명령어를 실행한 결괏값을 읽기 모드 형태의 파일 객체로 돌려줌



```python
f = os.popen("dir")
```

- 읽어 들인 파일 객체의 내용 보기



```python
print(f.read())
```

<pre>
 C 드라이브의 볼륨에는 이름이 없습니다.
 볼륨 일련 번호: E0E8-707D

 C:\WINDOWS 디렉터리

2023-03-13  오후 06:11    <DIR>          .
2023-03-13  오후 06:11    <DIR>          ..
2019-12-07  오후 06:50    <DIR>          addins
2021-12-15  오후 01:16    <DIR>          appcompat
2023-02-20  오전 11:44    <DIR>          apppatch
2023-03-15  오전 09:54    <DIR>          AppReadiness
2023-02-21  오후 05:37    <DIR>          assembly
2023-02-20  오전 11:44    <DIR>          bcastdvr
2021-12-15  오후 01:22            81,408 bfsvc.exe
2019-12-07  오후 06:31    <DIR>          Boot
2019-12-07  오후 06:14    <DIR>          Branding
2023-02-20  오후 01:36    <DIR>          CbsTemp
2021-07-08  오전 10:01             1,290 comsetup.log
2019-12-07  오후 06:14    <DIR>          Containers
2019-12-07  오후 06:10            29,857 Core.xml
2019-12-07  오후 06:10            29,857 CoreSingleLanguage.xml
2021-09-13  오후 01:34    <DIR>          CSC
2021-07-08  오전 09:51                10 Csup.txt
2019-12-07  오후 06:14    <DIR>          Cursors
2021-09-13  오후 01:47    <DIR>          debug
2021-07-08  오전 10:05            22,863 diagerr.xml
2019-12-07  오후 06:31    <DIR>          diagnostics
2021-12-15  오후 01:25    <DIR>          DiagTrack
2021-07-08  오전 10:05            22,863 diagwrn.xml
2019-12-07  오후 06:49    <DIR>          DigitalLocker
2021-08-31  오전 08:10             6,400 DtcInstall.log
2023-02-20  오전 11:44    <DIR>          en-US
2023-02-20  오전 11:38         5,253,864 explorer.exe
2021-09-13  오후 01:49    <DIR>          Firmware
2019-12-07  오후 06:14    <DIR>          GameBarPresenceWriter
2019-12-07  오후 06:31    <DIR>          Globalization
2019-12-07  오후 06:49    <DIR>          Help
2022-10-04  오후 02:05         1,075,712 HelpPane.exe
2019-12-07  오후 06:09            18,432 hh.exe
2019-12-07  오후 06:31    <DIR>          IdentityCRL
2021-07-08  오전 06:25    <DIR>          IME
2023-02-20  오전 11:44    <DIR>          ImmersiveControlPanel
2023-03-16  오후 06:07    <DIR>          INF
2019-12-07  오후 06:14    <DIR>          InputMethod
2023-02-20  오전 11:44    <DIR>          ko-KR
2019-12-07  오후 06:14    <DIR>          L2Schemas
2023-03-08  오후 05:01    <DIR>          LiveKernelReports
2023-03-13  오후 06:11    <DIR>          Logs
2021-07-08  오전 09:27             1,378 lsasetup.log
2019-12-07  오후 06:08            43,131 mib.bin
2023-03-16  오전 11:42    <DIR>          Microsoft.NET
2019-12-07  오후 06:14    <DIR>          Migration
2019-12-07  오후 06:14    <DIR>          ModemLogs
2012-08-06  오후 02:14         1,731,072 MSetCaller.exe
2021-09-13  오후 01:36    <DIR>          MSetup
2022-10-04  오후 01:52           201,216 notepad.exe
2022-07-11  오전 10:32    <DIR>          OCR
2019-12-07  오후 06:14    <DIR>          Offline Web Pages
2021-12-15  오전 10:58    <DIR>          Panther
2019-12-07  오후 06:14    <DIR>          Performance
2023-03-14  오전 10:28           100,490 PFRO.log
2019-12-07  오후 06:31    <DIR>          PLA
2023-02-20  오전 11:44    <DIR>          PolicyDefinitions
2023-03-16  오후 12:05    <DIR>          Prefetch
2022-07-11  오전 10:32    <DIR>          PrintDialog
2019-12-07  오후 06:10            30,831 professional.xml
2023-02-20  오전 11:44    <DIR>          Provisioning
2022-12-06  오후 08:26           736,120 py.exe
2022-12-06  오후 08:26            49,536 pyshellext.amd64.dll
2022-12-06  오후 08:26           736,640 pyw.exe
2021-07-08  오전 06:22           370,176 regedit.exe
2019-12-07  오후 06:31    <DIR>          Registration
2021-07-08  오전 06:12    <DIR>          RemotePackages
2019-12-07  오후 06:14    <DIR>          rescache
2019-12-07  오후 06:31    <DIR>          Resources
2021-07-08  오전 09:32    <DIR>          RSTLog
2019-12-19  오후 04:07         2,877,104 RtlExUpd.dll
2010-08-06  오후 05:09            16,018 Samsung.png
2019-12-07  오후 06:14    <DIR>          SchCache
2021-07-08  오전 06:12    <DIR>          schemas
2020-09-21  오전 04:40    <DIR>          sec
2021-07-08  오전 06:12    <DIR>          security
2021-07-08  오전 09:27    <DIR>          ServiceProfiles
2021-09-13  오후 01:46    <DIR>          ServiceState
2022-07-11  오전 10:17    <DIR>          servicing
2019-12-07  오후 06:18    <DIR>          Setup
2023-03-16  오후 06:07            11,166 setupact.log
2021-07-08  오전 09:28                 0 setuperr.log
2022-07-11  오전 10:32    <DIR>          ShellComponents
2022-10-04  오후 01:54    <DIR>          ShellExperiences
2019-12-07  오후 06:31    <DIR>          SKB
2021-09-13  오후 01:32    <DIR>          SoftwareDistribution
2019-12-07  오후 06:14    <DIR>          Speech
2019-12-07  오후 06:14    <DIR>          Speech_OneCore
2023-02-20  오전 11:38           163,840 splwow64.exe
2019-12-07  오후 06:14    <DIR>          System
2019-12-07  오후 06:12               219 system.ini
2023-03-16  오후 06:07    <DIR>          System32
2023-02-20  오전 11:44    <DIR>          SystemApps
2023-02-20  오전 11:44    <DIR>          SystemResources
2021-12-15  오후 01:25    <DIR>          SystemTemp
2023-02-20  오후 01:36    <DIR>          SysWOW64
2019-12-07  오후 06:14    <DIR>          TAPI
2021-07-08  오전 09:28    <DIR>          Tasks
2023-03-17  오전 09:10    <DIR>          Temp
2019-12-07  오후 06:14    <DIR>          tracing
2020-04-21  오전 05:57    <DIR>          twain_32
2019-12-07  오후 06:10            65,024 twain_32.dll
2019-12-07  오후 06:14    <DIR>          Vss
2019-12-07  오후 06:14    <DIR>          WaaS
2019-12-07  오후 06:31    <DIR>          Web
2021-07-08  오전 09:47               124 win.ini
2023-03-17  오전 11:04               276 WindowsUpdate.log
2019-12-07  오후 06:10            11,776 winhlp32.exe
2023-02-27  오후 02:15    <DIR>          WinSxS
2019-12-07  오후 06:52           316,640 WMSysPr9.prx
2019-12-07  오전 06:29            11,264 write.exe
              33개 파일          14,016,597 바이트
              79개 디렉터리  164,516,950,016 바이트 남음

</pre>
#### 기타 유용한 os 관련 함수

- ***os.mkdir***(디렉터리) : 디렉터리 생성

- ***os.rmdir***(디렉터리) : 디렉터리 삭제. 단 디렉터리가 비어있어야 삭제 가능

- ***os.unlink***(파일 이름) : 파일 지우기

- ***os.rename***(src, dst) : src라는 이름의 파일을 dst라는 이름으로 바꿈


### shutil

- 파일을 복사해 주는 파이썬 모듈


src라는 이름의 파일을 dst로 복사하기

- dst가 디렉터리 이름일 경우 : src라는 파일 이름으로 dst 디렉터리에 복사

- 동일한 파일 이름이 있을 경우 : 덮어쓰기



```python
import shutil
```


```python
shutil.copy("src.txt", "dst.txt")
```

<pre>
'dst.txt'
</pre>
위 예를 실행하면 src.txt 파일과 동일한 내용의 파일이 dst.txt로 복사됨



```python
import os
os.getcwd()
```

<pre>
'C:\\Users\\user\\New'
</pre>
### glob

- 가끔 파일을 읽고 쓰는 기능이 있는 프로그램을 만들다 보면 특정 디렉터리에 있는 파일 이름 모두를 알아야 할 때가 있다. 

- 이럴 때 사용하는 모듈이 바로 glob


#### 디렉터리에 있는 파일들을 리스트로 만들기 - glob(pathname)

- glob 모듈은 디렉터리 안의 파일들을 읽어서 돌려준다. *, ? 등 메타 문자를 써서 원하는 파일만 읽어 들일 수도 있다.


- C:/Users/user/test 디렉터리에 있는 파일 중 이름이 sys로 시작하는 파일을 모두 찾아서 읽어들이기



```python
import os
os.chdir("C:/Users/user/test")
import glob
glob.glob("sys*")
```

<pre>
['sys1.py', 'sys2.py']
</pre>
### tempfile

- 파일을 임시로 만들어서 사용할 때 유용한 모듈

- ***tempfile.mkstemp()*** : 중복되지 않는 임시 파일의 이름을 무작위로 만들어서 돌려줌 


#### tempfile.TemporaryFile()

- 임시 저장 공간으로 사용할 파일 객체를 돌려줌

- 이 파일은 기본적으로 바이너리 쓰기 모드(wb)를 가짐

- f.close()가 호출되면 이 파일 객체는 자동으로 사라짐



```python
import tempfile
f = tempfile.TemporaryFile()
f.close() # 생성한 임시 파일 자동 삭제
```

### time

- 시간과 관련된 time 모듈에는 함수가 굉장히 많다. 그 중 가장 유용한 몇 가지만 살펴보자


#### time.time

- UTC(Universal Time Coordinated 협정 세계 표준시)를 사용해 현재 시간을 실수 형태로 돌려주는 함수

- 1970년 1월 1일 0시 0분 0초를 기준으로 지난 시간을 초 단위로 돌려줌



```python
import time
time.time()
```

<pre>
1679041213.0852582
</pre>

```python
time.time()/60
time.time()/60/60
time.time()/60/60/24 #며칠
time.time()/60/60/24/30 #몇 달
time.time()/60/60/24/30/12 # 몇 년
```

<pre>
53.981645794929086
</pre>
#### time.localtime

- time.time()이 돌려준 실수 값을 사용해 연도, 월, 일, 시, 분, 초, ...의 형태로 바꾸어주는 함수



```python
time.localtime(time.time())
```

<pre>
time.struct_time(tm_year=2023, tm_mon=3, tm_mday=17, tm_hour=17, tm_min=21, tm_sec=4, tm_wday=4, tm_yday=76, tm_isdst=0)
</pre>

```python
t = time.localtime()
print(t.tm_year, "년", t.tm_mday, "일")
```

<pre>
2023 년 17 일
</pre>
#### time.asctime

- 위 time.localtime에 의해서 반환된 튜플 형태의 값을 인수로 받아서 날짜와 시간을 알아보기 쉬운 형태로 돌려주는 함수



```python
time.asctime(time.localtime(time.time()))
```

<pre>
'Fri Mar 17 17:21:58 2023'
</pre>
#### time.ctime

- time.asctime(time.localtime(tim.time()))은 time.ctime()을 사용해 간편하게 표시 가능

- asctime과 다른 점은 ctime은 항상 현재 시간만을 돌려줌



```python
time.ctime()
```

<pre>
'Fri Mar 17 17:24:32 2023'
</pre>
#### strftime과 strptime

- ***strftime*** : 날짜와 시간(datetime)을 문자열로 출력

- ***strptime*** : 날짜와 시간 형식의 문자열을 datetime으로 변환


##### time.strftime

- strftime 함수는 시간에 관계된 것을 세밀하게 표현하는 여러 포맷 코드를 제공



```python
time.strftime('출력할 형식 포맷 코드', time.localtime(time.time()))
```

- time.strftime을 사용하는 예시



```python
import time
```


```python
time.strftime('%x', time.localtime(time.time()))
```

<pre>
'03/17/23'
</pre>

```python
time.strftime('%c', time.localtime(time.time()))
```

<pre>
'Fri Mar 17 17:26:40 2023'
</pre>

```python
import datetime
now = datetime.datetime.now()
```


```python
date = now.strftime('%Y-%m-%d')
date
```

<pre>
'2023-03-17'
</pre>

```python
time = now.strftime('%H:%M:%S')
time
```

<pre>
'18:30:07'
</pre>

```python
datetime = now.strftime('%Y-%m-%d %H:%M:%S')
datetime
```

<pre>
'2023-03-17 18:30:07'
</pre>

```python
time = now.strftime('')
```

##### time.strptime

- datetime.strptime(문자열, 형식)



```python
import datetime
str_datetime = '2021-04-08 21:31:48'
currdate = datetime.datetime.strptime(str_datetime, "%Y-%m-%d %H:%M:%S")

print(type(currdate))
```

<pre>
<class 'datetime.datetime'>
</pre>
#### time.sleep

- 주로 루프 안에서 많이 사용

- 이 함수를 사용하면 일정한 시간 간격을 두고 루프 실행 가능



```python
import time
for i in range(10):
    print(i)
    time.sleep(i)
```

<pre>
0
1
2
3
4
5
6
7
8
9
</pre>
위 예는 1초 간격으로 0부터 9까지의 숫자 출력<br>

위 예에서 볼 수 있듯이 time.sleep함수의 인수는 실수 형태 사용 가능<br>

즉, 1이면 1초, 0.5면 0.5초가 된다.


### calendar

- 파이썬에서 달력을 볼 수 있게 해주는 모듈


#### calendar.calendar(연도)

- 그 해의 전체 달력을 볼 수 있음



```python
import calendar
print(calendar.calendar(2023))
```

<pre>
                                  2023

      January                   February                   March
Mo Tu We Th Fr Sa Su      Mo Tu We Th Fr Sa Su      Mo Tu We Th Fr Sa Su
                   1             1  2  3  4  5             1  2  3  4  5
 2  3  4  5  6  7  8       6  7  8  9 10 11 12       6  7  8  9 10 11 12
 9 10 11 12 13 14 15      13 14 15 16 17 18 19      13 14 15 16 17 18 19
16 17 18 19 20 21 22      20 21 22 23 24 25 26      20 21 22 23 24 25 26
23 24 25 26 27 28 29      27 28                     27 28 29 30 31
30 31

       April                      May                       June
Mo Tu We Th Fr Sa Su      Mo Tu We Th Fr Sa Su      Mo Tu We Th Fr Sa Su
                1  2       1  2  3  4  5  6  7                1  2  3  4
 3  4  5  6  7  8  9       8  9 10 11 12 13 14       5  6  7  8  9 10 11
10 11 12 13 14 15 16      15 16 17 18 19 20 21      12 13 14 15 16 17 18
17 18 19 20 21 22 23      22 23 24 25 26 27 28      19 20 21 22 23 24 25
24 25 26 27 28 29 30      29 30 31                  26 27 28 29 30

        July                     August                  September
Mo Tu We Th Fr Sa Su      Mo Tu We Th Fr Sa Su      Mo Tu We Th Fr Sa Su
                1  2          1  2  3  4  5  6                   1  2  3
 3  4  5  6  7  8  9       7  8  9 10 11 12 13       4  5  6  7  8  9 10
10 11 12 13 14 15 16      14 15 16 17 18 19 20      11 12 13 14 15 16 17
17 18 19 20 21 22 23      21 22 23 24 25 26 27      18 19 20 21 22 23 24
24 25 26 27 28 29 30      28 29 30 31               25 26 27 28 29 30
31

      October                   November                  December
Mo Tu We Th Fr Sa Su      Mo Tu We Th Fr Sa Su      Mo Tu We Th Fr Sa Su
                   1             1  2  3  4  5                   1  2  3
 2  3  4  5  6  7  8       6  7  8  9 10 11 12       4  5  6  7  8  9 10
 9 10 11 12 13 14 15      13 14 15 16 17 18 19      11 12 13 14 15 16 17
16 17 18 19 20 21 22      20 21 22 23 24 25 26      18 19 20 21 22 23 24
23 24 25 26 27 28 29      27 28 29 30               25 26 27 28 29 30 31
30 31

</pre>
#### calendar.prcal(연도)

- 위와 똑같은 결괏값 출력



```python
calendar.prcal(2023)
```

<pre>
                                  2023

      January                   February                   March
Mo Tu We Th Fr Sa Su      Mo Tu We Th Fr Sa Su      Mo Tu We Th Fr Sa Su
                   1             1  2  3  4  5             1  2  3  4  5
 2  3  4  5  6  7  8       6  7  8  9 10 11 12       6  7  8  9 10 11 12
 9 10 11 12 13 14 15      13 14 15 16 17 18 19      13 14 15 16 17 18 19
16 17 18 19 20 21 22      20 21 22 23 24 25 26      20 21 22 23 24 25 26
23 24 25 26 27 28 29      27 28                     27 28 29 30 31
30 31

       April                      May                       June
Mo Tu We Th Fr Sa Su      Mo Tu We Th Fr Sa Su      Mo Tu We Th Fr Sa Su
                1  2       1  2  3  4  5  6  7                1  2  3  4
 3  4  5  6  7  8  9       8  9 10 11 12 13 14       5  6  7  8  9 10 11
10 11 12 13 14 15 16      15 16 17 18 19 20 21      12 13 14 15 16 17 18
17 18 19 20 21 22 23      22 23 24 25 26 27 28      19 20 21 22 23 24 25
24 25 26 27 28 29 30      29 30 31                  26 27 28 29 30

        July                     August                  September
Mo Tu We Th Fr Sa Su      Mo Tu We Th Fr Sa Su      Mo Tu We Th Fr Sa Su
                1  2          1  2  3  4  5  6                   1  2  3
 3  4  5  6  7  8  9       7  8  9 10 11 12 13       4  5  6  7  8  9 10
10 11 12 13 14 15 16      14 15 16 17 18 19 20      11 12 13 14 15 16 17
17 18 19 20 21 22 23      21 22 23 24 25 26 27      18 19 20 21 22 23 24
24 25 26 27 28 29 30      28 29 30 31               25 26 27 28 29 30
31

      October                   November                  December
Mo Tu We Th Fr Sa Su      Mo Tu We Th Fr Sa Su      Mo Tu We Th Fr Sa Su
                   1             1  2  3  4  5                   1  2  3
 2  3  4  5  6  7  8       6  7  8  9 10 11 12       4  5  6  7  8  9 10
 9 10 11 12 13 14 15      13 14 15 16 17 18 19      11 12 13 14 15 16 17
16 17 18 19 20 21 22      20 21 22 23 24 25 26      18 19 20 21 22 23 24
23 24 25 26 27 28 29      27 28 29 30               25 26 27 28 29 30 31
30 31
</pre>
#### calendar.prmonth(월)

- 2023년 12월의 달력만 출력



```python
calendar.prmonth(2023, 12)
```

<pre>
   December 2023
Mo Tu We Th Fr Sa Su
             1  2  3
 4  5  6  7  8  9 10
11 12 13 14 15 16 17
18 19 20 21 22 23 24
25 26 27 28 29 30 31
</pre>
#### calendar.weekday(연도, 월, 일)

- 그 날짜에 해당하는 요일 정보 출력

- 월요일: 0, 화요일: 1, 수요일: 2, 목요일: 3, 금요일: 4, 토요일: 5, 일요일: 6



```python
calendar.weekday(2023,12,31)
```

<pre>
6
</pre>
#### calendar.monthrange(연도, 월)

- 입력받은 달의 1일이 무슨 요일인지와 그 달이 며칠가지 있는지를 튜플 형태로 돌려줌



```python
calendar.monthrange(2023, 12)
```

<pre>
(4, 31)
</pre>
위 예는 2023년 12월 1일은 금요일이고, 이 달은 31일까지 있다는 것을 보여줌


날짜 관련 프로그래밍을 할 때 위 2가지 함수는 매우 유용하게 사용됨


### random

- 난수(규칙이 없는 임의의 수)를 발생시키는 모듈

- random, randint


#### random.random()

- 0.0과 0.1 사이의 실수 중 난수 값 돌려주는 예시



```python
import random
random.random()
```

<pre>
0.5037757872104343
</pre>
#### random.randint

- 1에서 10 사이의 정수 중 난수 값을 돌려줌



```python
random.randint(1,10) # 끝 숫자를 포함한다
```

<pre>
6
</pre>
- 1에서 55사이의 정수 중에서 난수 값을 돌려줌



```python
random.randint(1,55)
```

<pre>
3
</pre>
- random 모듈을 사용한 함수 만들기



```python
import random
def random_pop(data):
    number = random.randint(0,len(data)-1)
    return data.pop(number)

if __name__ == "__main__":
    data = [1,2,3,4,5]
    while data: print(random_pop(data))
```

<pre>
5
1
2
4
3
</pre>
위 random_pop 수는 리스트의 요소 중 무작위를 하나 선택해 꺼낸 후 그 값을 돌려줌. <br>

꺼낸 요소는 pop 메서드에 의해 사라짐


#### random.choice

- random_pop함수는 random 모듈의 choice 함수를 사용해 더 직관적으로 만들 수 있음



```python
def random_pop(data):
    number = random.choice(data)
    data.remove(number)
    return number
```

random.choice 함수는 입력으로 받은 리스트에서 무작위로 하나를 선택해 돌려줌


#### random.shuffle

- 리스트의 항목을 무작위로 섞고 싶을 때 사용



```python
import random
data = [1,2,3,4,5]
random.shuffle(data)
data
```

<pre>
[2, 4, 1, 5, 3]
</pre>
[1,2,3,4,5] 리스트가 shuffle 함수에 의해 섞여서 [2,4,1,5,3]으로 변함


#### random.uniform()

- 2개의 숫자 사이의 랜덤 실수 리턴



```python
random.uniform(1,10)
```

<pre>
6.917801691134953
</pre>
#### random.choice()

- 랜덤하게 하나의 원소 선택



```python
import random
l = [0,1,2,3,4]
print(random.choice(l))
```

<pre>
0
</pre>
- 튜플이나 문자열에서도 choice 함수를 사용해 문자를 랜덤하게 취득 가능



```python
import random
print(random.choice(('xxx','yyy','zzz')))
print(random.choice('abcde'))
```

<pre>
yyy
d
</pre>
- 주의점 : 공백 리스트나 튜플 또는 문자열에 choice 함수를 사용하면 에러 발생



```python
import random
print(random.choice([]))
```

#### random.choices()

- ***형식***: choices(리스트, k =취득개수)

- choices 함수의 첫 번째 파라미터 : 대상이 되는 리스트

- choices 함수의 두 번재 파라미터 : 랜덤으로 취득하고 싶은 요소 개수 k



```python
import random
l = [0,1,2,3,4]
print(random.choices(l, k=3))
```

<pre>
[0, 1, 2]
</pre>
choices 함수를 사용해 취득한 결과를 보면 추출 대상 리스트에는 중복된 값을 지정하지 않았지만 중복된 값이 표시되어 있음

<br>sample 함수와 다르게 choices 함수는 한번 추출한 요소를 제외시키지 않음<br>

그래서 추출 대상 리스트의 요소수보다 랜덤하게 취득하고 싶은 요소를 크게 지정해도 에러가 발생하지 않음



```python
import random
l = [0,1,2,3,4]
print(random.choices(l,k=10))
```

<pre>
[1, 0, 1, 4, 0, 2, 2, 3, 3, 1]
</pre>
추출 대상 리스트에는 요소가 5개 있지만 랜덤으로 10개 추출 가능

<br>k를 생략할 경우 기본값으로 1 지정


#### random.sample()

- 리스트에서 여러 개 요소를 랜덤으로 취득

- sample로 랜덤하게 취득한 값은 중복되지 않음

- ***형식*** : ***sample***(리스트, 취득 개수)<br>

***sample*** 함수의 첫번째 파라미터 : 추출 대상이 되는 리스트<br>

***sample*** 함수의 두번째 파라미터 : 랜덤으로 취득하고 싶은 요소 개수




```python
import random
l = [0,1,2,3,4]
print(random.sample(l,3))

#반환값 데이터 타입 확인
print(type(random.sample(l,3)))
```

<pre>
[1, 4, 2]
<class 'list'>
</pre>
***sample***을 사용해 취득한 결과값은 리스트 형태로 반환<br>

결과값이 없는 경우에도 리스트 형태로 반환



```python
import random
l = [0,1,2,3,4]
print(random.sample(l,0))
```

<pre>
[]
</pre>
- 취득하고 싶은 요소 개수가 추출 대상 리스트 요소수보다 큰 경우 에러발생



```python
import random
l = [0,1,2,3,4]
print(random.sample(l,10))
```

- sample 함수에도 튜플이나 문자열 지정 가능



```python
import random
print(random.sample(('xxx','yyy','zzz'),2))
print(random.sample('abcde', 2))
```

<pre>
['zzz', 'xxx']
['a', 'c']
</pre>

```python
random.sample() : 중복없이
random.shuffle() 

random.choices() : k개 복원추출(중복가능)
random.randint(10,15) : 정수 1개 임의출력,
                        10~15사이의 정수 1개 출력?
    
random.random.random() : 0초과 1미만의 실수 중 1개 임의 출력
random.uniform(10,15) : 10~15 사이의 실수 1개 출력?
```

### webbrowser

- 자신의 시스템에서 사용하는 기본 웹 브라우저를 자동으로 실행하는 모듈


#### webbrowser.open

- ***웹 브라우저가 이미 실행된 상태*** : 입력 주소로 이동

- ***웹 브라우저가 실행되지 않은 상태*** : 새로 웹 브라우저 실행 후 해당 주소로 이동

- 다음 예제는 웹 브라우저를 자동으로 실행하고 해당 URL인 google.com으로 가게 함




```python
import webbrowser
webbrowser.open("http://google.com")
```

<pre>
True
</pre>
#### webbrowser.open_new

- 이미 웹브라우저가 실행된 상태이더라도 새로운 창으로 해당 주소가 열리게 함


### 스레드를 다루는 threading 모듈

- ***프로세스***: 컴퓨터에서 동작하고 있는 프로그램

- 보통 1개의 프로세스는 한 가지 일만 하지만 스레드(Thread)를 사용하면 한 프로세스 안에서 2가지 또는 그 이상의 일을 동시에 수행 가능



```python
import time

def long_task(): # 5초의 시간이 걸리는 함수
    for i in range(5):
        time.sleep(1) # 1초간 대기
        print("working:%s\n" % i)

print("Start")
    
for i in range(5): # long_task를 5회 수행
    long_task()

print("End")
```

<pre>
Start
working:0

working:1

working:2

working:3

working:4

working:0

working:1

working:2

working:3

working:4

working:0

working:1

working:2

working:3

working:4

working:0

working:1

working:2

working:3

working:4

working:0

working:1

working:2

working:3

working:4

End
</pre>
long_task 함수는 수행하는 데 5초의 시간이 걸리는 함수. 위 프로그램은 이 함수를 총 5번 반복해서 수행하는 프로그램.<br>

이 프로그램은 5초가 5번 반복되니 총 25초의 시간이 걸림.<br>

하지만 스레드를 사용하면 5초의 시간이 걸리는 long_task 함수를 동시에 실행할 수 있으니 시간을 줄일 수 있다.


- 스레드를 사용해 수정한 프로그램



```python
import time
import threading # 스레드를 생성하기 위해서는 threading 모듈이 필요

def long_task():
    for i in range(5):
        time.sleep(1)
        print("working:%s\n" % i)
print("Start")

threads = []
for i in range(5):
    t = threading.Thread(target=long_task) # 스레드 생성
    threads.append(t)
    
for t in threads:
    t.start() # 스레드 실행

print("End")
```

<pre>
Start
End
working:0

working:0

working:0

working:0

working:0

working:1

working:1

working:1

working:1

working:1

working:2

working:2

working:2

working:2

working:2

working:3
working:3


working:3

working:3

working:3

working:4

working:4

working:4

working:4

working:4

</pre>
이와 같이 프로그램을 수정 후 실행해 보면 25초 걸리던 작업이 5초 정도에 수행된다.<br>

threading.Thread를 사용해 만든 스레드 객체가 동시 작업을 가능하게 해 주기 때문<br>

하지만 위 프로그램을 실행 시 "Start"와 "End"가 먼저 출력되고 그 이후에 스레드의 결과가 출력됨. 또한 프로그램이 정상 종료되지 않음.<br>

우리가 기대하는 것은 "Start"가 출력되고 그 다음에 스레드의 결과 출력 후 마지막으로 "End"가 출력되는 것


- 문제 해결을 위해 수정한 프로그램



```python
import time
import threading

def long_task():
    for i in range(5):
        time.sleep(1)
        print("working%s\n" % i)

print("Start")

threads = []
for i in range(5):
    t = threading.Thread(target=long_task)
    threads.append(t)
for t in threads:
    t.start()
for t in threads:
    t.join() # join으로 스레드가 종료될 때까지 기다림

print("End")
```

<pre>
Start
working0

working0

working0

working0

working0

working1
working1


working1

working1

working1

working2
working2


working2

working2

working2

working3
working3

working3


working3

working3

working4
working4

working4


working4

working4

End
</pre>
스레드의 join함수는 해당 스레드가 종료될 때까지 기다리게 함. <br>

따라서 위와 같이 수정하면 우리가 원하던 출력을 보게 됨.



```python
- random.choices()  #random.choice
- random.sample()<br><br>
- random.randrange()
```

## 5-4 예외 처리


### 오류는 어떨 때 발생?


- 디렉터리 안에 없는 파일을 열려고 시도



```python
f = open("나없는파일", 'r')
```

FileNotFoundError 오류 발생


- 0으로 다른 숫자를 나누는 경우



```python
4/0
```

4를 0으로 나누려니까 ZeroDivisionError 오류 발생



```python
a = [1,2,3]
```


```python
a[4]
```

IndexError 오류 발생


### 오류 예외 처리 기법


#### try, except문

- 기본 구조: <br>

  try:<br>

  ...<br>

  except [발생 오류[as 오류 메시지 변수]]:

  ...

- ***try 블록 수행 중 오류 발생*** : except 블록 수행

- ***try 블록 수행 중 오류 발생X*** : except 블록 수행되지 X


#### except 구문을 사용하는 3가지 방법


##### 1. try, except만 쓰는 방법

오류 종류에 상관없이 오류 발생하면 except 블록 수행




try: <br>

...<br>

except: <br>

...


##### 2. 발생 오류만 포함한 except문

오류 발생 시 except문에 미리 정해 놓은 오류 이름과 일치할 때만 except 블록 수행


try:<br>

...<br>

except 발생 오류:<br>

...


##### 3. 발생 오류와 오류 메시지 변수까지 포함한 except문

두 번째 경우에서 오류 메시지의 내용까지 알고 싶을 때 사용


try:<br>

...<br>

except 발생 오류 as 오류 메시지 변수:<br>

...



```python
try:
    4/0
except ZeroDivisionError as e:
    print(e)
```

<pre>
division by zero
</pre>
위처럼 4를 0으로 나누려고 하면 ZeroDivisionError가 발생해 except 블록이 실행되고 변수 e에 담기는 오류 메시지를 출력(division by zero)


- 나코딩



```python
try:
    a = [1,2,3]
    a[4]
except IndexError as e:
    print(e)
```

<pre>
list index out of range
</pre>
#### try ... finally

- finally절은 try문 수행 도중 예외 발생 여부에 상관없이 항상 수행

- 보통 finally절은 사용한 리소스를 close해야 할 때 많이 사용



```python
f = open('foo.txt', 'w')
try:
    #무언가 수행
finally:
    f.close()
```

foo.txt 파일을 쓰기 모드로 연 후 try문을 수행 후 예외 발생 여부와 상관없이 finally절에서 f.close()로 열린 파일 닫기 가능


#### 여러 개의 오류 처리하기

- 구문 : <br>

try:<br>

...<br>

except 발생 오류 1: <br>

...

except 발생 오류 2: <br>

...



```python
try:
    a = [1,2]
    print(a[3])
    4/0
except ZeroDivisionError:
    print("0으로 나눌 수 없습니다.")
except IndexError:
    print("인덱싱할 수 없습니다.")
```

<pre>
인덱싱할 수 없습니다.
</pre>
인덱싱 오류가 먼저 발생했으므로 4/0으로 발생되는 ZeroDivisionError 오류는 발생되지 않았다.


- 오류 메시지도 가져오기



```python
try:
    a = [1,2]
    print(a[3])
    4/0
except ZeroDivisionError as e:
    print(e)
except IndexError as e:
    print(e)
```

<pre>
list index out of range
</pre>
- ZeroDivisionError와 IndexError 함께 처리



```python
try:
    a = [1,2]
    print(a[3])
    4/0
except (ZeroDivisionError, IndexError) as e:
    print(e)
```

<pre>
list index out of range
</pre>
2개 이상의 오류를 동시에 처리하기 위해서는 위와 같이 괄호를 사용해 함께 묶어 처리


### 오류 회피하기



```python
try:
    f = open("나없는파일", 'r')
except FileNotFoundError: # 파일이 없더라도 오류를 발생시키지 않고 통과
    pass
```

### 오류 일부러 발생시키기(raise)

- raise 명령어를 사용해 오류를 강제로 발생시킬 수 있다.


- Bird 클래스를 상속받는 자식 클래스는 반드시 fly라는 함수를 구현하도록 만들고 싶은 경우(강제로 그렇게 하고 싶은 경우)



```python
class Bird:
    def fly(self):
        raise NotImplementedError
```

- 자식 클래스가 fly 함수를 구현하지 않은 상태로 fly 함수 호출한 경우



```python
class Eagle(Bird): #Eagle 클래스는 Bird 클래스를 상속 받음
    pass

eagle = Eagle()
eagle.fly()
```

Eagle클래스는 Bird클래스를 상속받는다. 그런데 Eagle클래스에서 fly함수를 구현하지 않았기 때문에 Bird 클래스의 fly 함수가 호출된다.<br>

그리고 raise문에 의해 NotImplemented Error 발생


- NotImplementedError가 발생되지 않도록 다음과 같이 Eagle클래스에 fly 함수 반드시 구현



```python
class Eagle(Bird):
    def fly(self):
        print("very fast")
    
eagle = Eagle()
eagle.fly()
```

<pre>
very fast
</pre>
### 예외 만들기

- 프로그램 수행 도중 특수한 경우에만 예외 처리를 하기 위해 종종 예외를 만들어서 사용

- 파이썬 내장 클래스인 Exception 클래스를 상속하여 예외를 만들 수 있다



```python
class MyError(Exception):
    pass
```

- 별명 출력해주는 함수 작성



```python
def say_nick(nick):
    if nick == '바보':
        raise MyError()
    print(nick)
```


```python
say_nick("천사")
```

<pre>
천사
</pre>

```python
say_nick("바보") # MyError 발생
```

- 예외 처리 기법을 사용해 MyError 발생을 예외 처리



```python
try:
    say_nick("천사")
    say_nick("바보")
except MyError:
    print("허용되지 않는 별명입니다.")
```

<pre>
천사
허용되지 않는 별명입니다.
</pre>
- 오류 메시지 사용한 예외 처리



```python
try:
    say_nick("천사")
    say_nick("바보")
except MyError as e:
    print(e)
```

<pre>
천사

</pre>
하지만 프로그램을 실행해 보면 print(e)로 오류 메시지가 출력되지 않음.<br>

오류 메시지 출력 시 오류 메시지가 보이게 하려면 오류 클래스에 다음과 같은 __str__ 메서드 구현<br>

__str__ 메서드 : print(e)처럼 오류 메시지를 print문으로 출력할 경우 호출되는 메서드



```python
class MyError(Exception):
    def __str__(self):
        return "허용되지 않는 별명입니다."
```


```python
try:
    say_nick("천사")
    say_nick("바보")
except MyError as e:
    print(e)
```

<pre>
천사
허용되지 않는 별명입니다.
</pre>
"허용되지 않는 별명입니다." 라는 오류메시지 출력



```python
```
