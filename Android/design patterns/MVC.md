- View
    1. 사용자에게 보여지는 UI를 나타낸다
    2. Model로부터 data를 받아 사용자에게 보여준다
- Model
    1. 어플리케이션에서 사용되는 data와 그 data를 처리한다
    2. View에 의존적이지 않기 때문에 재사용이 가능하다.
- Controller
    1. 사용자의 입력(Action)을 받고 처리한다.
    2. 주로 Activity나 Fragment로 표현된다.
    3. Model의 data 변화에 따라 View를 선택한다.
- 동작
    1. 사용자의 Action이 Controller에 들어온다.
    2. Controller는 사용자의 Action을 확인하고, Model을 업데이트한다.
    3. Controller는 Model을 이용하여 화면을 나타낸다.
- 특징
    1. Controller는 여러 개의 View를 선택할 수 있는 1:N 구조이다.
    2. Controller는 View를 선택할 뿐 직접 업데이트하지 않는다.
    3. View와 Model을 완벽하게 분리하고, Model 테스트가 용이하다.
- 단점
    1. Controller가 Android API에 종속되어 테스트가 어렵다.
    2. View를 변경하면 Controller도 변경해야 한다.
    3. 많은 코드들이 Controller에 집중되면 성능이 저하되고 유지보수가 어려워진다.
