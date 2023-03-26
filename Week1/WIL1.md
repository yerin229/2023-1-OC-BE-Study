# 기초 백엔드 스터디 1주차

복습: No
부제: API, MVC, Restful
작성일시: 2023년 3월 26일 오전 2:48

### [웹 개발 방법]

1. 정적 컨텐츠
2. MVC와 템플릿 엔진 (가장 많이 씀)
3. API

### 1. 정적 컨텐츠

- 서버에서 하는 것 없이 파일을 그냥 그대로 웹 브라우저에 전달

![Untitled](%E1%84%80%E1%85%B5%E1%84%8E%E1%85%A9%20%E1%84%87%E1%85%A2%E1%86%A8%E1%84%8B%E1%85%A6%E1%86%AB%E1%84%83%E1%85%B3%20%E1%84%89%E1%85%B3%E1%84%90%E1%85%A5%E1%84%83%E1%85%B5%201%E1%84%8C%E1%85%AE%E1%84%8E%E1%85%A1%2065b1f5e36791419991d8ef3a264644a8/Untitled.png)

### 2. MVC와 템플릿 엔진

- 서버에서 HTML을 변형해서 웹 브라우저에 전달
- Model1 방식: 예전에는 controller와 view가 나뉘지 않고 view에서 모든게 다 있음(JSP)
- MVC 방식: Model, View, Controller
    - View: 화면 그리는 데 집중
    - Model&Controller: 비즈니스 로직, 내부 관련 처리 집중

![Untitled](%E1%84%80%E1%85%B5%E1%84%8E%E1%85%A9%20%E1%84%87%E1%85%A2%E1%86%A8%E1%84%8B%E1%85%A6%E1%86%AB%E1%84%83%E1%85%B3%20%E1%84%89%E1%85%B3%E1%84%90%E1%85%A5%E1%84%83%E1%85%B5%201%E1%84%8C%E1%85%AE%E1%84%8E%E1%85%A1%2065b1f5e36791419991d8ef3a264644a8/Untitled%201.png)

### 3. API

- JASON(데이터 구조 포맷)으로 client에게 data 전달
    - API로 data만 전달해주면 화면은 client가 알아서 그리고 정리
- @ResponseBody 사용
    - HTTP의 BODY에 문자 내용 직접 반환
    - viewResolver 대신 HttpMessageConverter 동작
    - 기본 문자 처리: StringHttpMessageConverter
    - 기본 객체 처리: MappingJackson2HttpMessageConverter
    - byte 처리 등등 기타 여러 HrrpMessageConverter가 기본으로 등록되어 있음
- REST API
    - REST(자원을 이름으로 구분해 해당 자원의 상태를 주고받는 모든 것) 기반으로 서비스 API 구현
    - REST API  제공하는 웹 서비스 = RESTful하다