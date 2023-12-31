# 06. 객체
## 06-1 객체의 기본
### 객체
const product = {
  제품명: '건조 망고'
  유형: '당절임',
  성분: '망고, 설탕'
  원산지: '필리핀'
  eat: function () {
    console.log('망고인데')
  }
}

product.제품명
product.유형
product.성분
product.원산지

### 동적으로 객체 속성 추가 / 제거

## 06-2 객체의 속성과 메소드 사용하기
기본 자료형 → 스택에 값을 저장 → 속성과 메서드를 가질 수 없다.
- 숫자
- 문자열
- 불
객체 자료형 → 스택과 힙을 연결 → 속성과 메서드를 가질 수 있다.
- 함수
- 배열
- 객체
- 이외 전부

함수를 객체처럼 쓰는 언어는 함수를 "일급 객체(first-class object)로 다룬다"라고 표현한다.

### 기본 자료형의 일시적 승급
우너래 기본 자료형은 속성과 메소드를 가질 수 없다. 그런데 자바스크립트는 사용의 편리성을 위해서 기본 자료형의 속성과 메소드를 호출할 때(기본 자료형 뒤 에 온점을 찍고 무언가 하려고 하면) 일시적으로 기본 자료형을 객체로 승급시킨다. 그래서 속성과 메소드를 사용할 수 있다.

### 프로토타입으로 메소드 추가하기
어떤 객체의 prototype이라는 속성이 바로 객체 전용 옷(틀)이라고 할 수 있다. protolype 객체에 속성과 메소드를 추가하면 모든 객체(와 기본 자료형)에서 해당 속성과 메소드를 사용할 수 있다.

### Number 객체
- toFixed()
- isNaN(), isFinite()

### String 객체
- trim()
- split()

### JSON 객체


### Math 객체
- floor(10.1)
- ceil(10.1)
- round(10.1)
- max(1,2,3)
- random() ex) Math.floor(Math.random() * 50)

### 외부 script 파일 읽어 들이기

## 06-3 객체와 배열 고급
