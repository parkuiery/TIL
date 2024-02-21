## Modifier이란

> 컴포저블을 장식하거나 강화할 수 있음
> 
- 뷰의 크기, 동작 및 모양 변경
- 접근성 라벨과 같은 정보 추가
- 사용자 입력 처리 (=onClick)
- 스크롤, 확대 축소와 같은 높은 수준의 상호작용 추가

<br>

## Modifier 내장 함수

### padding

- `padding` : 요소 주위에 공간을 배치
- `paddingFromBaseline` : 레이아웃 상단 기준선부터 특정 거리 유지

### Size

- `fillMaxWidth` : 컴포저블이 상위 요소로부터 부여받은 최대 너비를 채우도록 함
- `fillMax / Height / Size / Width` : 각각 match_parent
- `size` : width, height 지정
- `requiredSize` : 사이즈 고정 (size 보다 우선 순위가 높음)
- `matchParentSize` : 상위 Box와 크기가 같아지도록 함
- `weight` : 전체 레이아웃 크기의 비율로 지정

### offeset

- 레이아웃 방향에 따라 지정 가능
- x, y 지정값을 줄 수 있음

상호작용

- `clickable` : 컴포저블이 사용자 입력에 반응하도록 설정, 이벤트 적용

<br>

- Modifier 순서는 매우 중요
- Modifier 재사용 `.then()` 사용 가능
