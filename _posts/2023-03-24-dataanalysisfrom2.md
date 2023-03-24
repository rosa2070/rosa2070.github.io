---
layout: single
title:  "파이썬 라이브러리를 활용한 데이터 분석"
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


# 파이썬 언어의 기본, Ipython, 주피터노트북


## 2.1 파이썬 인터프리터


파이썬 : ***인터프리터*** 언어<br>

파이썬 인터프리터는 한 번에 하나의 명령어만 실행<br>

표준 인터프리터는 명령행에서 python을 입력해 실행



```python
#Anaconda Prompt에서
(base) C:\Users\user>python
Python 3.10.9 | packaged by Anaconda, Inc. | (main, Mar  1 2023, 18:18:15) [MSC v.1916 64 bit (AMD64)] on win32
Type "help", "copyright", "credits" or "license" for more information.
>>> a = 5
>>> print(a)
5
```

```>>>``` : 파이썬 인터프리터의 ***프롬프트***, 여기에 코드 입력<br>

```exit()``` : 파이썬 인터프리터를 종료하고 명령행 프롬프트로 돌아가기 (```Ctrl-D```로도 가능)


파이썬 프로그램을 실행할 때는 첫 번째 인자로 .py 파일을 넘긴다. <br>

예를 들어 다음 내용으로 hello_world.py를 작성했다고 하자.



```python
#hello_world.py
print('Hello world')
```

터미널에서 다음과 같이 실행 가능(hello_world.py 파일은 반드시 현재 작업하고 있는 터미널의 디렉터리에 존재해야 함)



```python
(base) C:\Users\user\dataanalysis>python hello_world.py
Hello world
```

일부 파이썬 개발자는 이런 식으로 파이썬 코드를 실행하며, 데이터 분석이나 과학 계산 파이썬 개발자들은 향상된 대화형 파이썬 인터프리터인 IPython 또는 IPython 프로젝트에서 만든 웹 기반의 ***주피터 노트북*** 사용<br>

***%run*** 명령어를 사용하면 IPython은 지정된 파일의 코드를 같은 프로세스 안에서 실행하여 실행이 끝났을 때 그 결과를 인터랙티브하게 탐색할 수 있게 함



```python
(base) C:\Users\user\dataanalysis>ipython
Python 3.10.9 | packaged by Anaconda, Inc. | (main, Mar  1 2023, 18:18:15) [MSC v.1916 64 bit (AMD64)]
Type 'copyright', 'credits' or 'license' for more information
IPython 8.10.0 -- An enhanced Interactive Python. Type '?' for help.

In [1]: %run hello_world.py
Hello world

In [2]:
```

표준 프롬프트는 ```>>>```인 반면 IPython의 프롬프트는 ```In [2]:```와 같은 형식으로 번호가 붙는다.


## 2.2 IPython 기초

이 절에서는 IPython 셸과 주피터 노트북을 실행하는 방법, 주요 콘셉트를 소개


### 2.2.1 IPython 셸 실행하기


***IPython*** : 일반 파이썬 인터프리터를 실행시키듯이 ipython 명령어를 입력해 실행 가능



```python
(base) C:\Users\user\dataanalysis>ipython
Python 3.10.9 | packaged by Anaconda, Inc. | (main, Mar  1 2023, 18:18:15) [MSC v.1916 64 bit (AMD64)]
Type 'copyright', 'credits' or 'license' for more information
IPython 8.10.0 -- An enhanced Interactive Python. Type '?' for help.

In [1]: a =5

In [2]: a
Out[2]: 5
```

파이썬 코드를 입력하고 Enter키를 눌러서 실행 가능<br>

파이썬에 그냥 변수 이름만 입력 : 그 객체의 문자열 표현 출력



```python
In [4]: import numpy as np

In [5]: data = {i : np.random.randn() for i in range(7)}

In [6]: data
Out[6]:
{0: 0.331797604568851,
 1: -0.4453867577695362,
 2: -0.32127346857737854,
 3: 1.5857183379978113,
 4: 0.3981765861368851,
 5: 0.6683993999381282,
 6: 1.578446053139218}
```

