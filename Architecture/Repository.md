<img width="706" alt="image" src="https://github.com/parkuiery/TIL/assets/128464859/5c354d9f-67cb-40b3-abc7-592821ee5978">

# Repository란?

UI에서 사용할 데이터들을 가져올 수 있도록 접근하는 **LocalDataSource**(앱 내부 데이터-Room,RemoteDataSource /서버 데이터- Retrofit)을 캡슐화하여 사용하는 것이다

# 사용하는 이유

MVC패턴으로 개발을 하게되면 View(Activity/Fragment)에 모든 코드를 작성하여 단점들이 존재하였다.

> View와 Model사이에 의존성이 발생하여 View의 UI 갱신을 위해 Model을 직/간접적으로 참조하여 Activity/Fragment의 크기가 커지고 로직들이 복잡해 질 수록 유지보수가 힘들어진다.

<br>

### 이점

- 도메인과 연관된 모델을 가져오기 위해서 필요한 DataSource가 Presenter  계층에서는 알 필요가 없다
    - DataSource를 새롭게 추가해도 부담이 없다
- DataSource의 변경이 되더라도 다른 계층에는 영향이 없다
- Client는 Repository 인터페이스에 의존하기 때문에 테스트하기 용이하다

<br>

> Repository는 결굴 Presenter 계층과 Data 계층간의 Coupling을 느슨하게 만들어주는것이다.

<br>

1. **View** → **ViewModel**로만 데이터를 가져온다.
2. **ViewModel** → **Repository**로 데이터 접근한다.
3. **Repository** → **DataSource(local/remote)**로 부터 데이터를 요청한다.
