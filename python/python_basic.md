# I. 변수 할당
```py
varNum = 5
print(varNum)
varNum = 10
print(varNum)
>> 5
   10
```
- 변수명에 알파벳, 숫자, 밑줄 포함 가능
- 변수명의 시작을 숫자로 할 수 없음
- 예약어를 변수명으로 사용할 수 없음
- 새 값을 할당하면 값이 업데이트 됨

# II. 데이터 자료형
## 1. 단일 데이터
- 숫자
  - int : 정수
  - float : 실수
- 문자열(str)
  - `input()`으로 입력받으면 모두 문자열
- 불린
  - True / False
## 2. 리스트
>`list = [a, b, c, d ...]`
  - `sum()` : 리스트 내 요소들의 합
  - `min()` : 리스트 내 요소중 가장 작은 값
  - `max()` : 리스트 내 요소중 가장 큰 값
  - `sorted()` : 리스트 내 요소의 정렬
  - `remove()` : 리스트 내 특정요소 삭제
  - `pop()` : 리스트의 맨 뒤 요소를 삭제
  - `zip()`
    ```py
    foods = []
    sides = []
    lunch = zip(foods, sides)
    ```

### 컴프리헨션
> 하나 이상의 iterator로부터 파이썬의 자료구조를 만드는 방법
  ```py
  mylist = [i for i in range(10)]
  print(mylist)
  >> [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]

  # 1 부터 10,000까지 중 7의 갯수
  str(list(range(1, 10001))).count('7')

  sum([str(x).count('7') for x in range(1, 10001)])
  ```

## 3. 튜플
> `tuple = (a, b, c, d ...)`
  - 수정이 안되므로 처음 지정할때 값을 다 넣기
  - 수정은 안 되나 `(tuple1) + (tuple2)`로 list의 `.append`와 같은 결과
    - 한 가지 요소만 더할 경우 ` + (a,)` 콤마 넣기
- 처리 속도가 빠르다
- type이 tuple 인 이유?
  ```py
  a = ''
  b = 1
  c = ['a', 'b', ['a', b], (a, 'c')]
  for b in c:
    a = b
  print(type(a))
  ```

## 4. 딕셔너리
### 기본
> `dic = {a : 1, b : 2, c = 3}`
  ```py
  dic[a]
  >> 1
  ```
- key와 value의 쌍으로 구성, key값은 unique
- 순서가 없어서 인덱싱, 슬라이싱 불가

### 함수
- 예약어 목록
```py
import keyword
keyword.kwlist
>>
# if 조건문
if
elif : 실행문1이 False일때 elif 다음의 조건문
else : if문의 실행문1이 False일 경우~

# for 반복문
for

# while 반복문
while
pass
break : 반복문 중단
continue : 

# 논리
False : 논리연산자 불일치
True : 논리연산자 일치
and : 논리 곱(~ 이고 ~)
not
or
in
is

# 함수
def : 함수 시작
class : 클래스 객체
lambda
return


# 모듈
import
from
as : 모듈약칭 설정

None : 값이 없음

# 예외처리
try
except : 
finally : 에러가 나더라도 이후문장 실행

assert : 가정 설정문?
async : 비동기 프로그래밍?
await

del : 값 제거

global : 전역변수로 지정
nonlocal
raise

with
yield
```
- `.keys()` : 딕셔너리의 키값을 반환
- `.values()` : 딕셔너리의 밸류값을 반환
- `items()` : 딕셔너리의 키와 밸류값을 동시에 반환
- `.update()` : 괄호안의 딕셔너리와 .앞의 딕셔너리를 합함
- dic[key]

