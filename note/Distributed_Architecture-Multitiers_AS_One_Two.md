# Distributed_Architecture-Multitiers_AS

### Multitier Architecture Style

### 1. One-tier Architecture

##### 정의

- 아래와 같은 layer들(코드들)을 한 노드(node)에 적재하는 것을 One-tier Architecture
- 외부에서의 접근은 terminal로 함(원격 시스템)

- Monolithic information system: 한 컴퓨터 안에 모든 코드를 다 가지고 있는 형태
  - information system(layered AS):
    - presentation layer: user나 client에게 프로그램을 더 잘 활용할 수 있도록 제공하는 layer
    - application logic layer: application들이 해야하는 일들에 관련된 processing들이 이루어지는 layer
    - resource management layer: DB 접근,관리하는

- mainframe기반 및 dumb-terminal(입출력만 담당하는 terminal) 상호작용

##### Structure

![image](https://user-images.githubusercontent.com/33410490/82011637-89e33200-96b0-11ea-8a9c-0c793d121e2f.png)



### 2. Two-tier Architecture

##### 정의

- 두 개의 node가 있음 --> information system을 두 개의 그룹으로 나눔
  - client node: presentation layer
    - 사용자가 접근해서 처리하기 편한 노드에 적재
    - presentation layer: the client and the PC
      - PC에서 사용할 수 있는 계산능력을 활용할 수 있음
      - 시스템의 복잡도를 높이지 않으면서 다른 목적으로 presentation layer를 조정
    - Thin client: 해야되는 일이 많지 않고, process하는 능력과 메모리가 크지 않은 client
    - Fat client: 해야되는 일이 많고 능력과 메모
    
  - server node: application logic layer, resource management layer
    
    - 자원에 관련된  그리고 information 저장된 형태로 가지고 있는 형태의 일들
    - 보통 관리자가 존재
    
    - 복잡하고 어려운, 일처리를 많이하고 데이터나 리소스에 접근을 많이하는 서버군에 적재

##### structure

<img src="https://user-images.githubusercontent.com/33410490/82012267-5ef9dd80-96b2-11ea-8a38-1caa049cf48b.png" alt="image" style="zoom:80%;" />

- Two-tier Client-Server Architectures

  - Client: 사용자에 더 가까운 layer에 일들을 지니며 그에 대한 프로그램들을 적재
  - Server: 자원에 관련된, 

  ![image](https://user-images.githubusercontent.com/33410490/82012877-edbb2a00-96b3-11ea-9b21-d6329207b603.png)

  - (a) ~ (e) : information system 중 어느 layer를 기준으로 자를 지에 따른 차이
  - (a): presentation layer를 기준으로 자름, server node에도 presentation layer의 연장선이 존재
  - (b): presentation layer를 기준으로 완전히 나눔
  - (c): application logic layer를 기준으로 자름, 연장선이 존재
    - fat하다고 함 : client가 하는 일이 많은 경우(heavy한 client)를 일컬음
  - (d): application logic layer를 기준으로 완전히 나눔
  - (e): resource management layer를 기준으로 나눔, 연장선이 존재
