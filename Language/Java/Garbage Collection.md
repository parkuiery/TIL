# Garbage Collection
**더이상 사용되지 않는 인스턴스를 찾아 메모리에서 삭제함**

유효하지 않은 메모리를 JVM의 가비지 컬렉터가 불필요한 메모리를 알아서 정리

<br/>

### Minor GC & Major GC

JVM의 Heap영역은 처음 설계될 때 다음의 2가지를 전제(Weak Generational Hypothesis)로 설계되었다.

- 대부분의 객체는 금방 접근 불가능한 상태(Unreachable)가 된다.
- 오래된 객체에서 새로운 객체로의 참조는 아주 적게 존재한다.

<br/>

**객체는 대부분 일회성되며, 메모리에 오랫동안 남아있는 경우는 드물다**

객체의 생존 기간에 따라 물리적인 Heap 영역을 나누게 되었고 Young, Old 총 2가지 영역으로 설계되었다

![image](https://github.com/parkuiery/TIL/assets/128464859/66bfe7f6-917b-4749-b25f-48aca8ad70fc)

- Young 영역(Young Generation)
    - 새롭게 생성된 객체가 할당(Allocation)되는 영역
    - 대부분의 객체가 금방 Unreachable 상태가 되기 때문에, 많은 객체가 Young 영역에 생성되었다가 사라짐
    - Young 영역에 대한 가비지 컬렉션(Garbage Collection)을 Minor GC라고 부름
    
- Old 영역(Old Generation)
    - Young영역에서 Reachable 상태를 유지하여 살아남은 객체가 복사되는 영역
    - Young영역보다 크게 할당되며, 영역의 크기가 큰 만큼 가비지는 적게 발생
    - Old 영역에 대한 가비지 컬렉션(Garbage Collection)을 Major GC라고 부름

 
<br/>

**Old 영역이 Young 영역보다 크게 할당되는 이유**

- Young 영역의 수명이 짧은 객체들은 큰 공간을 필요로 하지 않음
- 큰 객체들은 Young 영역이 아니라 바로 Old 영역에 할당됨

<br/>

### Old 영역에 있는 객체가 Young 영역의 객체를 참조하는 경우

Old 영역에는 512 bytes의 덩어리(Chunk)로 되어 있는 카드 테이블(Card Table)이 존재

![image](https://github.com/parkuiery/TIL/assets/128464859/dd75c3a6-0946-4d97-96c5-0f51f27fcdfb)

<br/>

### 카드 테이블

Old 영역에 있는 객체가 Young 영역의 객체를 참조할 때 마다 그에 대한 정보가 표시

**도입된 이유**

Young 영역에서 가비지 컬렉션(Minor GC)가 실행될 때 모든 Old 영역에 존재하는 객체를 검사하여 참조되지 않는 Young 영역의 객체를 식별하는 것이 비효율적이기 때문이다

**→ 카드 테이블만 조회하여 GC의 대상인지 식별**

<br/>

# Garbage Collection 동작방식

Young 영역과 Old 영역은 서로 다른 메모리 구조로 되어 있기 때문에 세부적인 동작 방식은 다름

기본적으로 GC가 실행되면 2가지 공통 단계를 따름

1. **Stop The World**
- JVM이 애플리케이션의 실행을 멈추는 작업
- GC가 실행될 떄 GC를 실행하는 쓰레드를 제외한 모든 스레드들의 작업이 중단, GC가 완료되면 작업이 재개

2. **Mark and Sweep**
- **Mark** : 사용되는 메모리와 사용되지 않는 메모리를 식별하는 작업
- **Sweep** : Mark 단계에서 사용되지 않음으로 식별된 메모리를 해제하는 작업
