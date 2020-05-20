# Distributed_Architecture-Proxy_AS

### Proxy Architecture

##### 정의

- proxy: 대표 가상 연결점
- 외부에 있는 Distributed Object

- proxy 관련 설명자료

  ![image](https://user-images.githubusercontent.com/33410490/82118051-88e4fa00-97af-11ea-8b93-dc58417a675d.png)

  proxy는 다른 객체에 대한 대리자 역할을 하는 proxy 객체를 통해 객체에 대한 method 호출을 강제로 수행하여 해당 객체에 대한 method 호출(indirect한 call)을 위임함

- 껍데기만 있는 조종자..!

- proxy 객체는 일반적으로 서비스 제공 객체와 공통 인터페이스 또는 superclass를 공유함

- server단에서 실행!!!

##### 특징

- transparent(투명성) management가 가능
  - real한 객체가 내부적으로 인식하지 못하더라도 요청하는 invocation에 따라서 real한 객체가 실행될 것이라고 믿을 수 있는
- proxy의 다양한 유형의 서비스 관리
  - real한 객체를 invocation하고 완료가 되면 바로 return하는 method를 만듦
  - Remote Proxy: distributed object가 client단에 없지만 마치 local에 있는 것처럼 illusion을 줌
  - Access Proxy: 외부의 remote한 노드(서비스를 제공하는 객체)들이 있는데  이에 접근하는 것을 통제
  - Virtual Proxy: 서비스 객체가 실제로 존재하기 전에 존재한다는 환상을 만듦

##### Structure

- Method calls through a proxy

  ![image](https://user-images.githubusercontent.com/33410490/82118963-6c4bc080-97b5-11ea-8103-a237b3b1591e.png)

- Proxy class diagram

  ![image](https://user-images.githubusercontent.com/33410490/82118980-9b623200-97b5-11ea-80e9-329ac9c5c318.png)

- class diagram2

  <img src="https://user-images.githubusercontent.com/33410490/82119012-f136da00-97b5-11ea-87a7-aeb772e7fd15.png" alt="image" style="zoom: 67%;" />

- Dynamics

  ![image](https://user-images.githubusercontent.com/33410490/82119070-6c988b80-97b6-11ea-9601-82d6f85a1baf.png)

  - 파란색 박스: Client node
  - 빨간색 박스: Server node

##### Benefits and Liabilities

- Benefits
  - original 객체에 접근할 수 있음
  - 공간 절약: 외부에 있는 distributed object을  내부에 가지고 오지 않아도(대표만 있으면 됨) control이 가능하기 때문
  - Cache proxy(Performance의 분리): server쪽과 client쪽의 operation 분리
  - housekeeping(유지보수) and functionality(기능적)의 분리
- Liabilities(고려할 사항)
  - Potential overkill(잠재적인 위험 부담)
    - proxy --> proxy -> ... --> distributed object의 경우에는 indirection level이 많아지면 네트워크에서 수행해야 하는 업무가 많아짐
    - 어디에서 문제인건지 알 수가 없음(환경 관리가 힘듦)

