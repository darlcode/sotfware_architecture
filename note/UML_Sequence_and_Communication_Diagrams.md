# UML - Sequence and Communication Diagrams

## 1. Sequence Diagram

- 동적표현 Diagram
- 시스템 실행 시 생성되고 소멸되는 객체를 표기
- 객체들 간의 주고 받는 메세지를 보여줌
- **한 사건(Event)**이 발생했을 때 **여러 객체간 관계**를 **시간순서**에 따라 정의
- Usecase 내의 객체와 객체에 내포되어 있는 메시지 표현

<img src="https://user-images.githubusercontent.com/33410490/81257416-2fbded80-906e-11ea-9e24-9a7b6593b9d2.png" alt="image" style="zoom:50%;" />

- Actor가 시스템을 봤을 때 하는(해야하는) 일들을 시간의 순서로 나열한 것

- 외부 접근 --> **Boundary Class**
- 로직(누구를 부르고 어떤 것을 한다) --> **Control Class**

- 내부적으로 데이터 세이브 --> **Entity Class**



- Message Signatures:
  - `attribute = signal or message name (arguments) : return_type`



#### Nested Messages:

한 object이 여러 메시지를 송신하는 경우?



#### Message Arrows

![image](https://user-images.githubusercontent.com/33410490/81258166-0736f300-9070-11ea-9abc-4e5c2af65c93.png)

- Synchronous Message: 동기화 시키는 메시지, 왼쪽 Object이 불러주면 이를 받아 받았는 지 확인을 하고 Return message가 올 때까지 기다림
- Asynchronous Message: 기다리지 않음
- <<...>> : stereotype



## 2. Communication Diagram

- UML 1.X대에서 Collaboration Diagram이라고 불림
- Object와 Object의 관계로 구성된 communication을 보여줌 --> Sequence Diagram과 유사하나
- 메시지가 **일련의 번호(Sequence Number)**를 부여하여 표현된다는 점에서 차이가 있음
- 객체간의 구조적인 관계를 강조

<img src="https://user-images.githubusercontent.com/33410490/81261379-f0e06580-9076-11ea-8ed1-d4e582798789.png" alt="image" style="zoom: 50%;" />

- **Boundary, Control, Entity Class**

