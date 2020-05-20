# Distributed_Architecture-Client_Server_Architecture_Style

### Client-Server Architecture Style

#### 정의

- 두 개의 processes(실행되는 프로그램. client, server)가 각자 다른 processors(노드)에 적재되어 있어 서로가 소통을 통해 각자의 역할을 담당하는 것

- distributed system architecture중 가장 일반적으로 쓰임

#### Structure

- Client:

  - Server에게 request를 보내는 프로그램

- Server(핵심):

  - Client로 부터 request를 받고 처리하고 결과를 돌려주는 역할을 함
  - 항상 Client가 request하기를 기다리는 형태 --> 항상 돌아감

- 

- request-reply interaction

  <img src="https://user-images.githubusercontent.com/33410490/81945556-38e42700-9639-11ea-9a7c-426fc6d003be.png" alt="image" style="zoom:80%;" />

  - Client(Client node에 적재)는 Server에 request를 보냄

  - Server(Server node에 적재)는 request를 받고 해당되는 서비스를 스스로 작동하고 reply함

  - `질문!!` request 에 관련된 process computation은 Client? Server 중 어디에서 하는 지?

    `정답` server에서 돌아감

- Two-tier?

  - tier? 층

    - client는 server에 request를 보내는 하나의 단을 이루고 있음(두 개 묶음 --> 하나의 티어)
    - server

  - [출처]( https://www.tutorialspoint.com/software_architecture_design/distributed_architecture.htm )

    <img src="https://user-images.githubusercontent.com/33410490/81947273-53b79b00-963b-11ea-8a22-9c8576dbc231.png" alt="image" style="zoom:80%;" />

    - network를 통해 request를 보냄

#### Benefits

- 해야 하는 일의 분리(Separation of responsibilities) --> Client와 Server 각자 해야하는 Roll&Responsibility가 있음
  - user interface presentation
  - business logic processing
- Server components의 재사용(reusability)

#### Disadvantages

- heterogeneous(이종의) infrastructure의 경우 : 다른 종류의 시스템(예를 들어 어떤 컴퓨터는 리눅스 어떤 컴퓨터는 윈도우)의 경우 requests를 어떻게 주고 받을 지 고민을 해야함
- Security : 네크워크를 통해 다른 시스템에 접근하므로 
- availability and reliability: Server가 항상 대기 상태에 있는 지 혹은 신뢰서을 보장할 수 있는 지
- testability and scalability: 프로세스가 테스팅 가능한 지 혹은 한 Server에 여러 Client의  request를 할 수 있는 지