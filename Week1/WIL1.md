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

![Untitled](https://user-images.githubusercontent.com/127593340/227830301-a45624a2-8ef5-4fe3-854b-69a9eec06d59.png)

### 2. MVC와 템플릿 엔진

- 서버에서 HTML을 변형해서 웹 브라우저에 전달
- Model1 방식: 예전에는 controller와 view가 나뉘지 않고 view에서 모든게 다 있음(JSP)
- MVC 방식: Model, View, Controller
    - View: 화면 그리는 데 집중
    - Model&Controller: 비즈니스 로직, 내부 관련 처리 집중

![Untitled 1](https://user-images.githubusercontent.com/127593340/227830296-d3d45b34-46e9-4cb5-bdfd-7e2bd1c8c95e.png)

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
