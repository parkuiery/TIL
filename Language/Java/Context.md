# Context

---

> 현재 사용되고 있는 애플리케이션(또는 액티비티)에 대한 포괄적인 정보를 지니고 있는 객체
> 
- **Application의 현재 상태**를 나타낸다.
- Activity와 Application의 정보를 얻기 위해 사용할 수 있다.
- 안드로이드 **시스템 서비스에서 제공하는 API** (리소스, DB, Shared Preferences 등) 에 접근하기 위해 사용
- Activity와 Application 클래스는 Context 클래스를 확장한 클래스이다.

<br/>

context의 잘못된 사용은 메모리릭 문제로 이어짐

<br/>

# Context의 종류

1. Application Context
2. Activity Context

<br/>

## Application Context

`Activity` 에서 **`applicationContext`** (자바의  경우 **`getApplicationContext()`** 를 통해 얻을 수 있음)라는 프로퍼티를 통해 얻을 수 있는 싱글톤 인스턴스이다

- 어플리케이션 라이프사이클과 묶여있음
- 현재 Context가 정료되고 나서도 Context가 필요한 작업이나, **액티비티 범위를 벗어난 곳에 Context가 필요한 작업**에 적합

<br/>

## Activity Context

**액티비티 안에서만 사용 가능**

**`Activity` 의 라이프 사이클에 종속되어 있음**

`**Activity` 스코프 내에서 사용**될 때 넘겨주거나 `Activity` 와 **라이프사이클이 같은 객체**를 생성할 때 넘겨준다.

**`Activity` 가 소멸되면 해당 `Context` 도 같이 소멸된다**

<br/>

 **`Toast` , `Dialog` 등의 UI 동작에는 Activity Context를 사용**

UI 컴포넌트들은 어차피 Activity 의 라이프 사이클에 종속되는 것들이기 때문에, Activity Context 를 사용해주면 된다.

<br/>

Acitivity는 GarbageCollected가 가능하지만, Application은 ApplicationContext를 사용한 객체를 메모리 할당해제하지 않으면 메모리 누수가 발생한다