첫 두 줄은 파이썬 코드인데, 두 번째 줄에서 data라는 이름의 변수를 생성하고 새로 생성한 파이썬 사전형(딕셔너리)를 참조하도록 함.<br>

마지막 줄은 data 변수의 값 출력


대부분의 파이썬 객체는 print를 이용한 보통의 출력 결과와는 달리 좀 더 읽기 편하거나 ***보기 좋은 형태***로 출력<br>

위 예제를 표준 파이썬 인터프리터에서 보면 다소 읽기 불편한 형태로 출력



```python
Python 3.10.9 | packaged by Anaconda, Inc. | (main, Mar  1 2023, 18:18:15) [MSC v.1916 64 bit (AMD64)] on win32
Type "help", "copyright", "credits" or "license" for more information.
>>> from numpy.random import randn
>>> data = {i : randn() for i in range(7)}
>>> print(data)
{0: 0.20672553450387546, 1: 0.017326901197757646, 2: 0.8644699310714371, 3: -0.2444758473744509, 4: -0.6762926100850093, 5: -0.37695916931421003, 6: 2.096549305346934}
```

또한 IPython은 일부 코드(약간 개선된 복사/붙여넣기 기능을 통해) 아니면 전체 파이썬 스크립트를 쉽게 실행할 수 있는 기능 제공


### 2.2.2 주피터 노트북 실행하기


주피터 프로젝트의 주요 구성요소 중 하나인 ***노트북***은 코드, 텍스트, 데이터 시각화를 비롯한 다른 출력을 대화형으로 구성할 수 있는 대화형 문서 형식<br>

주피터 노트북은 어떤 프로그래밍 언어로도 작성 가능한 주피터 대화형 컴퓨팅 프로토콜의 구현체인 ***커널***과 상호작용<br>

파이썬 주피터 커널은 IPython 시스템을 이용해 동작


***jupyter notebookr*** 명령어 : 주피터 실행



```python
(base) C:\Users\user>jupyter notebook
[W 16:44:53.507 NotebookApp] Loading JupyterLab as a classic notebook (v6) extension.
[I 2023-03-24 16:44:53.507 LabApp] JupyterLab extension loaded from C:\Users\user\anaconda3\lib\site-packages\jupyterlab
[I 2023-03-24 16:44:53.507 LabApp] JupyterLab application directory is C:\Users\user\anaconda3\share\jupyter\lab
[I 16:44:54.360 NotebookApp] The port 8888 is already in use, trying another port.
[I 16:44:54.360 NotebookApp] Serving notebooks from local directory: C:\Users\user
[I 16:44:54.360 NotebookApp] Jupyter Notebook 6.5.2 is running at:
[I 16:44:54.360 NotebookApp] http://localhost:8889/?token=bcfad8e6562b26fb066b7f33964e85ece9f4c1f70e8a6533
[I 16:44:54.360 NotebookApp]  or http://127.0.0.1:8889/?token=bcfad8e6562b26fb066b7f33964e85ece9f4c1f70e8a6533
[I 16:44:54.360 NotebookApp] Use Control-C to stop this server and shut down all kernels (twice to skip confirmation).
[C 16:44:54.388 NotebookApp]
```

대부분의 플랫폼에서는 --no--browser 옵션을 지정하지 않으면 자동으로 기본 웹 브라우저 실행<br>

그렇지 않다면 노트북을 실행했을 때 출력되는 웹 주소(여기서는 ```http://localhost:8888/```)로 접속


### 2.2.3 탭 자동완성


겉으로 보기에 IPython은 표준 파이썬 인터프리터와는 조금 다르게 생김<br>

표준 파이썬 셸에 비해 가장 두드러진 개선은 ***탭을 통한 자동완성 기능***으로, 대부분의 통합 개발 환경이나 대화형 데이터 분석 환경에 구현되어 있는 기능<br>

