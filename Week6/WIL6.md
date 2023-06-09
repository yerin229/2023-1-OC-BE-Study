# 기초 백엔드 스터디 6주차

복습: No
부제: interface, 추상클래스
작성일시: 2023년 5월 14일 오후 7:58

## <**추상 클래스와 인터페이스>**

1. 추상 클래스
    
    : 추상 메서드를 선언, 상속을 통해 자손 클래스에서 완성하도록 유도하는 클래스 (미완성 설계도)
    
    - 상속을 위한 클래스 ⇒ 객체 생성 X
    - 추상 메서드: 선언부만 작성하고 구현부 작성 X ⇒ 상속받는 클래에 따라 달라질 수 있음
    
    ```jsx
    abstract class 클래스이름 {
        ...
        public abstract void 메서드이름();
    }
    ```
    
2. 인터페이스
    
    : 다른 클래스를 작성하는데 도움을 주는 목적으로 작성 (기본 설계도)
    
    - 다중상속(구현) 가능
    - 일반 메서드, 멤버 변수를 구성원으로 가질 수 있음
    
    ```jsx
    interface 인터페이스이름 {
        public static final 상수이름 = 값;
        public abstract void 메서드이름();
    }
    ```
    
3. 공통점&차이점
    - 공통점
        - 추상메서드 사용 가능 (추상클래스가 인터페이스의 역할 다 수행 가능)
    - 차이점
        - 추상클래스는 IS - A (~이다), 인터페이스는 HAS - A (~을 할 수 있는)
            - 자바의 특성: 1개의 클래스만 상속 가능
                
                ⇒ 추상 클래스 상속 = 클래스의 구분
                
                ⇒ 인터페이스 구현 = 할 수 있는 기능들 구현
                
        - 공통된 기능의 사용 여부
            - 모든 클래스가 인터페이스를 사용해 기본 틀 구성
                
                ⇒ 공통으로 필요한 기능들도 모든 클래스에서 오버라이딩해 재정의 필요
                

[추상클래스 인터페이스 예제]

![1](https://github.com/yerin229/2023-1-OC-BE-Study/assets/127593340/2a4f89c1-95b5-48e3-bc5f-9acb2acadeb2)

- 인간은 동물과 생명체 상속, 생명체들은 인간과 동물 상속
- 각각 가능한 기능들을 인터페이스로 구현


## <**static과 final 그리고 불변 객체>**

1. static
    
    : 객체 없이 사용할 수 있는 필드와 메소드(공용 데이터에 해당하거나 인스턴스 필드를 포함하지 않는 메소드) 선언 ⇒ 전역 변수
    
2. final
    
    : 저장되는 값이 최종적인 값 ⇒ 수정 불가
    
3. 불변객체
    
    : 객체 생성 이후 내부의 상태 변하지 X
    
    - read-only 메소드만 제공
        
        (객체 내부 상태 제공하는 메소드 제공 X or  방어적 복사 통해 제공)
        
    - 대표적 예시: String
4. final, 불변객체 사용 이유
    - Thread-Safe해 병렬프로그램에 유용, 동기화 고려X
        - 공유자원이 불변의 자원이므로
    - Failure Atomic 메소드 만들 수 있음
        - 어떤 예외가 발생해도 메소드 호출 전의 상태 유지 가능
    - Cache나 Map, Set 등의 요소로 활용하기 적합
        - 데이터가 저장된 후 다른 부가작업 고려 X ⇒ 다른 자료구조 사용에 용이
    - Side Effect 피해 오류 가능성 최소화
        - Side Effect: 변수의 값 변경 or 필드 값 설정 등의 변화 발생하는 효과
        - 기본적으로 값의 수정 불가능 ⇒ 변경 가능성 적음&객체의 생성과 사용 상당히 제한 ⇒ 순수 함수들로 구성
    - 다른 사람이 작성한 함수 예측가능, 안전하게 사용
        - 협업시 다른 사람이 개발한 함수를 위험없이 이용 가능
    - GC의 성능 높일 수 있음
        - 컨테이너는 컨테이너가 참조하는 가장 젊은 객체들보다 더  젊음 ⇒ GC 수행시 컨테이너 하위의 불변객체들 skip
