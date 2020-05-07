# GRASP_Design_Principle - Expert부터

3. **Expert**(information expert):

   - 그 일에 대해서 잘 알고 있는 역할을 가진 모듈이 그 일을 담당을 할 수 있도록 하는 것이 Expert를 만드는 것
   - 맡은 역할을 수행하기 위해 필요한 정보드를 지니고 있는 class가 곧 information expert에 해당된다고 할 수 있음
   - information이 있는 곳에서 그 일이 일어날 수 있도록 해주는 것(정보가 돌아다니지 않고 encapsulated)
   - Benefit: 
     - 정보의 encapsulation이 가능해짐 --> **low coupling** --> 관리 용이
     - behavior가 다른 class에 있을 때 요청하는 information은 그 위치에 있도록 해주는 것 --> **high cohesion**

4. **Creator**:

   - Constructor와 구별해야함

     - Constructor는 class를 만들고 그 class에서 Object을 'new'를 사용하여 부르게 될 경우 `_ = new Student()` `Student()`안에 `Student`라는 Constructor가 있어 Object instance를 생성하여 return 해주는 것
     - Creator는 관련된 Object에 대해서 누가 그 Object을 생성하느냐를 결정하는 것

   - 예시:

     class B에 class A의 instance(Objects)를 생성하는 것을 할당했을 경우:

     - **B** *aggregates* **A** Objects : A의 Objects를 모아서 가지고 있는
     - **B** *contains* **A** Objects : A의 Objects를 포함
     - **B** *record* instance of **A** Objects : A의 Objects이 해야할 일을 추적하여 관리하는 class는 B
     - **B** *closely* uses **A** Objects : B만 사용함
     - **B** *has the initializing* data that will be passed to **A** when it is created(thus **B** is an Expert with respect to creating **A**) : A의 Objects을 만드는 모든 초기값들은 B가 가지고 있음

5. **Controller**:

   - 제어자 : 외부에 일들이 일어나고 내부에 그 일들을 처리하는 경우가 있는 데, 이와 같은 외부/내부의 일을 분리(traffic)하는 역할을 맡아서 하는 것

   - external event를 받아서 안에 있는 Object에 이 event를 handle해달라고 전달하는 것(internal event-handling object)(**forwarding**)

     <img src="https://user-images.githubusercontent.com/33410490/81270563-e11c4d80-9085-11ea-9231-afe0a0d707b6.png" alt="image" style="zoom: 50%;" />

   - 외부에서 접근할때는 Controller의 interface만 알면 접근 가능함

   - Object represents facade controller / use case / session controller / role controller

     <img src="https://user-images.githubusercontent.com/33410490/81270237-63f0d880-9085-11ea-86d5-26ef3469f4e4.png" alt="image" style="zoom: 50%;" />

   - Benefits:

     - reusable
     - use case와 관련된 일들을 maintain할 수 있음
     - 관련된 일에 대해 activity가 순차적으로 진행되도록 관리가 가능해짐

   

6. **Don't Talk to Strangers**:

   - 두 class가 서로를 직접 인식하거나 다른 방식으로 연결해야 할 이유가 없으면 두 class가 직접 상호 작용해서는 안됨(관련이 없는 reference라면  classes를 서로 연결하지 않도록 함 --> not directly interact)

   - 두 class가 정보만 교환을 하는 경우 indirect하게 정보만 전달할 수 있는 class를 만듦(indirectly through another class) --> ***intermediate unit***이 생김
   - low coupling