# Hierarchical SA - Master_Slave_Architecture_Styles

#### 정의

**Hierarchical SA**(Software Architecture): 전체 시스템을 계층적인 구조 형태로 구분하여서 보는 형태(소프트웨어 시스템을 logical modules로서 분해를 해서 서로 계층적인 관계성을 가지고 서브시스템을 나누는 것)

#### Structure

분해된 module들은 서로 연결이 되어 있고, 이 연결은 method invocation이나 communication을 통해서 이루어짐

<img src="https://user-images.githubusercontent.com/33410490/81383000-45084a00-914a-11ea-85c0-55dea560793a.png" alt="image" style="zoom: 50%;" />

#### Architecture Styles

Master-Slave / Layered / Virtual machine & Container / Plug-In & Microkernel



## 1. Mater-Slave Architecture Style

#### 정의

- 시스템이 여러개를 제공하고 있고 문제가 일어날 때 장애를 극복할 수 있는 형태이며 이를 통해 시스템에 대한 신뢰도가 높아짐
- Master: 주체 Module
  - replicated service한테 적절한 일을 invocate
  - 모든 slave에게서 결과를 받음
  - 어떤 경우에는 그 중 가장 좋은 결과만 취합해서 사용하기도 함
- Slave: 종속 일 Module
  - 복제되는 서비스를 제공할 수 있음(replicated services)
  - 같은 기능적 일을 하기도 함(same functional task)
  - instruction을 같고 다른 content로 일을 수행할 수 있음

#### Structure

<img src="https://user-images.githubusercontent.com/33410490/81387261-5b65d400-9151-11ea-85cd-3c9a1124bef8.png" alt="image" style="zoom:50%;" />

<img src="https://user-images.githubusercontent.com/33410490/81387290-69b3f000-9151-11ea-9749-81e8b60ab63a.png" alt="image" style="zoom:50%;" />

- << slaves >> : stereotype



#### 유형1 (웹 서버)

<img src="https://user-images.githubusercontent.com/33410490/81388209-ee533e00-9152-11ea-8797-67dd5692ac20.png" alt="image" style="zoom:67%;" />

- 사용자가 request를 보냄
- request를 master가 받고 이를 하나의 slave에 전달
- slave들은 fast-ethernet으로 연결 되어 있고 DB와 같은 저장장소를 연결함
- slave가 request를 받고 이를 처리해서 보냄
- processing부분은 slave가 request를 받고 전달하는 것은 master가 함

동종의 software system을 slave node에서 운영을 하게 되고 **master가 적절한 request를 slave에 전달**하게 됨



#### 유형2 (큰 Task)

- Task -> **Assign Subtasks to slave nodes**

  <img src="https://user-images.githubusercontent.com/33410490/81388941-0081ac00-9154-11ea-8541-d083a485fcdd.png" alt="image" style="zoom:67%;" />