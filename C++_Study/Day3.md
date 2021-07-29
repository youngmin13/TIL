# Day2
## 2021-07-29

<br>

1. Chapter4 'The Object Life Cycle'
    - Exception
        - 크게 runtime_error, logic_error, language suppor error로 나뉜다.
        - try에서 throw한 exception을 catch에서 잡는데 이에 대해서는 조금 더 이해가 필요할 거 같다. 
        - stack에 쌓이면서 실행되는 순서를 이해하는 것이 중요할 듯
    - Copy
        - value만 가져오는 것과 주소까지 복사하는 것으로 나뉜다.
        - copy constructor
            - 원래 버퍼가 가리키는 데이터를 새로운 버퍼에 복사
        - copy assignment
            - operator=의 형식을 띄는 operator를 만들어주어야 한다.
            - 현재 버퍼를 해제한후 새로운 버퍼를 가리킨다.
    - Move
        - copy는 시간과 비용이 많이 든다. move를 사용하면 기존의 것에서 새로운 constructor를 만들지 않고 내용을 바로 가져온다. 기존의 것은 초기화.
        - rvalue vs lvalue
            - move는 rvalue를 사용한다.
            - rvalue는 name을 가지지 않고 일시적인 값만 가지기 떄문에 수정이 가능하여서 사용하는 것 같다. 조금 더 자세한 이해가 필요할 듯.

<br>

2. Chapter5 'Runtime Polymorphism'
    - interface
        - interface는 function signature를 정의한다. implementation에서 실제 함수의 기능을 만들어야한다.
        - Baseclass에서 Derivedclass로 inherite 해준다.
        - 상속받은 class가 baseclass의 함수를 사용할 경우 override를 해준다. baseclass의 private 부분은 derived에서 사용할 수 없다.
        - virtual
            - derivedclass가 baseclass의 method를 재정의해주려면 virtual을 사용한다. 
            - method에 = 0 을 추가하면 derivedclass를 추가할 수 있다.
            - virtual에서 destructor를 만들어주어야 memory leak을 막을 수 있다.
        - constructor injection
            - class의 constructor에 interface를 참조하여 instance가 수행할 것을 정한다.
            - 참조를 바꿀 수 없으므로 interface의 개체는 class의 수명동안 변경되지 않는다.
        - properly injection
            - pointer를 사용하기 때문에 참조를 바꿀 수 있다. (새 걸로 삽입 가능)
        - object의 lifecycle 에서 멤버의 기본 유형을 수정할 수 있으려면 properly를 사용한다. 다만 비용이 든다.
