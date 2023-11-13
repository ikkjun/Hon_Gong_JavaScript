- [07 문서 객체 모델](#07문서-객체-모델)
  * [07-1 문서 객체 조작하기](#07-1-----------)
    + [DOMContentLoaded 이벤트](#domcontentloaded----)
    + [문서 객체 가져오기](#----------)
    + [글자 조작](#-----)
    + [속성 조작](#-----)
    + [스타일 조작](#------)
    + [문서 객체 생성하기](#----------)
      - [생성](#--)
      - [추가](#--)
    + [문서 객체 이동하기](#----------)
    + [문서 객체 제거하기](#----------)
    + [이벤트 설정하기](#--------)
  * [07-2 이벤트 활용](#07-2-------)
    + [이벤트 모델](#------)
    + [키보드 이벤트](#-------)
    + [이벤트 발생 객체](#---------)
    + [기본 이벤트 막기](#---------)
    + [글자 입력 양식 이벤트](#------------)
      - [1. 버튼](#1---)
      - [2. 글자 입력](#2------)
      - [3. 선택](#3---)
      - [4. 체크박스](#4-----)
      - [5. 라디오버튼](#5------)
    + [글자 입력 양식 이벤트](#-------------1)
    + [드롭다운 목록 활용하기](#------------)
    + [체크 박스 활용하기](#----------)
    + [라디오 박스](#라디오-박스)
    + [좀 더 알아보기](#--------)
      - [localStorage 객체](#localstorage---)



# 07 문서 객체 모델
## 07-1 문서 객체 조작하기

html, head, body, title, h1, di, span
- HTML: 요소(element)
- 자바스크립트: 문서 객체(document object)

문서 객체 모델(Document Object Model → DOM): 문서 객체를 조합하서 만든 전체적인 형태

### DOMContentLoaded 이벤트
문서 객체 조작할 때 DOMContentLoaded 이벤트 사용

document.body.innerHTML += '<h1></h1>'

innerHTML: 문자열 → += '<h1></h1>'

Uncaught TypeError: Cannot read properties of null (reading 'innerHTML')
위에서 부터 읽는 html특성상 아직 body태그가 만들어지지 않았는데 body를 조작하려고 해서 오류가 발생한다.

스크립트 태그를 사용할 수 있는 위치
1. head > script > document.addEventListener('DOMContentLoaded', () => {})
2. body > script // 맨 마지막 부분

### 문서 객체 가져오기
document.head
document.body
document.title

document.querySelector(선택자)
document.querySelectorAll(선택자)


### 글자 조작
textContent
innerHTML

### 속성 조작
setAttribute('이름', '값')
getAttribute('이름')
다만 표준에 있는 속성은 그냥 입력해도 된다.


### 스타일 조작
style.backgroundColor
style['background-color']

### 문서 객체 생성하기 
#### 생성
document.createElement(문서 객체 이름)
#### 추가
부모객체.appendChild(자식객체)
ex. document.body.appendChild(header)

### 문서 객체 이동하기
appendChild()

### 문서 객체 제거하기
문서 객체.parentNode.removeChild(문서 객체)
ex. h1.parentNode.removeChild(h1)

### 이벤트 설정하기
모든 문서 객체는 생성되거나 클릭되거나 마우스를 위에 올리거나 할 때 이벤트가 발생한다. 그리고 이 이벤트가 발생할 때 실행할 함수는 addEventListener() 메소드를 사용한다.

```javascript
<script>
문서 객체.addEventListener(이벤트 이름, 콜백 함수)
</script>
```


이벤트가 발생할 때 실행할 콜백 함수를 이벤트 리스너 또는 이벤트 핸들러라고 부른다.

이벤트를 제거할 때는 removeEventListener() 메소드를 사용한다.

```javascript
<script>
문서 객체.removeEventListener(이벤트 이름, 이벤트 리스너)
</script>
```

## 07-2 이벤트 활용
### 이벤트 모델
### 키보드 이벤트
### 이벤트 발생 객체
### 기본 이벤트 막기

### 글자 입력 양식 이벤트
#### 1. 버튼
#### 2. 글자 입력
#### 3. 선택
#### 4. 체크박스
#### 5. 라디오버튼

### 글자 입력 양식 이벤트
값을 추출할 때 value 속성 사용한다.
keydown → keypress → 입력양식에 값이 들어감! → keyup
입력양식을 활용한다면 keyup이벤트를 활용하기
change 이벤트: 입력양식 전체(해당 input태그 전체의 입력)에 값 입력을 마쳤을 때 실행된다. 

### 드롭다운 목록 활용하기

### 체크 박스 활용하기
어떤 대상의 true 또는 false속성을 선택할 때

### 라디오 박스
여러 대상 중에서 하나를 선택하는 경우
반드시 name속성을 지정해야 한다.

### 좀 더 알아보기
#### localStorage 객체
localStorage.getItem('키')
localStorage.setItem('키', '값')
localStorage.removeItem('키')
localStorage.clear()  // 전체 제거