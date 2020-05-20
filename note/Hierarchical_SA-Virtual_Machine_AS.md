# Hierarchical_SA-Virtual_Machine_AS

#### Virtual Machine(VM) Architecture Style

- 존재하는 시스템(physical machine) 위에 올라가는 시스템
- virtual abstraction, a set of attributes and operations
- emulation software: 한 시스템에서 다른 시스템을 복사하여 두 번째 시스템이 첫 번째 시스템을 따라 행동하는 것

#### Example

- Java Virtual Machine(JVM)

  ![image](https://user-images.githubusercontent.com/61573968/81662553-b6ad0480-9478-11ea-80c2-8bdf52718866.png)

  - Java Source Code에서 Java Compiler하면 JVM만 있으면 Java Byte Code를 실행할 수 있음

  <img src="https://user-images.githubusercontent.com/61573968/81663528-bb25ed00-9479-11ea-913f-3d5c3f8dbdc4.png" alt="image" style="zoom: 50%;" />

  - JVM이 있다면 어떠한 physical machine이던지 platform 독립적인 byte code를 실행할 수 있는 환경을 제공할 수 있게 된다는 것을 의미

#### Application domain

- physical problem이랑 전혀 상관 없는 environment에서도 사용 가능

```
직접 솔루션이없는 경우 시뮬레이션 또는 변환으로 문제를 해결하는 데 적합합니다.
샘플 응용 프로그램에는 마이크로 프로그래밍, XML 처리, 스크립트 명령 언어 실행, 규칙 기반 시스템 실행, 스몰 토크 및 Java 인터프리터 유형 프로그래밍 언어의 해석기가 있습니다.
```



#### Case Study

- **Cloud Computing**

  <img src="https://user-images.githubusercontent.com/61573968/81666781-713f0600-947d-11ea-9911-df4401a8608e.png" alt="image" style="zoom:67%;" />

  - 자원이 어딘가 외부에 있고 그것을 대여해서 사용하는 utility(전기 물과 같이 일반적으로 사람들이 필요로 하는 서비스를 일컬음) model --> 사용하는 만큼 비용 지불
  
- VM은 Hypervisor(physical Operating System을 다른 VM에서 공용적으로 사용할 수 있도록 환경을 제공)가 있음
  - Hypervisor: 제한된 resource들을 여러 VM들이 공유할 수 있도록 해줌

  <img src="https://user-images.githubusercontent.com/61573968/81667380-2a054500-947e-11ea-8050-c1ac91d062f4.png" alt="image" style="zoom: 80%;" />
  
  - Container Engine
  - OS가 없음 대신 라이브러리나 디렉토리로 구성
  - OS가 차지하는 공간이 없기 때문에 매우 효율적으로 resource의 사용이 가능

#### Benefits

- machine내의 platform에 독립적으로 운영 가능
- portability를 가지고 다른 machine에 이식 가능
- 소프트웨어를 개발할 때 physical system에 국한되지 않고 필요한 환경을 구축해서 사용할 수 있음
- 또 다른 환경에 simulation과 같은 작업을 할 때 운영 가능



#### Limitations

- 프로그램을 실행할 때 interpreter에 의해 해석이 되어야 실행이 가능하기 때문에 interpreter에 대한 overhead가 발생할 수 있음