셸에서 입력을 하는 동안 탭을 누르면 네임스페이스에서 그 시점까지 입력한 내용과 맞아떨어지는 변수(객체, 함수 등)를 자동으로 찾아줌



```python
In [1]: an_apple = 27

In [2]: an_example = 42

In [3]: an<Tab>
an_apple  and  an_example any()      
```

이 예제에서 IPython은 앞서 정의한 두 변수는 물론이고 파이썬 예약어인 ***and***와 내장 함수인 ***any***를 함께 보여주는 것을 확인 가능<br>

물론 어떤 객체의 메서드나 속성 뒤에 마침표를 입력한 후 자동완성 기능을 활용할 수도 있음



```python
In [4]: b = [1,2,3]

In [5]: b.<Tab>
b.append()  b.count()   b.insert()  b.reverse()
b.clear()   b.extend()  b.pop()     b.sort()
b.copy()    b.index()   b.remove()
```

모듈도 똑같이 동작



```python
In [6]: import datetime

In [7]: datetime.<Tab>
datetime.date          datetime.MAXYEAR       datetime.time          datetime.tzinfo
datetime.datetime      datetime.MINYEAR       datetime.timedelta
datetime.datetime_CAPI sys           datetime.timezone
```

주피터 노트북과 IPython 5.0 이상 버전에서는 자동완성 목록이 일반 텍스트 출력이 아닌 드롭다운 형식으로 나타남


***NOTE_*** 탭을 눌렀을 때 화면에 출력 결과가 너무 많으면 초보자는 헷갈릴 수 있는데, <br>

IPython은 아예 _로 시작하는 내부 메서드와 속성을 제외한 결과를 보여줌<br>

물론 먼저 _를 입력하면 해당 메서드와 속성 선택 가능<br>

이런 메서드를 탭 자동완성 목록에 기본으로 넣고 싶다면 IPython 환경 설정에서 설정 가능<br>

자세한 내용은 IPython 문서 참고



탭 자동완성은 대화형 네임스페이스 검색과 객체 및 모듈 속성의 자동완성뿐만 아니라 <br>

파일 경로를 입력(파이썬 문자열 안에서도)한 후 탭을 누르면 입력한 문자열에 맞는 파일 경로를 컴퓨터의 파일 시스템 안에서 찾아 보여줌.



```python
dfds
```


```python
In [8]: datasets/movielens/<Tab>
datasets/movielens/movies.dat    datasets/movielens/README
datasets/movielens/ratings.dat   datasets/movielens/users.dat
```


```python
나중에 살펴볼 %run 명령어(2.2.5절 참조)와 조합하면 키 입력 줄일 수 있음<br>
또한 자동완성 기능을 사용하면 함수에서 이름을 가진 인자(=기호까지 포함해서)도 보여줌
```

### 2.2.4 자기관찰


변수 이름 앞이나 뒤에 ? 기호를 붙이면 그 객체에 대한 일반 정보 출력



```python
In [11]: b?
Type:        list
String form: [1, 2, 3]
Length:      3
Docstring:
Built-in mutable sequence.

If no argument is given, the constructor creates a new empty list.
The argument must be an iterable if specified.
```


```python
In [14]: print?
Docstring:
print(value, ..., sep=' ', end='\n', file=sys.stdout, flush=False)

Prints the values to a stream, or to sys.stdout by default.
Optional keyword arguments:
file:  a file-like object (stream); defaults to the current sys.stdout.
sep:   string inserted between values, default a space.
end:   string appended after the last value, default a newline.
flush: whether to forcibly flush the stream.
Type:      builtin_function_or_method
```

이 기능은 객체의 ***자기관찰***(인트로스펙션***introspection***)이라고 하는데, 만약 객체가 함수이거나 인스턴스 메서드라면 정의되어 있는 문서(docstring)를 출력<br>

IPython이나 주피터에서 사용 가능한 아래와 같은 함수를 작성했다고 하자.



```python
def add_numbers(a,b):
    """
    Add two numbers together
    
    Returns
    -------
    the_sum : type of arguments
    """
    return a + b
```

?기호를 사용해 문서 출력



