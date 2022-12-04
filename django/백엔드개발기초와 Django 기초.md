# [Django] 백엔드개발기초와 Django 기초

1달뒤: 2022년 4월 24일
1일뒤: 2022년 3월 25일
7일뒤: 2022년 3월 31일
공부일: 2022/03/24
다씀?: Yes

## 웹의 동작 원리

---

Client는 요청을 보내고 Server는 요청을 받아 응답을한다. 서버도 Client가 될 수 있다.

## 프론트엔드와 백엔드

---

- 프론트엔드
    - 사용자 인터페이스
    - 사용자 입력
    - 데이터 출력
    - 주요 기술
        - HTML, CSS, JS, REACT, VUE.JS 등
- 백엔드
    - 시스템 관리 및 제어
    - 비즈니스 로직, 연산 수행
    - 데이터 베이스 관리
    - 프로그래밍 언어뿐만 아니라 운영체제에 대한 지식, DBMS에 대한 지식 등도 필요
    - 주요 기술
        - python django ubuntu java django c# oracle sqlite mysql 등


## 웹프레임워크

---

- **Framework와 Library의 차이점**


    | Framework | Library |
    | --- | --- |
    | 소프트웨어 개발을 위한 기능, 구조의 틀을 제공 | 소프트웨어 개발을 위한 기능을 제공 |
    | 시스템 흐름을 프레임워크가 제어함 | 시스템 흐름을 개발자가 제어함 |
- **Framework의 장점**
    - 효율적 : 이미 구현되어있는 코드로 시간과 비용을 절약하여 생산성이 높음
    - 품질 향상 : ㅅ
    - 유지보수 용이
- **Framework의 단점**
    - 별도 학습 필요
    - 기본 설계된 구조로 개발이 다소 제한적
- **언어별 웹 프레임워크**
    - php -larabel
    - python - django, flask
    - java -spring

## Django

---

- 개발속도 빠름
- 기본적으로 필요한 기능 제공
- 인증, 보안 부분들도 고려됨
- fullstack framework
- Python web framework
- MTV design pattern (Model - Template - View)
- 오픈소스
- 앱 단위로 프로젝트 구성
    - App = Django project를 구성하는 module
        - app name은 영문 복수형으로 생성
        - 장고 프로젝트 관점에서 관련된 기능을 모아둔 파이썬 파일

### 핵심 요소

- **python**
- **ORM(Object-Relational Mapping)**
    - **객체지향 언어**와 **관계형 데이터베이스**를 연결해주는 기술
    - **Models, QuerySet API** 등이 ORM에 포함
- **Templates**
    - 자체 템플릿 시스템으로 디자인과 로직을 분리하여 독립적 개발 가능
    - HTML 파일을 분리하여 **재사용**, 체계적으로 관리할 수 있음
    - HTML 파일에 include, if, for 등 템플릿 언어를 사용 가능
- **Forms**
    - **데이터의 유효성 검사**
    - 구성하고나 하는 형태 렌터링(HTML 태그 생성) → FORM 태그 자체를 생성해줌?
    - 제출하는 폼 데이터의 변경 확인
- **Authentication**
    - 시스템 인증과 권한부여 기본 제공
        - 인증 : 사용자가 누구인니 판별
        - 권한 : 인증된 사용자가 어떤 일을 할 수 있는지 결정
- **Admin**
    - 관리자 인터페이스 제공
    - 등록된 모델의 기본적인 조회, 추가, 수정, 삭제 기능 제공
    - 사용자 관리, 사용자 그룹 관리, 사용자 별 권한 기본 제공
- **Internationalization**
    - 동일한 소스코드로 텍스트의 번역, 날짜/시간/숫자의 포맷, 타임존의 지정 등과 같은 다국어 환경 제공
    - 개발자와 템플릿 작성자는 언어 및 문화에 맞게 번역하거나 형식 지정 가능
    - 특정 사용자의 기본 설정에 따라 웹 앱을 현지화
- **Security**
    - 대표적인 보안사항 기능 제공
    - CSRF( 교차 사이트 요청 위조) 보호
    - SQL 주입 보호

### 기본 구조

- MTV 디자인 패턴

    ![Untitled](%5BTHE%20ORIGIN%5D%201%20%E1%84%87%E1%85%A2%E1%86%A8%E1%84%8B%E1%85%A6%E1%86%AB%E1%84%83%E1%85%B3%E1%84%80%E1%85%A2%E1%84%87%E1%85%A1%E1%86%AF%E1%84%80%E1%85%B5%E1%84%8E%E1%85%A9%E1%84%8B%E1%85%AA%20Django%20%E1%84%80%E1%85%B5%E1%84%8E%E1%85%A9%207ec6ede335f0422f9ff8a5f4b12a7cc9/Untitled.png)

    | 구분 | 역할 | 파일 |
    | --- | --- | --- |
    | Model | 데이터 관리
    데이터베이스와 연결 및 실행 | models.py |
    | Template | 데이터 출력
    사용자에게 표현 방식 정의
    rendering data in the views | html |
    | View | controller 역할
    to get the requested data from the models
    create HTML pages that display the data from the Template
    비즈니스 로직을 처리 | views.py |


### 실행 흐름

![Untitled](%5BTHE%20ORIGIN%5D%201%20%E1%84%87%E1%85%A2%E1%86%A8%E1%84%8B%E1%85%A6%E1%86%AB%E1%84%83%E1%85%B3%E1%84%80%E1%85%A2%E1%84%87%E1%85%A1%E1%86%AF%E1%84%80%E1%85%B5%E1%84%8E%E1%85%A9%E1%84%8B%E1%85%AA%20Django%20%E1%84%80%E1%85%B5%E1%84%8E%E1%85%A9%207ec6ede335f0422f9ff8a5f4b12a7cc9/Untitled%201.png)

### 개발 환경 세팅

- python 설치
    - 사이트에서 찾아서 설치하는거 귀찮아서 `winget instll python3` 명령어로 설치
    - 근데 제대로 설치 안된건지 뭔지 PATH 설정도했고 옛날에 다운받은것도 삭제했는데 `python3` 명령어 입력했더니 윈도우 스토어 뜨길래 거기서 또 다운받고 하니 괜찮아짐.. winget은., 멀까..
