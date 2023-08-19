# 배열

### 문자 배열에 빈 공간 할당하기

```java
var stringArray = Array(10, { "" })
```
길이가 10이고 모든 요소가 빈 문자열로 초기화된 문자열 배열 생성

<br/>

### arrayOf()

```kotlin
val arr:Array<Int> = arrayOf(1,2,3)

val arr = arrayOf(1,2,3)
```

생성과 동시에 초기화

자료형은 생략 가능

<br/>

**Null로 된 값을 생성하고 싶을 때**

```kotlin
val arr = arrayOfNulls<Int>(10)
```

초깃값이 null인 길이 10의 int형 배열 생성

<br/>

### Array()

```kotlin
	val arr: Array<Int> = Array(3) { 0 }
```

arr에는 [0,0,0]으로 초기화

```kotlin
val arr: Array<Int> = Array(3) { i -> i }
```

arr에는 [0,1,2]으로 초기화

<br/>

## 이차원 배열

```kotlin
var arr = Array<Array<Int>>(3){Arraay<Int>(3){ 0 } }
```

```kotlin
var arr1 = Array(3, { Array(3, {0}) })
var arr2 = arrayOf(arrayOf(1, 2, 3), arrayOf(4, 5, 6))
```
