# 조건문

### 변수에 직접 if 문 사용하기

```java
var a = 5
var b = 3
var bigger = if (a>b) a else b
```

<br/>

### if 문의 마지막 값을 반환값으로 사용하기

```java
var a = 5
var b = 3
var bigger = if (a > b) {
	var c = 30
	a // 마지막 줄의 a 값이 변수 bigger에 저장
} else {
		b
}
```

<br/>

## 조건문 when

switch문과 비슷

범위 값 처리 가능 → 들어갈수 있는 값이 넓음

```java
when (파라미터) {
    비교값1 -> {
        
		}
    비교값2 -> {
        
    }
   	else -> {
        //변수값이 앞에서 비교한 값들과 다르면 이 영역이 실행된다
    }
}
```

콤마(, )로 구분해서 한 번에 비교 가능 

(..) → 범위 연산자

파라미터 없이 if문 처럼 사용 가능
