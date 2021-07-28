# Day2
## 2021-07-28

<br>

1. Chapter3 'Reference Types'
    - pointer
        - pointer에 array name을 할당하면 해당 array의 첫번째 요소를 가리키게 된다. 
        - void pointer는 dereferenced를 할 수 없기 때문에 arithmetic을 하기위해서는 type casting이 필요하다.
        - byte 단위의 저수준 작업을 하기 위해서는 std::byte pointer를 사용해야한다.
    - reference
        - reference는 직접적인 상수의 할당은 할 수 없다.
        - 할당된 함수의 다른 이름을 지정했다고 보는 것이 맞는 것 같다.
        - reference에 다른 값을 가지는 변수를 할당하면 기존에 할당했던 변수의 값도 변화한다.
    - this는 기존의 방식처럼 현재 struct의 변수들을 가르키는 것이다. 하지만 argument의 이름과 struct variable의 이름이 같은 경우를 대비하여 struct variable은 this를 붙여서 사용한다.
    - const
        - argument에 사용된 const는 해당 함수 안에서 argument의 변경을 금지한다는 뜻이다. (읽기는 가능하나 수정은 안됨)
        - member variable을 const로 사용한다면 수정할 수 없는 값이 된다.
    - member initializer
        - 객체의 멤버들을 초기화할 때 사용한다.
        - constructor와 비슷한 기능을 하는 것으로 보이나 body 전에 : 를 사용하여 초기화한다.

<br>

2. Chapter4 'The Object Life Cycle'
    - static 
        - static 변수는 프로그램이 종료될때까지 저장공간이 유지되기 때문에 함수 안에서 선언하더라도 값이 변경된다.
        - struct안에서 선언되었다면 밖에서 초기화를 해야한다.
    - dynamic
        - dynamic storage를 사용할때는 반드시 deallocate를 해주어야한다. user-mode code에서는 해주지 않더라도 종료되었을때 memory leak이 일어나지 않지만 kernel code에서는 os가 resource를 정리해주지 않기 때문이다.

....다음날 계속