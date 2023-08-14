# Retrofit
**안드로이드와 서버간의 REST API 통신을 도와주는 라이브러리**

### 장점

1. **높은 성능**

  빠른 성능

![image](https://github.com/parkuiery/TIL/assets/128464859/f08b4d45-22be-4bcb-839b-d0169ff7d573)

2. **뛰어난 가독성**

  Annotation으로 HTTP 메소드를 정의함

  → 코드의 구현이 쉬워지고 직관적으로  코드 설계가능

3. **쉬운 유지보수**

  서버 연동 시 주로 주고받는 데이터인 JSON, XML을 자동으로 파싱해주는 Converter 연동을 지원

  **converter-gson** - JSON 타입의 결과를 객체로 자동 매핑(파싱)해줌

<br/>

# 모델 생성

**Model :  서버 연동을 위해 사용하는 데이터 추상화 클래스**

Convertor가 JSON 데이터를 자동으로 파싱

객체를 생성한 후 모델에서 정의한 변수에 데이터를 담아줌

이것을 보통 **DTO 클래스**라고 부른다

<br/>

# 서비스 인터페이스 정의

annotation으로 HTTP Method를 지정

서버에 전송할 데이터를 추가 

Service는 **Retrofit에서 사용하는 용어로 API를 정의하는 인터페이스**를 의미