### 활용
- 단어장 만들기
  ```py
  menu = '''
  ---선택메뉴---
  1. 단어 등록
  2. 단어 검색
  3. 모든 단어 보기
  0. 종료하기
  ----------------------------------------
  '''
  list = []
  dict = {}
  while True:
      print(menu)
      choice = input('선택:')

      if choice == '1':
          input_word = input('새 단어:')
          list.append(input_word)
          dict[input_word] = input(f'{input_word}의 뜻:')
          print('-' * 30)

      elif choice == '2':
          search_word = input('검색할 단어:')
          if search_word in list:
              print(f'{search_word}의 뜻 : {dict[search_word]}')
          else:
              print(f'미등록 단어입니다')
          print('-' * 30)

      
      elif choice == '3':
          for key, value in dict.items():
              print(f'{key} : {value}')
          print('-' * 30)


      elif choice == '0':
          break

      else:
          print('잘못 입력하셨습니다')
          print('-' * 30)
  ```

## 5. 세트
> `set = {a, b, c, d ...}`
- 키만 모아놓은 딕셔너리
- 중복이 제거됨(딕셔너리의 키가 unique key 이므로)
  ```py
  a = set('Hello')
  print(a)
  >> {'e, 'H', 'l', 'o'}
  ```
### 집합
- insertion

# III. 연산자
> 프로그래밍 언어의 시작 : 빠른 연산을 위해
## 1. 산술연산자
- `+` : 덧셈, `+=` : a = a + 1
- `-` : 뺄셈, `-+` : a = a - 1
- `*` : 곱셈, `*=` : a = a * 1
- `**` : 거듭제곱, `**=` : a = a ** 1
- `/` : 나눗셈, `/=` : a = a / 1
- `//` : 몫, `//=` : a = a // 1
- `%` : 나머지, `%=` : a = a % 1

## 2. 관계연산자
- `>` : 왼쪽이 크다
- `<` : 오른쪽이 크다
- `==` : 같다
- `!=` : 같지 않다
- `<=` : 오른쪽이 크거나 같다
- `>=` : 왼쪽이 크거나 같다

## 3. 논리연산자
> 결과값이 True / False
- `and`(논리곱) : 둘다 참이어야 참
- `or`(논리합) : 둘중 하나만 참이어도 참
- `not`(논리부정) : 참이면 거짓, 거짓이면 참
- 멤버쉽연산자
  - `in`
  - `not in`

# IV. 조건문, 반복문
## 1. if문
```py
if 조건문1:
  실행문1
# 조건문이 참이면 실행문1 실행

elif 조건문2:
  실행문2
# 조건문1이 거짓이고, 조건문2가 참이면 실행문2 실행

else:
  실행문 3
# 조건문1, 2가 모두 거짓이면 실행문3 실행
```
- 주민번호로 정보얻기
  ```py
  num = input('주민번호를 입력하세요 :').split('-')
  if num[1][0] == '1' or num[1][0] == '3':
      sex = '남성'
  elif num[1][0] == '2' or num[1][0] == '4':
      sex = '여성'
  year = int(num[0][0:2])
  if num[1][0] == '1' or num[1][0] == '2':
      year += 1900
  elif num[1][0] == '3' or num[1][0] == '4':
      year += 2000
  print(f'{year}년 {num[0][2:4]}월 {num[0][4:6]}일, {2023 - year + 1}세, {sex}')
  ```
