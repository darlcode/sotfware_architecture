# Distributed_Architecture-MultitierAS_3_and_N_Tires

### Three-tier Architectures

##### 정의

- client tier와 server쪽에 있는 tier간에 중간에 어떤 application에 관련된 일들을 담당하는 tier가 제공되는 아키텍처

- information system을 배치(deploy:설치를하고 수행을하는 것)를 할 때 각 layer별로 배치함

  - layer가 tier인것은 아님!

  - layer는 소프트웨어에 관련된 일들끼리 모듈화
  - tier는 역할로써 나누어 적재하는 것

- presentation layer는 client에 / application logic layer는 middleware에 / resource management layer는 하단에 배치

##### structure

- Application Layering

  - User-Interface Level (tier)
  - Processing Level (tier)
  - Data Level (tier)

  ![image](https://user-images.githubusercontent.com/33410490/82116493-30106400-97a5-11ea-88ea-6b0a4d05d728.png)

##### 특징

- processing을 하는 중간단계가 있음
- scalable, robust(안정된) and flexible(유연성)
- 각 열할마다 node수를 조정할 수 있음
- 다른 종류의 일들을 각각 scale out할 수 있는 multiple source로부터 데이터를 integrate할 수 있는 구조를 지님
- TP Monitor(transaction), Distributed Objects, Web

<img src="https://user-images.githubusercontent.com/33410490/82116618-23404000-97a6-11ea-9244-703d187e679f.png" alt="image" style="zoom: 67%;" />



##### Request view Architecture

![image](https://user-images.githubusercontent.com/33410490/82116781-1a03a300-97a7-11ea-95e9-020e8144308d.png)

- Vertical Distribution
  - 수직적으로 일처리를 해나가는 형태



### Multi-tiers(N-tier) Architecture Style

##### 정의

- 시스템의 요구사항에 따라서 tier를 여러단계로 나누는 것
- front-end-tier(client) ㅡ middle-tier(s) ㅡ back-end-tier(resource)(s)

##### 예시

![image](https://user-images.githubusercontent.com/33410490/82116995-787d5100-97a8-11ea-950a-6d0bf66e4dc9.png)

- web server에 한번에 많은 requests를 보내게 되면 web server가 죽게 됨 --> DOS
- web server가 죽더라도 application server는 수행가능

##### 장점

- 재사용성(reusability)가 좋음
- scalability가 보장
- portability(flexibility)
- traffic을 효율적으로 관리 가능

##### 단점

- testability : test tool의 부족
- 시스템에 여러 server를 추가하면 서버의 reliability(안정성)와 availability(가용성)가 중요해짐

