# Http Method
---

### REST란?

- 자원(Resource): URL
- 행위(Verb): HTTP Method
- 표현(Representations)

<aside>
 HTTP Method
조회: GET
등록: POST
수정: PUT
삭제: DELETE

</aside>

### 전체 종류

GET: 서버로 부터 데이터를 취득

POST: 서버에 데이터를 추가, 작성 등

PUT: 서버의 데이터를 갱신, 작성 등

DELETE: 서버의 데이터를 삭제

HEAD: 서버 리소스의 헤더(메타 데이터의 취득)

OPTIONS: 리소스가 지원하고 있는 메소드의 취득

PATCH: 리소스의 일부분을 수정

CONNECT: 프록시 동작의 터널 접속을 변경

### 멱등성(Idempotence)이란?

여러번 수행해도 결과가 같음을 의미한다. 즉, 호출로 인하여 데이터기 변형이 되지 않는다는 것을 의미한다.

### 1. **GET**

GET 메소드는 주로 데이터를 읽거나(Read) 검색(Retrieve)할 때에 사용되는 메소드이다. 만약에 GET요청이 성공적으로 이루어진다면 XML이나 JSON과 함꼐 200(Ok) HTTP 응답 코드를 리턴한다. 에러가 발생하면 주로 404(Not found) 에러나 400 (Bad request) 에러가 발생한다.

- HTTP  명세에 의하면 GET 요청은 오로지 데이터를 읽을 때만 사용되고 수정할 떄는 사용하지 않는다.
- GET 요청은 idempotent 하다.
- 같은 요청을 여러 번 하더라도 변함없이 항상 같은 응답을 받을 수 있다.
- 데이터를 변경하는 연산에 사용하면 안된다.

예시

```c
GET /user/1
```

데이터를 조회하는 것이기 떄문에 요청시에 Body 값과 Content-Type 가 비워져있다. 조회할 데이터에 대한 정보는 URL을 통해서 파라미터를 받고 있는 모습을 볼 수 있다.

데이터 조회에 성공한다면 Body 값에 데이터 값을 저장하여 성공 응답을 보낸다.

### 2. POST

POST 메소드는 주로 새로운 리소스를 생성(create)할 떄 사용된다.

- POST 요청은 idempotent 하지 않다.
- 같은 POST 요청을 반복해서 했을 떄 항상 같은 결과물이 나오는 것을 보장하지 않는다.
- 두 개의 같은 POST 요청을 보내면 같은 정보를 담은 두 개의 다른 resource를 반환할 가능성이 높다.

예시

```
POST /user
body : {date : "example"}
Content-Type : "application/json"
```

데이터를 생성하는 것이기 떄문에 요청시에 Body 값과 Content-Type 값을 작성해야한다. 해당 예시는 JSON을 통해서 작성된 예시이다.

URL을 통해서 데이터를 받지 않고, Body 값을 통해서 받는다.

데이터 조회에 성공한다면 Body 값에 저장한 데이터 값을 저장하여 성공 응답을 보낸다.

### 3. PUT

PUT는 리소스를 생성 / 업데이트하기 위해 서버로 데이터를 보내는 데 사용된다.

- PUT 요청은 idempotent
- 동일한 PUT 요청을 여러 번 호출하면 항상 동일한 결과가 생성됩니다.

예시

```c
PUT /user/1
body : {date : "update example"}
Content-Type : "application/json"
```

데이터를 수정하는 것이기 떄문에 요청시에 Body 값과 Content-Type  값을 작성해야한다. 

URL 을 통해서 어떠한 데이터를 수정할지 파라미터를 받는다. 그리고 수정할 데이터 값을 Body 값을 통해서 받는다.

데이터 조회에 성공한다면 Body 값에 저장한 데이터 값을 저장하여 성공 응답을 보낸다.

### 4. DELETE

```c
DELETE /user/1
```

데이터를 삭제하는 것이기 떄문에 요청시에 Body 값과 Content-Type 값이 비워져있다.

URL을 통해서 어떠한 데이터를 삭제할지 파라미터를 받는다.

데이터 삭제에 성공한다면 Body 값 없이 성공 응답만 보내게 된다.

---

### POST 방식 vs GET 방식 (보안 측면)

- GET과 비교하여 URL에 데이터의 정보가 들어 있지 않으므로 조금 더 안전하다고 볼 수 있다.

### GET 방식 vs POST 방식 (속도)

- GET 방식은 캐싱을 하기 떄문에 여러번 요청시 저장된 데이터를 활용하므로 조금 더 빠를 수 있다.

### POST vs PUT

- POST와 PUT은 구분해서 사용해야한다. POST는 새로운 데이터를 계속 생성하기 떄문에 요청시마다 데이터를 생성하지만, PUT은 사용자가 데이터를 지정하고 수정하는 것이기 때문에 같은 요청을 계속하더라도 데이터가 계속 생성되지 않는다.

### PUT vs PATCH

- PUT은 지정한 데이터를 전부 수정하는 Method이지만 PATCH는 정보의 일부분이 변경되는 방법이다. 그래서 PUT은 멱등하지만, PATCH는 멱등하다고 볼 수 없다.
