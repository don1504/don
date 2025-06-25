Python에서 주의해야 할 점들
문법 관련 주의사항
들여쓰기 (Indentation)
Python은 들여쓰기로 코드 블록을 구분합니다
탭과 스페이스를 섞어 쓰면 안 됩니다
일관성 있게 스페이스 4개 또는 탭 사용

# 잘못된 예
# 올바른 예
if True:
print("Hello")  # 들여쓰기 없음 - 에러!
if True:
1234 print("Hello")  # 스페이스 4개, 4칸띄기기


대소문자 구분
Python은 대소문자를 구분합니다
Print와 print는 완전히 다른 것
# 잘못된 예
# 올바른 예
Print("Hello")  # 에러! (대문자 P)
print("Hello")  # 올바름





변수와 데이터 타입
변수명 규칙
숫자로 시작할 수 없음
특수문자 사용 불가 (밑줄 _ 제외)
예약어 사용 불가
# 잘못된 변수명
# 올바른 변수명
2name = "John"     # 숫자로 시작
my-name = "John"   # 하이픈 사용
class = "A"        # 예약어 사용
name2 = "John"
my_name = "John"
class_name = "A"


문자열 처리 주의사항
# 따옴표 주의
# 잘못된 경우
# 올바른 경우
text = "She said "Hello""  # 에러!
text = "She said \"Hello\""  # 올바름
text = 'She said "Hello"'   # 올바름



# 문자열과 숫자 연산
# 잘못된 경우
# 올바른 경우
age = 25
print("나이: " + age)   # 에러! 타입 불일치
age = 25
print("나이: " + str(age))   # 올바름
print(f"나이: {age}")        # 올바름 (f-string)









리스트와 인덱스
인덱스 범위 주의
my_list = [1, 2, 3]
print(my_list[3])  # 에러! 인덱스 범위 초과
print(my_list[2])  # 올바름 (마지막 요소)
print(my_list[-1]) # 올바름 (뒤에서 첫 번째)

리스트 복사 주의
list1 = [1, 2, 3]
list2 = list1        # 참조 복사 (같은 메모리)
list2.append(4)
print(list1)         # [1, 2, 3, 4] - 원본도 변경됨!

# 올바른 복사 방법
list2 = list1.copy()  # 또는 list1[:]

반복문과 조건문
무한 루프 주의
# 위험한 코드
while True:
    print("무한 루프!")  # Ctrl+C로 중단해야 함

# 안전한 코드
count = 0
while count < 10:
    print(f"카운트: {count}")
    count += 1  # 카운터 증가 잊지 말기!

조건문에서 할당 연산자 실수
x = 5
if x = 10:  # 에러! 할당 연산자 사용
    print("x는 10")

if x == 10:  # 올바름! 비교 연산자 사용
    print("x는 10")


불확실한 상황에서는 항상 보수적 판단
다중 안전장치 및 페일세이프 메커니즘
3. 상황별 세분화된 판단
날씨, 시간, 도로 조건 등 환경 요소 고려
법규 준수 및 교통 상황 적응
4. 예측 기반 의사결정
시간 계산을 통한 충돌 예방
다른 교통 참여자 행동 예측
이러한 if문들은 실제 자율주행 시스템의 핵심 의사결정 로직을 보여줍니다!



함수 관련
매개변수 기본값 주의
# 위험한 코드
def add_item(item, my_list=[]):
    my_list.append(item)
    return my_list

# 문제: 기본값이 공유됨
list1 = add_item("apple")
list2 = add_item("banana")
print(list2)  # ['apple', 'banana'] - 예상과 다름!

# 올바른 코드
def add_item(item, my_list=None):
    if my_list is None:
        my_list = []
    my_list.append(item)
    return my_list

예외 처리
예외 처리 습관화
# 위험한 코드
number = int(input("숫자 입력: "))  # 문자 입력 시 에러!

# 안전한 코드
try:
    number = int(input("숫자 입력: "))
    result = 10 / number
    print(f"결과: {result}")
except ValueError:
    print("숫자를 입력해주세요")
except ZeroDivisionError:
    print("0으로 나눌 수 없습니다")

파일 처리
파일 닫기 잊지 말기
# 위험한 코드
file = open("data.txt", "r")
data = file.read()
# file.close() 잊음!

# 안전한 코드
with open("data.txt", "r") as file:
    data = file.read()
# 자동으로 파일이 닫힘

성능 관련
문자열 연결 최적화
# 비효율적
result = ""
for i in range(1000):
    result += str(i)  # 매번 새로운 문자열 객체 생성

# 효율적
result = "".join(str(i) for i in range(1000))

일반적인 실수들
print문에서 괄호 빠뜨리기
# Python 2 스타일 (에러!)
print "Hello"

# Python 3 스타일 (올바름)
print("Hello")

들여쓰기 혼용
# 에러 발생하는 코드
if True:
    print("Hello")  # 스페이스 4개
	print("World")  # 탭 문자 - 에러!

전역변수 사용 주의
count = 0

def increment():
    global count  # global 키워드 필요
    count += 1

def increment_wrong():
    count += 1  # 에러! 지역변수로 인식

이런 점들을 주의하면서 코딩하면 Python을 더 안전하고 효율적으로 사용할 수 있어요!
