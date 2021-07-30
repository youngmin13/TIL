# Day4
## 2021-07-30

<br>

1. Chapter6 'Compile-Time Polymorphism'
    - Templates
        - template<typename T> 와 같은 형태로 사용
        - 일반적으로 타입을 사용할 수 있다.
        - Named-conversion-functions
            - const_cast
                - const 타입의 변수를 modify하여 사용할 수 있다.
            - static_cast
                - implicit conversion을 할때 사용
            - reinterpret_cast
                - memory interpret을 제어하기위해 사용
            - narrow_cast
                - 변환시 변수의 범위가 줄어든다.
        - Concepts
            - type이 가져야하는 요구조건을 말한다.
            - type traits
                - parameter의 유효성을 검사
        - Requirements
            - template parameter에 제약조건을 의미

<br>

2. Chpter7 'Expressions'
    - Operators
        - logical operator: &, |, ^, ~, <<, >>, &&, ||, !
        - arithmetic operator
            - unary arithmetic operator
            - binary arithmetic operator
        - assignment operator
        - increment, decrement operator
        - comparison operator
        - member access operator
        - ternary conditional operator: x > 0 ? 1 : 0
        - comma operator
        - Operator overloading
            - 직접 연산자를 정의하여 지정 동작을 수행
    - Type conversions
        - implicit type conversions
            - 중괄호를 사용하면 안된다.
        - explicit type conversions
        - user defined type conversions
            - 사용자가 직접 conversion을 만들어 주는 것
    - Constant expression
        - 성능 및 안전 이유로 runtime 이 아니라 compile time에 계산 수행
        - constexpr을 사용하여 컴파일러의 범위 확장 가능
    - Volatile expression
        - dead store: 변수를 사용하지 않고 초기화를 두 번 해주면 앞의 초기화는 의미가 없어진다.
        - redundant load: 변수를 변경하지 않고 여러번 assignment 해준다.