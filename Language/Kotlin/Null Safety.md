# ?

```kotlin
var nullable: String? = null // 컴파일 성공
var nonNull: String = null // 컴파일 에러
```

# !!

객체가 Null이 아닌 것을 확신

만약 Null이면 NPE 발생

# ?.(Safe Call)

nullable한 변수를 검사하여 null이면 NPE 발생하지 않고 그대로  null 출력

# ?:(엘비스 연산자)

변수가 null인지 아닌지 검사하여  null이면 뒤에 있는 결과 실행
