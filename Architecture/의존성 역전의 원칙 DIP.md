# DIP (Dependency Inversion Principle)

## **→ 의존성 역전의 원칙**

> 의존 관계를 맺을 때 변하기 쉬운 것에 의존하기 보다는 변화하지 않는 것에 의존하라!
> 

**고수준 모듈은 저수준 모듈의 구현에 의존해서는 안 되며, 저수준 묘듈이 고수준 모듈에 의존해야 한다**

- **고수준 모듈**: 입력과 출력으로부터 먼(비즈니스와 관련된) 추상화된 모듈
- **저수준 모듈**: 입력과 출력으로부터 가까운(HTTP, 데이터베이스, 캐시 등과 관련된) 구현 모듈

![image](https://github.com/parkuiery/TIL/assets/128464859/6914a986-528d-4d7a-bc69-9556dc0297f9)

의존 역전 원칙에서 의존성이 역전되는 시점은 컴파일 시점이다

### DI의 장점

- boilerplate code를 줄여주므로 유연한 프로그래밍이 가능해진다
- 재사용성이 높아지고 유지보수가 쉬워진다
- 더 편한 유닛 테스트가 가능해진다
- 결합도를 낮추어서 확장성을 높여준다
