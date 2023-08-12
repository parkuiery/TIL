### 필드 값에 부적절한 값이 대입되는 것을 막기 위해서 사용 

<br/>
 
  **Getter** : 객체의 속성(property) 값을 반환하는 메서드

변수들의 **외부 노출을 제한**하고, **노출 범위를 정해주는 것** (이러한 속성이 은닉성)

**클래스의 필드에 직접 접근하는걸 막기 위해서 사용함**  

 <br/>
  
  **Setter** : 객체의 값을 설정, 변경하는 메서드  

변수의 값 대입이 여러 곳에서, 제한 없이 가능한 것을 **접근 제한자로 막고**,

접근 범위에 한해서 메소드로 대입 전 값을 처리 후 대입되게 하기 위해 사용 됨

<br/>

```java
private 타입 fieldName;   //필드 접근 제한자 : private

//Getter
public 리턴타입 getFieldName() {
		return FieldName;
}

//Setter
public void setFieldName(타입 fieldName) {
		this.fieldName = fieldName;
}
```

<br/>

Getter : getFieldName( )

- 접근 제헌자 : public
- 리턴 타입 : 필드의 리턴 타입
- 메소드 이름 : get + 필드 이름 (첫문자는 대문자)
- 리턴값 : 필드값

Setter : setFieldName(타입 fieldName)

- 접근 제한자 : public
- 리턴 타입 : void
- 메소드 이름 : set + 필드 이름 (첫문자는 대문자)
- 매개 변수 타입 : 필드 타입

<br/>

만약 필드 타입이 boolean일 경우 , Getter는 get으로 시작하지 않고 is로 시작하는 것이 관례이다.

Getter : isStop( )

- 접근 제한자 : public
- 리턴 타입 : 필드 타입
- 메소드 이름 : is + 필드이름 (첫문자는 대문자)
- 리턴값 : 필드값

Setter : setStop(boolean stop)

- 접근 제한자 : public
- 리턴 타입 : void
- 메소드 이름 : is + 필드이름 (첫문자는 대문자)
- 매개 변수 타입 : 필드 타입
