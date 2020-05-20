# Hierarchical SA-Layered_Architecture_Style

#### 정의

전체 시스템을 각 layer 마다 관련된 classes로만 구성한 architecture

- package안에 encapsulate 됨
- deployed component
- 각 layer는 해야하는 일이 각각 할당됨

#### Structure

- i번째 layer가 있으면 i+1로 request
  - i번째는 관련된 interface만 알고 있으면 됨
- interface를 통해서 각 layer는 encapsulate 됨
- **request**: 위 layer에서 밑 layer로 감 (method invocation을 통해)
- **response**: 밑 layer에서 위 layer로 감(method return을 통해)
- 보통은 인접한 layer와 연결이 되어 있어 근접한 layer와 request service를 함
- 특별한 경우 bridge type connection를 통해 request service를 함 (권장하지 않음)

#### Layered Architecture

- layer는 R&R(Role and Responsibility)를 지님
- layer는 추상적(abstract)으로만 보여주는 것이 좋음
- 각 component는 관련된 것만 고려하도록 구성
- isolation concept --> 추후에 재사용성(reusability)과 changeability에 좋음

#### Example

<img src="https://user-images.githubusercontent.com/61573968/81561580-595c7900-93ce-11ea-9132-49eb9c925e9d.png" alt="image" style="zoom:80%;" />

- layered approach는 관련된 일들을 monolithic block으로 본다는 점에서 장점을 지님

  <img src="https://user-images.githubusercontent.com/61573968/81563376-249df100-93d1-11ea-9232-52120d064677.png" alt="image" style="zoom: 50%;" />

- 각 layer마다 해야하는 일들을 나눠 의미론적으로 명칭을 붙임

- 상위의 layer가 일반화 되고 하위로 갈수록 전체 시스템을 support할 수 있도록 구성

#### Implementation

- package화 된 layer는 compress가 돼서 deploy가능함
- deploy가 된다면classpath 환경을 설정하여 다른 class에도 접근 가능



#### Two layers Software System

- Interaction layer:
  - user interfaces to clients
  - request를 받음
  - client에 response
- Processing layer:
  - 위에서 request(forward)된 것을 받음
  - 의미 있는 workflow(business logic process)를 가지고 처리
  - access DB
  - return하고 올라가서 client에 결과를 보여줌

#### Application domains

- generic services

#### Android Platform

#### Benefits

- 점진적으로 완성해나가는 software architecture로 아주 적합(외부는 abstraction)
- layer마다 독립성(independence)를 제공 -->외부에는 추상적인 것만 보여줌
- 유연성(flexibility): interchangeability, reusability
- component-based
- portability(이식가능성)

#### Limitations(한계점)

- 성능이 다소 떨어질 수 있음
  - performance overhead <-- 내부적으로 어떠한 일이 있는 지 모르는 상태에서 계속 performance를 delegate(위임)
  - data marshaling(정렬화) : object level로 parameter가 가게 되면 다른 시스템이 serialize해야하고 marshaling, unmarshalling하는 데 시간이 걸림
  - buffering(정체)
- interlayer communication: layer를 건너뛰는 경우 --> deadlock이 걸릴 가능성이 있음
- exceptions ans error handling: 본 layer에서 생겨난 에러는 본 layer에서 다루는 것이 좋음(너무 여러단계까지 올라가면 다루기 힘듦)

