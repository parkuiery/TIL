자바 가상 머신 JVM(Java Virtual Machine)은 
**자바 프로그램 실행환경을 만들어 주는 소프트웨어**

<br/>

- 자바 코드를 컴파일하여 .class 바이트 코드로 만들면 이 코드가 자바 가상 머신 환경에서 실행된다
- JVM은 자바 실행 환경 JRE(Java Runtime Environment)에 포함되어 있음

<br/>

**JVM을 사용하면 하나의 바이트 코드(.class)로 모든 플랫폼에서 동작하도록 할 수 있다**

![image](https://github.com/parkuiery/TIL/assets/128464859/48e7afd5-a515-410f-bede-a9a9756f3291)

**생성된 바이트 코드는 각자의 플랫폼에 설치되어 있는 자바 가상 머신(JVM)이 운영체제에 맞는 실행 파일로 바꿔준다**

<br/>

### 바이트 코드를 읽는 방식

JVM은 바이트코드를 명령어 단위로 읽어서 해석

**Interpreter 방식과 JIT 컴파일 방식 두 가지 방식을 혼합하여 사용한다**

- **Interpreter 방식**
    - 바이트 코드를 한 줄씩 해석하여 실행
    - 초기 방식으로, 속도가 느리다는 단점
- **JIT(Just In Time)**
    - Interpreter의 느린 속도를 보안하기 위한 컴파일 방식
    - 바이트코드를 JIT 컴파일러를 이용해 프로그램을 실제 실행하는 시점(바이트코드를 실행하는 시점)에 각 OS에 맞는 Native Code로 변환하여 실행 속도를 개선
    - 바이트코드를 Native Code로 변환하는 데에도 비용이 소모
    - JVM은 모든 코드를 JIT컴파일러 방식으로 실행하지 않고 인터프리터 방식을 사용하다가 일정 기준이 넘어가면 JIT 컴파일 방식으로 명령어를 실행
 
<br/>

### JVM 구성요소

![image](https://github.com/parkuiery/TIL/assets/128464859/8bc6983a-b0d8-40a3-abc4-9cdc1a704b82)

- 클래스 로더(Class Loader)
- 실행 엔진(Execution Engine)
    - 인터프리터(Interpreter)
    - JIT 컴파일러(Just-in-Time)
    - 가비지 콜렉터(Garbage collector)
- 런타임 데이터 영역 (Runtime Data Area)
