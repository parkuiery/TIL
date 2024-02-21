## 선언형 프로그래밍 패러다임

- 전에는 데이터를 표시하기 위해 UI 계층 구조를 업데이트 해야했음
- 트리를 탐색하고 노트 변경 → 수동적으로 조작하면 오류 발생 커짐
- 데이터를 여러 위치에서 렌더링 하면 업데이트하는 것을 잊기 쉬움
- 화면 전체를 개념적으로 재생성한 후 필요한 변경사항만 적용하는 방식
- 스테이트풀(Stateful) 뷰 계층 구조를 수동으로 업데이트 할 때의 복잡성을 방지
- 선언형 UI 프레임워크

<br>

## 간단한 구성 가능한 함수
- 함수는 `@Composable` 주석으로 주석이 지정되고 모든 Composable 함수에는 이 주석이 있어야한다→ Compose 컴파일러에게 알려줌

<br>

## 선언형 패러다임 전환
- Compose의 선언형 접근 방식에서 위젯은 비교적 스테이트리스(Stateless) 상태이며 settrt, gettet 함수를 노출하지 않음

<img width="709" alt="image" src="https://github.com/parkuiery/TIL/assets/128464859/1281ea51-a585-4bcf-ab57-63ad87863c31">

<img width="705" alt="image" src="https://github.com/parkuiery/TIL/assets/128464859/3dc9b698-ca74-48d7-8eba-848a883b181f">