- 자동주문머신
  ```py
  burger_single_price = [4300, 4900, 5400]
  burger_set_price = [6700, 7200, 7700]

  menu = f'''[맘스터치 키오스크]
  -----------------------
  - 싸이버거 : 단품 {burger_single_price[0]}원, 세트 {burger_set_price[0]}원
  - 화이트갈릭버거 : 단품 {burger_single_price[1]}원, 세트 {burger_set_price[1]}원
  - 인크레더블버거 : 단품 {burger_single_price[2]}원, 세트 {burger_set_price[2]}원
  -----------------------
  원하시는 버거갯수를 입력하세요
  '''
  print(menu)
  burger1_isset = 0
  burger2_isset = 0
  burger3_isset = 0

  burger1 = int(input('싸이버거를 몇개 주문하시나요? :'))
  if burger1 >= 1:
      burger1_isset = int(input('그중에 세트는 몇개 주문하시나요?'))
      if burger1_isset <= burger1:
          pass
      else:
          print('다시 입력해 주세요')

  burger2 = int(input('화이트갈릭버거를 몇개 주문하시나요? :'))
  if burger2 >= 1:
      burger2_isset = int(input('그중에 세트는 몇개 주문하시나요?'))
      if burger2_isset <= burger2:
          pass
      else:
          print('다시 입력해 주세요')

  burger3 = int(input('인크레더블버거를 몇개 주문하시나요? :'))
  if burger3 >= 1:
      burger3_isset = int(input('그중에 세트는 몇개 주문하시나요?'))
      if burger3_isset <= burger3:
          pass
      else:
          print('다시 입력해 주세요')

  total = (burger1 - burger1_isset) * burger_single_price[0] + burger1_isset * burger_set_price[0] + (burger2 - burger2_isset) * burger_single_price[1] + burger2_isset * burger_set_price[1] + (burger3 - burger3_isset) * burger_single_price[2] + burger3_isset * burger_set_price[2]

  print(f'현재까지 주문 총액은 {total}원 입니다.')

  side1_price = 1800
  side2_price = 2000

  side_menu = f'''[사이드메뉴]
  -----------------------
  - 코울슬로 : {side1_price}원
  - 콘샐러드 : {side2_price}원
  -----------------------
  원하시는 사이드메뉴 갯수를 입력하세요
  '''
  print(side_menu)
  side1 = int(input('코울슬로를 몇개 주문하시나요? :'))
  side2 = int(input('콘샐러드를 몇개 주문하시나요? :'))

  side_total = side1 * side1_price + side2 * side2_price
  print(f'현재까지 주문 총액은 {total + side_total}원 입니다.')
  bill = int(input('돈을 넣어 주세요'))

  if bill > total + side_total:
      print(f'주문해주셔서 감사합니다. 거스름돈 {bill - total + side_total}원 돌려드리겠습니다.')

  elif bill == total + side_total:
      print('주문해주셔서 감사합니다.')
  else:
      print(f'돈이 {total + side_total - bill}원 부족합니다.')
  ```
### for문
- 기본 형식
  ```py
  for num in range(1, 10, 2):
    print(f'{num} 안녕하세요')
  >> 1 안녕하세요
     3 안녕하세요
    5 안녕하세요
    ...
    9 안녕하세요
  # range(1, 10, 2) / 1: 해당숫자 부터 시작 / 10: 해당숫자-1 까지 반복 / 2: 간격
  ```
- 1부터 n까지 더하기
  ```py
  # for문 사용
  total = 0
  for i in range(1, 10001):
    total += i

  # sum() 사용
  sum(list(range(1, 10001)))
  ```

- 괄호 짝 맞추기
  ```py
  a_list = list(input('괄호 :'))
  a = 0
  for _ in a_list:
      if _ == '(':
          a += 1
      elif _ == ')':
          a -= 1
  if a_list[0] == '(' and a_list[-1] == ')' and a == 0:
      print('결과 : True')
  else:
      print('결과 : False')
  ```
- 구구단
  ```py
  n = int(input(f'몇단을 출력할까요? :'))
  print('-' * 30)
  for _ in range(1, 10):
      print(f'{n} X {_} = {n*_:>2}') 
  ```

## 2. while문
> for와 다르게 무한 반복, 탈출 조건을 할당해야 함
- 기본구분
  ```py
  while True:
    실행문1
    if 조건문1:
      break
  ```

# V. 함수
> 함수 \< 모듈 \< 패키지
- lambda : 함수를 간단하게 나타냄
- map()
- filter()
- 재귀함수

# VI. 모듈
> import 모듈명 as 약자

