#  HTTP Method(메서드)
### 의미
```
클라이언트 - 서버 구조에서 요청과 응답이 이루어지는 방식
```
### 사용 이유
```
리소스와 동작을 분리하기 위함
```
### 종류
```
* 크게 8가지
1. GET : 리소스를 조회
2. POST : 데이터 추가,등록
3. PUT : 리소스 대체,수정/해당 리소스가 없으면 새롭게 생성
4. DELETE : 리소스 삭제
5. PATCH : 리소스 부분 변경(수정)
6. HEAD : GET과 동일하나,HTTP 메세지의 body 부분을 제외하고 조회
7. OPTIONS : 서버와 브라우저가 통신하기 위한 통신 옵션을 확인하기 위함
8. CONNECT : 대상 자원으로 식별되는 서버에 대한 연결 요청
```
* 1.~5.를 자주 이용
### GET 메서드
```
리소스를 조회하는 메서드
멱등성이라는 개념을 지니고 있어, 여러 번 조회 요청을 하여도 리소스는 변하지 않음
서버에서 데이터를 전달하는 경우, 쿼리스트링을 통해서 전달(URL의 맨 마지막에 나옴)
* 해당 쿼리스트링은 클라이언트에게 전달하는 데이터 정보가 무장비 상태로 노출되므로 유의해야한다
```
예시
```
GET /search?q=hello&hl=ko HTTP/1.1
Host: www.google.com
```
### POST 메서드
```
리소스를 생성하는데 사용하는 메서드
성공적으로 creation을 완료하면 201 HTTP 응답을 반환한다
데이터를 메세지 바디에 쿼리 파라미터 형식으로 전달한다
데이터가 외부로 노출되지 않는다
조회가 가능하지만 멱등성을 지니지 않아 똑같은 결과갑 보장 X
캐싱을 이용하여 조회 속도가 POST 메서드에 비해 우수하다
데이터를 전송할 때 Body에 담아 전송하므로 메세지 길이 제한이 없다
문자열 데이터 뿐만 아니라 RadioButton같은 객체들의 값도 전송할 수 있다
* 쿼리 파라미터는 key - value 형식으로 되어 있다
```
예시
```
POST /members HTTP/1.1
Content-Type: application/json

{
 "username": "hello",
 "age": 20
}
```
### PUT 메서드
```
리소스를 완전히 대체하는 개념(덮어쓰기)
클라이언트가 리소스를 식별할 수 있다
부분 수정이 불가
멱등성을 지님
```
```
PUT /members/100 HTTP/1.1
Content-Type: application/json

{
 "username": "hello",
 "age": 20
}
```
### DELETE 메서드
```
리소스를 제거하는 역할
멱등성을 지님
```
예시
```
DELETE /members/100 HTTP/1.1
Host: localhost:8080
```
### PATCH 메서드
```
PUT과 같이 리소스를 수정하는 역할을 하지만 리소스를 부분 변경한다는 점에서 차이가 있다
기존 데이터 A,B가 존재할 때,B = C 로 대체 후 PATCH 요청을 하면 데이터가 A,C로 변경된다
PATCH 메서드를 지원하지 않는 서버도 있는데,그럴 경우 POST를 사용한다
멱등성을 지니지 않음
```
예시
```
PATCH /members/100 HTTP/1.1
Content-Type: application/json 

{
 "age": 50 
}
```
### 데이터 전달 방식
##### 1. 쿼리 파라미터(쿼리 스트링)을 통한 데이터 전송(url)
```
GET 메서드를 주로 사용한다
주로 검색 시에 검색어를 넘길 때 사용한다(필터)
게시판 리스트의 정렬 조건을 넘길  사용한다(정렬)
```
##### 2. 메세지 바디
```
POST,PUT,PATCH를 주로 사용한다
회원가입, 상품 주문 시에 사용된다
```
### 정적 데이터 조회
```
이미지나 정적 텍스터 문서 같은 경우에는 조회이므로 GET을 사용
정적 데이터는 일반적으로 쿼리 파라미터 없이 리소스 경로로 단순하게 조회가 가능
```
### 동적 데이터 조회
```
주로 검색 또는 게시판 글 목록을 정렬할 때 사용
조회 조건을 줄여주는 필터, 조회 결과를 정렬하는 정렬 조건을 쿼리 파라미터로 넘길 때 주로 사용
조회는 GET 사용
GET은 대부분 쿼리 파라미터를 사용하여 데이터를 전달
```
### HTML Form 데이터 전송
```
HTML Form 전송은 GET,POST만 가능
```
### POST 전송
```
웹 브라우저가 form을 읽어 HTTP 메세지를 전송
submit 시 action 경로로 POST 전송
form의 name 필드로 쿼리 파라미터와 같은 형식으로 (key-value) 메시지 바디를 구성
전송 데이터를 url encoding 처리하여 전송
```
### form을 GET으로 전송
```
GET이므로 바디 대신 쿼리 파라미터에 넣음
save는 저장한다는 뜻이므로 GEt을 사용하면 안됨
리소스가 변경될  GET을 사용하지 않는다
```
### GET 전송
```
특정 조건을 조회할  GET 사용 가능
```
### multipart/form-data
```
파일 업로드 같은 바이너리 데이터 전송 시 사용
```
### HTTP API 전송
서버 to 서버(백엔드 시스템끼리 통신하는 경우)
앱 클라이언트(아이폰,안드로이드)
웹 클라이언트(HTML에서 Form 대신 자바 스크립트를 통한 통신을 하는 경우)(Ajax)
GET(조회)(쿼리 파라미터로 데이터 전달)
POST,PUT,PATCH(메시지 바디를 통해 데이터 전송)
Content-Type : application/json 을 주로 사용(TEXT,XML,JSON) 등이 있다