```python
In [16]: add_numbers?
Signature: add_numbers(a, b)
Docstring:
Add two numbers together

Returns
-------
the_sum : type of arguments
File:      c:\users\user\<ipython-input-15-0eb10578c9b9>
Type:      function
```

??를 사용하면 가능한 경우 함수의 소스 코드도 보여줌



```python
In [17]: add_numbers??
Signature: add_numbers(a, b)
Source:
def add_numbers(a,b):
    """
    Add two numbers together

    Returns
    -------
    the_sum : type of arguments
    """
    return a + b
File:      c:\users\user\<ipython-input-15-0eb10578c9b9>
Type:      function
```

또한 ?는 표준 유닉스나 윈도우 명령행에서와 마찬가지로 IPython의 네임스페이스를 검색하는데 사용할 수도 있음.<br>

와일드카드(*) 기호와 함께 사용한 문자와 일치하는 모든 이름을 보여줌<br>

예를 들어 NumPy의 최상단 네임스페이스 안에서 load를 포함하는 모든 함수 목록을 가져올 수 있다.



```python
In [19]: np.*load*?
np.__loader__
np.load
np.loads
np.loadtxt
np.pkgload
```

### 2.2.5 %run 명령어


***%run*** 명령어를 사용하면 IPython 세션 안에서 파이썬 프로그램 파일을 불러와서 실행 가능<br>

다음과 같은 ipython_script_test.py 스크립트 파일이 있다고 하자.



```python
# ipython_script_test.py
def f(x,y,z):
    return (x+y)/z

a = 5
b = 6
c = 7.5

result = f(a,b,c)
```

이 스크립트 파일은 %run 명령을 사용해 다음처럼 실행 가능



```python
In [1]: %run ipython_script_test.py
```

스크립트 파일은 ***빈 네임스페이스***(다른 변수가 선언되지 않았거나 아무것도 임포트되지 않은 상태)에서 실행되므로<br>

명령행에서 python script.py 명령을 실행한 것과 동일하게 동작<br>

스크립트 파일에 정의된 모든 변수(임포트, 함수, 전역 변수)는 실행된 후 IPython에서 접근 가능



```python
In [2]: c
Out[2]: 7.5

In [3]: result
Out[3]: 1.4666666666666666
```

만약 파이썬 스크립트에 명령행 인자(sys.argv에 저장되는)를 넘겨야 한다면<br>

명령행에서 실행하는 것처럼 파일 경로 다음에 필요한 인자를 넘겨주면 된다.


***NOTE_*** 실행하려는 스크립트 파일에서 대화형 IPython 네임스페이스에 미리 선언된 변수에 접근해야 한다면 %run 대신 ***%run -i*** 명령 사용


주피터 노트북에서는 스크립트 파일을 코드 셀로 불러오는 ***%load 매직함수***를 사용할 수도 있다.



```python
In [1]: %load ipython_script_test.py

In [2]: # %load ipython_script_test.py
   ...: def f(x,y,z):
   ...:     return (x+y)/z
   ...:
   ...: a = 5
   ...: b = 6
   ...: c = 7.5
   ...:
   ...: result = f(a,b,c)
```

#### 실행 중인 코드 중지하기


%run을 통해 스크립트가 실행되고 있거나 오랜 실행 시간이 필요한 코드가 실행되고 있는 중간에 Ctrl-C를 누르면 KeyboardInterrupt 예외 발생.<br>

이 예외는 몇몇 특수한 경우를 제외한 거의 모든 파이썬 프로그램을 즉시 멈추도록 함.


***CAUTION_***

실행 중인 파이썬 코드가 컴파일된 확장 모듈에서 호출된 경우에는 Ctrl-C를 눌러도 프로그램이 즉각 멈추지 않는데, 

이런 경우에는 프로그램의 제어권이 파이썬 인터프리터로 되돌아올 때까지 기다리거나

심각한 경우 운영체제의 작업 관리자 메뉴를 이용해 파이썬 프로젝트를 강제로 종료



```python
```
