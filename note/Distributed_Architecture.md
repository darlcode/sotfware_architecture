# Distributed_Architecture

### Distributed Architecture

#### 정의

- 컴퓨터들의 집합
- 각기 독립적으로 하드웨어와 OS를 가지고 있는 컴퓨터들이(자기 플랫폼) 집합체로 모여 있는 시스템
- **네트워크적으로 서로 연결**이 되어 있어야 상호호환적으로 일을 할 수 있음
- 정리하자면, 네트워크로 연결되어서 커뮤니케이션(message passing, RPC(remote procedure calls), remote method invocation)할 수 있는 컴퓨팅 리소스들의 집합을 의미
- computing resources 및 storage도 포함

![image](https://user-images.githubusercontent.com/33410490/81937446-99ba3200-962e-11ea-8e44-19268f5a8849.png)

- SSI를 application layer에서 할 지 middle level의 platform에서 할 지를 정하는 것이 주안점

#### Structure

- distributed system을 디자인 하는 데 중요한 두 가지 요소:

  - network topology: (topology: 컴퓨터 네트워크의 요소들(링크, 노드)을 물리적으로 연결해 놓은 것 또는 그 연결방식을 말함)

    연결된 네트워크를 형성하기 위해 엔티티를 구성하는 방법

  - communications mode: 구성 요소가 서로 통신하는 방법

    - network topology위에서 communication의 상태
    - methods
    - 접근 방식
    - 어떤 layer에서 접근할 지

- 주요특성 :

  - service location transparency:
  - services reliability and availability

- distributed architecture을 지원하는 technology framework들이 있음
  - .NET, J2EE,,,

#### 다양한 distributed architecture의 종류들

- Client-Server
- Multitier
- Proxy
- Dispatcher (Load Balancer)
- P2P
- Broker
- Service-oriented architecture
- MicroService architecture