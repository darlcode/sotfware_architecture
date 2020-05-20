# Hierarchical SA - Master_Slave_AS_Examples

#### Cluster Computing

<img src="https://user-images.githubusercontent.com/33410490/81398975-38ddb600-9165-11ea-9a83-4e4351d3790b.png" alt="image" style="zoom: 67%;" />

-  클러스터 컴퓨팅은 많은 컴퓨터가 네트워크에 연결되어 있으며 단일 엔티티처럼 작동 함을 나타냄

-  클러스터는 일종의 병렬 / 분산 처리 네트워크로, 상호 연결된 개별 컴퓨터 배열과 컴퓨터 시스템이 단일 독립형 시스템으로 함께 작동하도록 설계

-  네트워크에 연결된 각 컴퓨터를 **노드**(메모리, 입력 및 출력 기능 및 운영 체제가있는 단일 또는 다중 프로세서 네트워크 )라고 함

-  클러스터 컴퓨팅은 빠른 컴퓨팅 속도와 향상된 데이터 무결성을 제공하여 복잡한 문제를 해결하는 솔루션을 제공 

- **장점:**

  - **비용 효율성** – 메인 프레임 컴퓨터조차도 매우 안정적인 것처럼 보이며 클러스터 컴퓨팅은 비용 효율성과 경제성으로 인해 구현에 더 적합함. 또한 이러한 시스템은 메인 프레임 컴퓨터 네트워크보다 향상된 성능을 제공함

  - P **세싱 속도** - 컴퓨팅 시스템 클러스터는 메인 프레임 컴퓨터와 동일한 처리 속도를 제공하며, 속도는 슈퍼 같음

  - **확장 된 리소스 가용성** – 컴퓨터는 자주 고장이 나므로 이러한 장애를 방지하기 위해 클러스터 컴퓨터는 고 가용성으로 제공. 따라서 한 노드에 장애가 발생하면 다른 노드가 활성화되고 장애가 발생한 노드의 프록시로 작동합니다. 이를 통해 가용성이 향상됨

  - **확장성** – 확장 성과 확장 성이 향상되었다는 것. 그들은 여러 개의 추가 자원 또는 네트워크를 일반적인 컴퓨터 시스템에 결합 할 수 있음

  - **유연성** – 클러스터 컴퓨팅을 우수한 사양으로 업그레이드하거나 추가 노드 (컴퓨터 시스템)를 추가하여 확장 할 수 있음



#### Case System Layout

<img src="https://user-images.githubusercontent.com/33410490/81399930-f0bf9300-9166-11ea-9231-145d917da001.png" alt="image" style="zoom:80%;" />



#### Hadoop HDFS(Hadoop distributed File System)

<img src="https://user-images.githubusercontent.com/33410490/81400199-8824e600-9167-11ea-83c6-7d57ef277265.png" alt="image" style="zoom: 67%;" />

<img src="https://user-images.githubusercontent.com/33410490/81400556-5b250300-9168-11ea-942f-300e2f4c3b11.png" alt="image" style="zoom:67%;" />



- NameNode(Master): 외부에서 어떤 큰 File을 보내면 이를 chunk 사이즈로 자른 뒤 DataNode에 저장, 정보는 meta data로 지님
- DataNode(Slave): process라고 보면 됨
- MapReduce!
- JobTracker(Master) / TaskTracker(Slave)



#### Hadoop 2.0 YARN

<img src="https://user-images.githubusercontent.com/33410490/81400804-e0101c80-9168-11ea-82a6-dfd8adf51758.png" alt="image" style="zoom: 67%;" />

- resource management

<img src="https://user-images.githubusercontent.com/33410490/81402438-5a8e6b80-916c-11ea-801e-ebf08610a3bc.png" alt="image" style="zoom: 80%;" />



<img src="https://user-images.githubusercontent.com/33410490/81402684-d688b380-916c-11ea-9b92-779a92d1bca6.png" alt="image" style="zoom:80%;" />



#### Master-Slave 특징

- slave들이 동종의 일들을 하게 돼서 병렬적으로 컴퓨팅을 하게 되는 것(parallel computing and accuracy of computation)
- 모든 slave들은 parallel: 다른 데이터를 가지고 같은 instruction을 수행
- 어떤 task가 적절하지 않은 result를 내는 slave가 있다면 그것은 **rule out**
- 가장 많은 Software System에서 사용하는 architecture
- server들의 redundancy: 중복적으로 slave들을 많이 가지고 있어 reliability를 높일 수 있는 좋은 아키텍처 스타일