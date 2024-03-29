### 클래스 내부에서 지정하는 것이 아닌 외부에서 사용자에 의해 지정되는 것

<br/>

특정 타입을 미리 지정해주는 것이 아닌 필요에 의해 지정할 수 있도록 하는 일반(Generic)타입

<br/>

<aside>
💡 제네릭 장점

1. 제네릭을 사용하면 잘못된 타입이 들어올 수 있는 것을 컴파일 단계에서 방지할 수 있다
2. 클래스 외부에서 타입을 지정해주기 때문에 따로 타입을 체크하고 변환해줄 필요가 없다. 즉, 관리가 편함
3. 비슷한 기능을 지원하는 경우 코드의 재사용성이 높아진다.
</aside>

<br/>

| 타입 | 설명 |
| --- | --- |
| < T > | Type |
| < E > | Element |
| < K > | Key |
| < V > | Value |
| < N > | Number |