## 1. urllib
> import urllib,
> import ssl
- 외부 사이트에서 가져오기
  ```py
  import urllib.request
  import ssl

  ctx = ssl._create_unverified_context()

  # 환율정보 페이지 불러오기
  print("[환율정보 불러오기]")
  URL = "https://search.naver.com/search.naver?where=nexearch&sm=top_hty&fbm=1&ie=utf8&query=%ED%99%98%EC%9C%A8"
  page = urllib.request.urlopen(URL, context=ctx)  
  text = page.read().decode("utf8")  # 해당 페이지의 소스코드
  # print(text)

  # 환율정보 가져오기: 기준시간 
  searchText = 'class="grp_info"> <em>'
  # 해당 유니크 텍스트의 가장 앞 부분의 위치를 찾음
  where = text.find(searchText)  #소스코드에서 해당 문자열의 시작위치
  targetInfo = text[where+len(searchText):where+len(searchText)+16]
  print(f'-환율기준시간: {targetInfo}')

  # 환율정보 가져오기: 달러
  searchText = '<span>미국 <em>USD</em></span></a></th> <td><span>'
  where = text.find(searchText)
  targetInfo = text[where+len(searchText):where+len(searchText)+8] 
  print(f'-달러당: {targetInfo}')

  #환율정보 가져오기: 유로
  searchText = '<span>유럽연합 <em>EUR</em></span></a></th> <td><span>'
  where = text.find(searchText)
  targetInfo = text[where+len(searchText):where+len(searchText)+8]
  print(f'-유로: {targetInfo}')

  # 환율정보 가져오기: 위안
  searchText = '<span>중국 <em>CNY</em></span></a></th> <td><span>'
  where = text.find(searchText)
  targetInfo = text[where+len(searchText):where+len(searchText)+6] 
  print(f'-위안: {targetInfo}')

  # 환율정보 가져오기: 엔화
  searchText = '<span><em>JPY 100</em>일본 </span></a></th> <td><span>'
  where = text.find(searchText)
  targetInfo = text[where+len(searchText):where+len(searchText)+6] 
  print(f'-엔화: {targetInfo}')
  ```

## 2. random
> import random
- 주사위 게임 승자 구하기
  ```py
  import random
  part = ['A', 'B', 'C', 'D']
  n = []
  for _ in range(4):
      n.append(random.randint(1, 6))
  print(n)
  if n.count(max(n)) >= 2:
      print('승부가 나지 않았습니다')
  else:
      print(f'{part[n.index(max(n))]}님이 승리했습니다')
  ```
- 랜덤 가위바위보
  ```py
  import random
  rsp = ['가위', '바위', '보']
  player = ['쫑댕', '소방']
  player1_win = 0
  player2_win = 0
  draw = 0
  print(f'{player[0]} vs {player[1]} 랜덤 {rsp[0]} {rsp[1]} {rsp[2]} 게임!')
  print('-' * 30)
  n = int(input('몇 번 게임할 건가요?: '))
  print()
  for _ in range(n):
      print(f'<<{_ + 1} 번째 게임!!>>')
      player_1 = random.choice(rsp)
      player_2 = random.choice(rsp)
      print(f'결과 => {player[0]}: [{player_1}], {player[1]}: [{player_2}]')
      if player_1 == player_2:
          print('비겼습니다.')
          draw += 1
      elif (player_1 == '가위' and player_2 == '보') or (player_1 == '바위' and player_2 == '가위') or (player_1 == '보' and player_2 == '바위'):
        print(f' {player[0]}이가 이겼습니다!!!')
        player1_win += 1
      else:
          print(f'{player[1]}이가 이겼습니다!!!')
          player2_win += 1

      print()
  print('-' * 30)
  print(f'최종 결과 : {player[0]} {player1_win}승!, {player[1]} {player2_win}승!')
  ```
## 3. datetime
- 기본 구문
  ```py
  import datetime
  now = datetime.datetime.now()
  # 현재 시각

  now.strftime('지금 시각은 %Y년 %m월 %d일 %H시 %M분 %S초 입니다.')
  # 시간 포맷하는 함수
  ```

# VII. 예외처리
- 기본 구문
  ```py
  try:
    실행문1
  except 에러명1:
    실행문2
  # 실행문1을 실행하다 에러1이 나면 에러를 출력하지 않고 실행문2를 실행한다
  ```


# VIII. 입출력
## 1. 관련 함수
- `eval()` : 문자열을 숫자처럼 계산
  ```py
  eval('3' + '4')
  >> 7
  ```
