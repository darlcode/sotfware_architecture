# Hierarchical_SA-Microkernel_Architecture_Style

#### Microkernel Architecture Style

![image](https://user-images.githubusercontent.com/33410490/81716832-ccd8b600-94b4-11ea-87c4-f4351da39580.png)

- driver가 하드웨어가 바뀜에 따라 변경이 되는데 OS할 때마다 깔아주면 OS가 변경이 많이 되므로 driver와 상관없이 OS만 돌아갈 수 있는 micro한 kernel을 만든 것
- 외부의 server들을 adapter를 통해 나감
- VM과 매우 유사한 구조
- 하드웨어 platform에 쉽게 이식가능한 형태 --> portability
- 개발 환경이 변경이 되어도 제공할 수 있는 구조
- 다른 OS에서 돌아가는 application이 쉽게 운영될 수 있도록 제공

#### Context

- 여러 application을 개발하는 입장에 있어서 하나의 kernel에서 작업을 할 수 있도록 하는 여러가지 flexibility를 제공하자는 취지

#### Problem

- 응용 프로그램 플랫폼은 지속적인 하드웨어 및 소프트웨어 발전에 대처 해야함
- 애플리케이션 플랫폼은 새로운 기술을 쉽게 통합 할 수 있도록 extensible, adaptable가능해야함

#### Structure

![image](https://user-images.githubusercontent.com/33410490/81718241-77050d80-94b6-11ea-84d8-a49988864558.png)

- 응용 프로그램 플랫폼의 기본 서비스를 microkernel 구성 요소로 encapsulate 함

- 크기 나 복잡성을 불필요하게 늘리지 않고 마이크로 커널 내에서 구현할 수없는 Core functionality는 internal server에서 분리해야함

- external server는 microkernel 위에서 올라가서 구현돼서 운영될 수 있도록 구현됨

- client는 external server에 접근할 때 adapter를 통해 접근함

- **Microkernel(CRC)**

  <img src="https://user-images.githubusercontent.com/33410490/81718905-4a052a80-94b7-11ea-8f94-3ea8ddd60aa5.png" alt="image" style="zoom:80%;" />

  - **class** : class name
  - **Responsibility**: 이 class가 해야하는 일 (microkernel)
    - core의 가장 기본적인 mechanism
    - IPC와 같은 communication facilities제공
    - internal service를 접근할 수 있는 encapsulate 능력을 지님
    - 다른 여러 관련된 resource를 관리할 수 있는 기능
  - **Collaborators**: 연결해서 같이 연관돼야 하는 class 이름
  - Microkernel:
    - 서비스를 제공하는 역할을 지님
    - 시스템에 대한 dependency를 지님
    - 자원을 관리
    - atomic service --> breaking할 수 없는 encapsulate한 서비스를 제공함

- **Internal Server(CRC)**

  <img src="https://user-images.githubusercontent.com/33410490/81719782-74a3b300-94b8-11ea-9709-1604a3346a81.png" alt="image" style="zoom:80%;" />

  - 내부적인 서비스를 driver level에서 구현
  - 시스템에 아주 세부적인 driver들을 encapsulate하는 능력을 지님
  - 기능성을 더 확장할 수 있는 역할을 지님
  - 하드웨어와 소프트웨어의 dependency를 지니며 그것을 encapsulate화 함
  - 필요에 따라서 서비스 request에 따라서 operation이 됨

- **External Server(CRC)**

  <img src="https://user-images.githubusercontent.com/33410490/81720077-debc5800-94b8-11ea-8a1b-1941340fa657.png" alt="image" style="zoom:80%;" />

  - client가 interface를 가지고 접근할 수 있도록 제공

- **Client & Adapter(CRC)**

  ![image](https://user-images.githubusercontent.com/33410490/81720251-1d521280-94b9-11ea-9976-23c3cd2a2340.png)

  - client는 application에 접근 가능
  - adapter는 client가 application에 접근 가능하도록 해줌(client와 web server간 중재자 역할)

#### Dynamics

<img src="https://user-images.githubusercontent.com/33410490/81720452-686c2580-94b9-11ea-951e-e0b9d885bc31.png" alt="image" style="zoom:80%;" />



![image](https://user-images.githubusercontent.com/33410490/81720524-7cb02280-94b9-11ea-88e0-853cc331c0f0.png)

- microkernel을 통해서 내부적인 일들이 수행됨



#### Microkernel Vs Monolithic Kernel

![image](https://user-images.githubusercontent.com/33410490/81720697-b8e38300-94b9-11ea-9f02-2a7eb3fe7827.png)

- **Microkernel**
  - kernel을 작게 만드는 것 --> minimal operation, 필요한 라이브러리를 낄 수 있음
  - heavy한 OS를 분해함
  - kernel이 위쪽에 있음(주황 분홍 갈색 하늘)
  - 필요에 따라 배치하여 운영
- **Monolithic Kernel**
  - 모든 것을 다 가지고 있는 것(하드웨어 위에 모든 OS가 해야할 일을 하는 것) 00> heavy

#### Benefits

- portability
- flexibility
- policy와 mechanism 분리 가능

#### Distributed MicroKernel Benefits

- scalability(확장성)
- reliability(신뢰성)
- ***transparency***(투명성)
- performance
- 설계롸 실행의 보잡도를 관리할 수 있음