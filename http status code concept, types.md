# http 상태코드 개념, 종류
## http 상태코드란?
```
특정 HTTP요청이 성공적으로 완료되었는지 알려주는 코드이다.
```
## 자주 사용되는 코드
#### 1XX : Informational(정보제공) 
```
최근에는 잘 사용되지 않는다
```
#### 2XX : Success(성공) 
```
: 200 : OK(요청이 성공적으로 수행되었음),(성공)
: 201 : Created (PUT 메소드에 의해 원격지 서버에 파일 생성됨),(생성됨)
: 202 : Accepted(웹 서버가 명령 수신함),(허용됨)
: 204 : No content,(PUT,POST,DELETE 요청의 경우 성공은 했지만 전송할 데이터가 없는 경우),(콘텐츠 없음)
```
#### 3XX : Redirection(리다이렉션)(요청을 완료하려면 추가행동 필요)
```
: 301 : Moved permanently (요구한 데이터를 변경된 타 URL에 요청함/Redirect된 경우),(영구 이동)
: 302 : Found (리다이렉트 요청 메소드가 GET으로 변하고 본문이 제거될 수 있음)
: 307 : Temporary Redirect (클라이언트가 요청한 리소스가 다른 URI에 있으며 이전 요청과 동일한 메소드를 사용해서 요청해야 할 때 서버가 클라이언트에 욫청을 직접 보냄)
: 308 : Permanent Redirect (요구한 데이터를 변경된 타 URL에 요청하고 요청 방식을 그대로 유지함)
```
#### 4XX : Client Error(클라이언트 에러) 
```
: 400 : Bad Request (사용자의 잘못된 요청을 처리할 수 없음),(잘못된 요청)
: 401 : Unauthorized (인증이 필요한 페이지를 요청한 경우),(권한 없음)
: 403 : Forbidden (접근 금지, 디텍터리 리스팅 요청 및 관리자 페이지 접근 등을 차단),(금지됨)
: 404 : Not found, (요청한 페이지 없음),(찾을 수 없음)
```
#### 5XX : Server Error(서버 에러)
```
: 500 : internal server error (내부 서버 오류)
: 503 : Service unnailable (서비스 제공 불가)(요청 처리 준비X)
```
## 전체 코드
#### 1XX : Informational(정보제공) 
```
정보전송 : 100 : Continue (클라이언트로 부터 일부 요청을 받았으면 나머지 정보를 계속 요청함),(계속)
임시응답 : 101 : Switching protocols(프로토콜 전환)
         : 102 : Processing (처리중)
```
#### 2XX : Success(성공) 
```
성공 : 200 : OK(요청이 성공적으로 수행되었음),(성공)
     : 201 : Created (PUT 메소드에 의해 원격지 서버에 파일 생성됨),(생성됨)
     : 202 : Accepted(웹 서버가 명령 수신함),(허용됨)
     : 203 : Non-authoritative information (서버가 클라이언트 요구 중 일부만 전송),(신뢰할 수 없는 정보)
     : 204 : No content,(PUT,POST,DELETE 요청의 경우 성공은 했지만 전송할 데이터가 없는 경우),(콘텐츠 없음)
     : 205 : Reset Content (콘텐츠 재설정)
     : 206 : Partial Content (일부 콘텐츠)
     : 207 : Multi-Status (다중 상태)
```
#### 3XX : Redirection(리다이렉션)(요청을 완료하려면 추가행동 필요)
```
     : 300 : Multiple Choices (여러 선택 항목)
     : 301 : Moved permanently (요구한 데이터를 변경된 타 URL에 요청함/Redirect된 경우),(영구 이동)
     : 302 : Not temporarliy (요구한 데이터를 변경된 타 URL에 요청함/Redirect된 경우),(다른 위치 찾음)
     : 303 : See Other (다른 위치 보기)
     : 304 : No content, (PUT,POST,DELETE 요청의 경우 성공은 했지만 전송할 데이터가 없는 경우),(수정되지 않음)
     : 305 : Use Proxy (프록시 사용)
     : 306 : Unused (예전 버전에서 사용하다가 현재는 사용하지 않는 상태 코드)
     : 307 : Temporary Redirect (임시 리다이렉션)
     : 308 : Permanent Redirect (요구한 데이터를 변경된 타 URL에 요청하고 요청 방식을 그대로 유지함)
   ```
#### 4XX : Client Error(클라이언트 에러) 
```
     : 400 : Bad Request (사용자의 잘못된 요청을 처리할 수 없음),(잘못된 요청)
     : 401 : Unauthorized (인증이 필요한 페이지를 요청한 경우),(권한 없음)
     : 402 : Payment required(예약됨),(결제 필요)
     : 403 : Forbidden (접근 금지, 디텍터리 리스팅 요청 및 관리자 페이지 접근 등을 차단),(금지됨)
     : 404 : Not found, (요청한 페이지 없음),(찾을 수 없음)
     : 405 : Method not allowed (허용되지 않는 http method 사용함),(허용되지 않은 메소드)
     : 406 : Not Acceptable (수용할 수 없음)
     : 407 : Proxy authentication required (프락시 인증 요구됨),(프록시 인증 필요)
     : 408 : Request timeout (요청 시간 초과)
     : 409 : Conflict (충돌)
     : 410 : Gone (영구적으로 사용 금지),(사라짐)
     : 411 : Length Required (길이 필요)
     : 412 : Precondition gailed (전체 조건 실패),(사전 조건 실패)
     : 413 : Request Entity Too Large (요청 객체가 너무 큼)
     : 414 : Request-URI too long (요청 URL 길이가 긴 경우임)
     : 415 : Unsupported Media Type (지원되지 않는 미디어 유형)
     : 416 : Range Not Satisfiable (처리할 수 없는 요청 범위)
     : 417 : Expectation Failed (예상 실패)
     : 422 : Unprocessable Entity (처리할 수 없는 엔티티)
     : 423 : Locked (잠김)
     : 424 : Failed Dependency (의존 관계로 실패)
     : 426 : Upgraded Required (업그레이드 필요함)
     : 428 : Precondition Required (사전 조건 필요함)
     : 429 : Too Many Requests (너무 많은 요청)
     : 431 : Reauest Header Fields Too Large (너무 큰 헤더)
     : 444 : Connection Closed Without Response (응답 없이 연결 닫음)
     : 452 : Unavailable For Legal Reasons (법적 사유로 불가)
   ```
#### 5XX : Server Error(서버 에러)
```
     : 500 : internal server error (내부 서버 오류)
     : 501 : Not implemented (웹 서버가 처리할 수 없음),(구현되지 않음)
     : 502 : Bad Gateway (불량 게이트웨이)
     : 503 : Service unnailable (서비스 제공 불가)(요청 처리 준비X)
     : 504 : Gateway timeout (게이트웨이 시간 초과)
     : 505 : HTTP wersion not supported (해당 http 버전 지원되지 않음)
     : 507 : Insufficient Storage (용량 부족)
   ```