# Hierarchical_SA-Plug-In_Architecture_Style

#### Plug-In Architecture Style

- 바뀌어지는 system에 매우 적응이 빠른 architecture
- plugging: extension의 의미
- 확장연결하고 공동작업을 조정하기 위한 socket으로써의 역할을 함
- plug-in architecture 기능이 있는 product-based(제품기반) application을 구현하기 위함



#### Structure

- Application logic --> extensibility(확장성), flexibility(유연성), isolation(application관련), custom processing logic
  - **independent** plug-in modules (예시: language extension)
    - 확장팩처럼 들어가는 것
    - 다른 모듈과는 서로 독립적
    - specialized processing(특수 처리), 추가 기능 및 코드를 포함
    - core system 보다 더 확장 된 기능들을 사용할 수 있도록 함
  - basic core system (예시: tv세트)
    - 시스템 작동에 필요한 최소한의 기능만을 포함하고 있음
    - 예) OS

<img src="https://user-images.githubusercontent.com/33410490/81708792-70719880-94ac-11ea-9b30-35917b15b6e6.png" alt="image" style="zoom:80%;" />

- plug-in registry
  - 각 plug-in module에 대한 정보
  - name, data contract, remote access protocol에 대한 세부적인 내용을 담고 있음

#### Examples

- **Eclipse IDE**

  - basic Eclipse product (기본)
  - plug-ins (추가)

  <img src="https://user-images.githubusercontent.com/33410490/81712163-45d50f00-94af-11ea-9d56-6f9d4a4b1314.png" alt="image" style="zoom:67%;" />

- **Internet browsers**

  - basic browser
  - viewers and other plug-ins

  <img src="https://user-images.githubusercontent.com/33410490/81712366-787f0780-94af-11ea-9b8e-f6d1ecd0e005.png" alt="image" style="zoom:50%;" />

- **Claims processing**

  - core system for claims processing
  - plug-in module contains the specific rules for the states

- **C# article example with Plug-In Architecture**

  ![image](https://user-images.githubusercontent.com/33410490/81710539-bf6bfd80-94ad-11ea-9ed9-bee0e13dcf02.png)

  ![image](https://user-images.githubusercontent.com/33410490/81711155-4ae58e80-94ae-11ea-9ed4-cb55fddc4de7.png)

- **Eclipse Architecture**

  ![image](https://user-images.githubusercontent.com/33410490/81711535-ba5b7e00-94ae-11ea-87c9-d96ad4470323.png)

  - plug-in은 JAR(Java Archive) 라이브러리에 java code로 구성되어 있음(디렉토리 구조로 되어 있음)

  - 확장의 확장이 가능함

    <img src="https://user-images.githubusercontent.com/33410490/81711894-07d7eb00-94af-11ea-9b6a-4452a073dd23.png" alt="image" style="zoom:50%;" />

- Chromium Architecture

  <img src="https://user-images.githubusercontent.com/33410490/81712696-e297ac80-94af-11ea-8c24-2900e8b168c8.png" alt="image"  />

  - Renderer: engine에 대한 일이 execution 됨
  - Plug-In을 할 때는 서로 interface만 맞춰주면 서로 callback으로 연결을 해서 실제 있는 곳에 proxy로 연결해서 연결할 수 있음

- Chrome Architecture

  ![image](https://user-images.githubusercontent.com/33410490/81713461-de1fc380-94b0-11ea-9b77-2b8ea07bf3ea.png)

  - abstract 함
  - DOM Tree로 encapsulate 되어 있음

- Internet Explorer Architecture

  ![image](https://user-images.githubusercontent.com/33410490/81713778-4373b480-94b1-11ea-8b23-2a9d74a8e8ec.png)

  - 보통 Tap process(보안이 중시 된 이후로)로 많이 얘기함

  ![image](https://user-images.githubusercontent.com/33410490/81714018-8fbef480-94b1-11ea-9328-ee1347bb590e.png)

  - dll로 구성

#### Benefits

- portability <-- extension
- flexibility <-- 필요에 따라서 requirement가 제품이 완료가 된 다음에도 요청을 했을 때 adaptation이 가능함
- policy(정책=사람의 decision)과 mechanism(구동체=어떤 operation? application program)간의 seperation(분리) --> 상황에 따라 사용