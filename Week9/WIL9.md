# 기초 백엔드 스터디 9주차

복습: No
부제: lambda, stream
작성일시: 2023년 5월 28일 오후 9:12

## **람다와 스트림**

1. 람다
    1. 람다식: 함수(method)를 간단한 식으로 표현하는 방법
        
        *함수 = 일반적 용어/클래스에 독립적, method = 객체지향개념 용어/클래스에 종속적
        
    2. 람다식 작성하기
        
        ![1](https://github.com/yerin229/2023-1-OC-BE-Study/assets/127593340/b05b227a-d075-4e55-baa4-793381ceeae7)
        
2. 스트림: 다양한 데이터 소스를 표준화된 방법으로 다루기 위한 것
    1. 특징
        - 데이터 소스로부터 데이터 읽기만 할 뿐 변경 X
        - 일회용 (필요시 스트림 재생성)
        - 최종연산 전까지 중간연산 수행 X
    2. 생성
        
        ![2](https://github.com/yerin229/2023-1-OC-BE-Study/assets/127593340/a7770717-a9c5-44f1-9683-6b6eb938b01c)
        ![3](https://github.com/yerin229/2023-1-OC-BE-Study/assets/127593340/e60ebf68-2cf4-4bf2-90ae-080f1abea552)
        ![4](https://github.com/yerin229/2023-1-OC-BE-Study/assets/127593340/969acb60-377c-47e4-91ed-ac405a8247a3)
        

## **Optional**

- Optional<T>: null이 올 수 있는 값을 감싸는 Wrapper 클래스
    
               참조하더라도 NPE가 발생하지 않도록 도와줌
    
    *NPE(NullPointerException): 피하기 위해 null 검사 필요 → 코드 복잡&번거로움
    
- Optional 생성하기
    - 값이 없는 경우: Optional.empty()로 생성
        - 내부에서 static 변수로 EMPTY 객체 미리 생성해 가지고 있음 → 1개의 EMPTY 객체 공유함 → 메모리 절약
    - 값이 Null이 아닌 경우: Optional.of()로 생성
    - 값이 Null일 수도, 아닐 수도 있는 경우: Optional.ofNillbale()로 생성
        - 이후에 orElse나 orElseGet 메소드를 이용해 값이 없는 경우라도 안전하게 값을 가져올 수 있음