- escape 문자
  
  문자|역할|설명
  |--|--|--|
  |\n|새줄로 이동|enter|
  |\t|다음탭 이동|tab|
  |\b|뒤로 한칸 이동|backspace|
  |`\\`|\출력|
  |`\'`|'출력|
  |`\*`|*출력|

- 특수문자
  - 문자 데이터를 변환할 국제적인 기준 : ASCII, UNICODE
  - `chr()` : 정수 $\rightarrow$ 문자로 변환
  - `ord()` : 문자 $\rightarrow$ 정수로 변환

    |기호|코드|
    |--|--|
    |★|'\u2605'|

## 2. 포매팅
```py
print('덧셈 : %d + %d = %d' % (num1, num2, num1 + num2))
# %d 자리에 포매팅, d(십진수), b(이진수), s(문자열)...

print(f'덧셈: {num1} + {num2} = {num1 + num2}')
# f'string

print(f'덧셈: {num1} + {num2:>3} = {num1 + num2}')
# >n : n(자릿수), >(우측정렬), <(좌측정렬), ^(가운데정렬)
```
```py
print('%d' % 123)
>> 123
# 십진수로 포맷

print('%5d' % 123)
>>   123
# 십진수의 5자리로 포맷

print('%05d' % 123)
>> 00123
# 십진수의 5자리 빈칸 0으로 포맷

print('%f' % 123.45)
>> 123.450000
# 숫자 입력 없으면 소수 6째 자리까지 포맷

print('%7.1f' % 123.45)
>>   123.5
# 7자리에 소수 첫째줄까지

print('%7.3f' % 123.45)
>> 123.450
# 7자리에 소수 셋째줄까지
```

## 3. 인덱싱, 슬라이싱
- 데이터에 순서가 있어야 한다

  ```py
  a = agriculture
  a[1:3]
  >> gr
  # 인덱스 순서는 첫 글자가 0부터 시작, :뒤의 숫자 바로 전까지 출력

  a = agriculture
  a[1:3:-1]
  >> rg
  # 세 번째 숫자가 -1이 입력되면 거꾸로 출력

  a = agriculture
  a[-3:-1]
  >> ur
  # 오른쪽 끝에서 부터 -1 ~ 로 세어 출력하는 것도 가능
  ```
  ```py
  print('%s' % 'Python')
  >> Python

  print('%10s' % 'Python')
  >>     Python
  # 10자리로 우측정렬한다
  # 문자 간 공백이 있을 경우 공백을 사이에 두고 양측으로 정렬됨
  ```
  ```py
  "I eat {0} apples".format(3)
  >> "I eat 3 apples"

  "I ate {0} apples. So, I'm {1}".format(10, 'full')
  >> "I ate 10 apples. So, I'm full"
  ```
- `count()` : 문자개수 세기
- `find()` : 위치 확인, 없는 문자를 입력하면 -1 반환
- `index()` : 위치 확인, 없는 문자를 입력하면 에러 반환
- `join()` : 문자열에서만 동작, `.join()` 앞의 문자를 괄호 안의 문자 사이에 넣는다
  ```py
  a = "!"
  a.join('파이썬')
  '파!이!썬'
  ```
- `enumerate()` : 인덱스와 값을 동시에 반환
  ```py
  list = [1, 2, 3, 4, 5, 6, 7, 8]
  for idx, v in enumerate(list):
      print(f'인덱스 : {idx}, 값 : {v}')
  ```
- `upper()`, `lower()` : 대문자로, 소문자로
- `strip()`, `lstrip()`, `rstrip()` : 전체 공백지우기, 왼쪽 오른쪽 공백 지우기
- `replace()` : 문자열 바꾸기
- `split()` : 문자열 나누기
  - `split()` 괄호 안의 문자가 없을 경우 리스트를 통으로 반환

# 9. 관련 링크
[파이썬 자습서](https://docs.python.org/ko/3.10/tutorial/datastructures.html#list-comprehensions)