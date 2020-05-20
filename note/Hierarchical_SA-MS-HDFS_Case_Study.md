# Hierarchical_SA-MS-HDFS_Case_Study

#### Hadoop HDFS

<img src="https://user-images.githubusercontent.com/33410490/81400199-8824e600-9167-11ea-83c6-7d57ef277265.png" alt="image" style="zoom: 67%;" />

## 1. HDFS(Hadoop Distributed File System)

#### 정의

- 분산적으로 데이터를 저장하는 구조체를 지님
- NameNode: FS(File System)에 관련된 meta data를 관리
- DataNode: 데이터들을 저장하는 역할
- reliable: 데이터를 여러게 duplicate해서 저장가능
- scalable: node들을 얼마든지 붙여 나갈 수 있음
- distributed computing: 분산적인 컴퓨팅이 가능하도록 하게 하는 플랫폼

#### Architecture

<img src="https://user-images.githubusercontent.com/33410490/81404189-e5249a00-916f-11ea-9e8f-f729a1e3f988.png" alt="image" style="zoom: 67%;" /> 

[출처](http://hadoop.apache.org/docs/stable/hadoop-project-dist/hadoop-hdfs/HdfsDesign.html)

#### Map Reduce

- software framework(소프트웨어적으로 어떤 어플리케이션을 쉽게 운용하게 해주는)

- 많은 데이터가 들어올 때 처리하기 쉽게 만들어 주는 것

- commodity hardware(저렴하게 살 수 있는 하드웨어)에서 cluster를 만들어 놓고 병렬로 heavy한 데이터를 처리함

- framework

  - A Single ResourceManager

  - cluster-node 당 하나의 Slave nodeManager

  - application별로 MRAppMaster

- Mechanism

  <img src="https://user-images.githubusercontent.com/61573968/81548330-18596a00-93b8-11ea-80b4-8e79e5f10fcf.png" alt="image" style="zoom: 80%;" />

  - big data를 분할하여 노드에 넣어줌

  - mapping(데이터를 가지고 처리할 수 있는 코드를 넣어줌) method라고 생각하면 됨

  - 그 결과값을 디렉토리에 넣고 reduce 메커니즘을 돌림(여러 노드들을 합쳐가면서 해야하는 일들을 수행하는 것)

  - **예시**

    <img src="https://user-images.githubusercontent.com/61573968/81548679-9e75b080-93b8-11ea-9306-93e5d525e9a2.png" alt="image" style="zoom:80%;" />

 

