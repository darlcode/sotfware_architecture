# GRASP Design Principles - Coupling and Cohesion

#### Define

- GRASP (General **Responsibility** Assignment Software):

  해야하는 책임량을 모듈에 할당해주는 일반화 된 원칙들을 말함

- OO(Object Oriented) design

- **assignment of responsibilities**

- changeability and reusability

- Class의 할 일을 할당해주는 것

- Object간의 할 일들이 명확해야함

- `'전반적인 설계에서의 역할이 어떠하다'`를 명시해주는 것

  

#### Types

1. **Doing responsibilities**: 해야되는 일을 **하는 것**
   - Method를 통해서 어떤 일을 operate할 수 있게 하는 것
   - 다른 Object에 있는 action을 시작할 수 있게 하는 것
   - 다른 Object에 있는 여러가지 activities를 제어(Control)하고 협업(Coordinating)하여 수행하는 것
2. **Knowing responsibilities**: 해야되는 일을 **아는 것**
   - private encapsulated 한 data를 알고 있는 것(현 클래스에서만 접근할 수 있는 데이터에 대해 알고 있는)
   - 관련된 다른 Object을 알고 있는 것(reference를 물고 있다는 것)
   - 이후에 derive 혹은 calculate될 여러가지 일들에 대해 알고 있는 것(이후의 변경가능성에 대해서도 알고 있음)



#### GRASP Patterns (6가지)

Low Coupling / High Cohesion / Expert를 찾아라 / Creator가 누군지 결정해라 / Controller의 역할을 강화 시켜라 / Don't talk to Stranger 모르는 Object or Module과 연결하지 마라

1. **Low Coupling:**

   - Coupling: 한 class가 다른 class에 연결된 정도(의존 정도)(아는 정도)
   - Problems of High Coupling: local change를 할 경우 관련된 class가 많아 변경이 힘듦 --> 재사용이 힘듦
   - Principle: responsibility를 주되 low dependency하여 재사용성을 높이는 관점에서 설계

2. **High Cohesion:**

   - Cohesion(응집도): 그 class의 해야하는 일이 관련되고 집중된 정도가 얼마나 강한지(한 가지 일이 할당이면 응집도가 높은 것이고 다양한 일이 몰려 있다면 응집도가 낮아지는 것을 의미)
   - Problems of low cohesion: 관련 없는 일들이 너무 많음, class를 이해하고 재사용하기 힘듦 --> high coupling
   - Principle: 해야되는 일이 집중되어 있는 것이 좋음, 복잡한 일들을 관리하기 편하게 담당을 해줄 수 있음
   - Benefit: 이해하기 쉬움, 관리가 쉬움, 재사용이 용이, Low Coupling

   

   ![image](https://user-images.githubusercontent.com/33410490/81264508-7ca8c080-907c-11ea-9340-a9d01724b7db.png)
   
   





