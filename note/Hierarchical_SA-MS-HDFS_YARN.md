# Hierarchical_SA-MS-HDFS_YARN

### YARN(Yet Another Resource Negotiator)

- resource에 해야하는 역할을 분리를 해서 resource의 관리를 더 잘할 수 있도록  만들어진 구조

- daemon(항상 운영하고 있는 프로세스)을 통해서 job scheduling/monitoring을 함

- global Resource Manager(RM)

- per-application Application Master(AM)

  <img src="https://user-images.githubusercontent.com/61573968/81551586-0e863580-93bd-11ea-9850-8c414db093a8.png" alt="image" style="zoom:80%;" />

  - MapReduce Status: 일에 대한 처리를 수행해주는 status flow
  - Job Submission

#### YARN Managers

- Resource Manager와 Node Manager는 전체 YARN에서 data-computation framework에 속해 있음

- Resource Manager: 

  - master daemon

  - 전반적인 resource의 관리 

- Node Manager:

  - slave daemons
  - task를 실행할 때마다
  - Data Node형태

  - machine마다 있는 framework agent(시스템 별 프레임워크 에이전트)
  - 컨테이너 담당
  - 시스템 자원 사용량을 모니터링 --> Resource Manager/Scheduler에게 보고

- Application Master(per-application):

  - 라이브러리같은 형태
  - resource관련된 일들을 할당도 받고 처리를 해주는 역할
  - Node Manager와 협업을 하여 자신의 업무가 얼마만큼 진행이 되었는 지 확인

- Container:

  - resources들의 package

    

- Application Submission in YARN

  ![image](https://user-images.githubusercontent.com/61573968/81556272-03370800-93c5-11ea-81fe-1edec5482cfb.png)

  - :one:: Submit the job
  - :two:: Get Application ID
  - :three:: Application Submission Context
  - :four:
    - :a:: Start Container Launch
    - :b:: Launch Application Master
  - :five:: Allocate Resource
  - :six:
    - :a:: Container
    - :b:: Launch
  - :seven:: Execute

- Application Workflow in Hadoop YARN

  <img src="https://user-images.githubusercontent.com/61573968/81557811-8ce7d500-93c7-11ea-98b1-4fe563f7fcc3.png" alt="image" style="zoom: 67%;" />

  1. Client가 RM에게 job을 submission함
  2. RM은 Container를 적절히 할당하여 AM을 start
  3. AM은 RM과 더불어 작업을 한다는 것을 소통
  4. AM은 container를 이용하여 RM이 하는 일을 할 수 있도록 함
  5. AM은 할당된 NM에게 container가 launch되도록 함
  6. Application code가 container위에서 돌아가도록 함
  7. Client가 RM과 Contact을 해서 적절하게 application이 돌고 있는 지를 확인
  8. AM은 report도 하고 unregister도 함

