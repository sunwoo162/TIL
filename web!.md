# web
## 1. html이란 무엇인가
설명
```
@ HTML(Hypertext Markup Language)은 웹 페이지의 구조와 내용을 정의하는 코드로, 웹사이트의 기본적인 구성 요소이다
@ HTML은 프로그래밍 언어가 아니라 마크업 언어이다.
@ Hypertext : 하이퍼텍스트 : 관련 항목을 연결하기 위해 구성된 텍스트(종종 이미지 등 삽입 포함)
@ Markup : 마크업 : 하드카피나 소프트카피로 출력될 모든 활자에 관한 스타일 가이드
@ Language : 언어 : 컴퓨터 시스템이 명령어를 이해하고 해석할 때 사용하는 언어
웹페이지의 구조를 결정한다(상호작용 가능은 불가)
```
요소
```
시작 태그, 글자, 내용, 종료 태그로 이루어짐(종료 태그 대신 웹페이지에 삽입하려는 콘텐츠의 소스나 링크가 있는 경우 비어 있음)
<img> : 웹페이에 이미지를 삽입
```
기본구조
```
<!DOCTYPE html> : 이 코드에서 HTML5를 사용하고 있음을 명시한다
<html> : 모든 HTML 문서의 루트, 혹은 최상이 요소이다. 다른 모든 요소는 이 안에 래핑되어야함
  <head> : 페이지 타이틀, 스타일시트, SEO용 메타 인포메이션 같은 정보가 있다
    <meta charset="UTF-8" /> : 페이지의 메타 인포메이션을 전달하는 빈 요소
    <meta http-equiv="X-UA-Compatible" content="IE=edge" /> : 페이지의 메타 인포메이션을 전달하는 빈 요소
    <meta name="viewport" content="width=device-width, initial-scale=1.0" /> : 페이지의 메타 인포메이션을 전달하는 빈 요소
    <title>Definition of HTML</title> : 웹페이지의 타이틀을 정의한다
  </head> : 페이지 타이틀, 스타일시트, SEO용 메타 인포메이션 같은 정보가 있다
  <body> : HTML 문서의 모는 내용은 body 태그 안에 있다(전체 페이지에 단 하나의 body 태그만 존재 가능)
    <!--Page content such as text and images goes in here-->
  </body> : HTML 문서의 모는 내용은 body 태그 안에 있다(전체 페이지에 단 하나의 body 태그만 존재 가능)
</html> : 모든 HTML 문서의 루트, 혹은 최상이 요소이다. 다른 모든 요소는 이 안에 래핑되어야함
```
## 2. http란 무엇인가
설명
```
@ Hyper Text Transfer Protocoal의 약자로, World Wide Wed(WWW,웹) 상에서 데이터를 주고받기 위한 프로토콜이다
@ 클라이언트(보통 웹 브라우저)와 서버간의 요청(request)과 응답(response)을 통해 작동한다
@ 다양한 종류 데이터(html,css,javaScript,png,git,mp4)를 전송할 수 있도록 설계 된 프로토콜이다
@ 웹 페이지에 포함된 각 구성 요소(이미지, 텍스트, HTML,영상 등)는 대부분 개별적인 HTTP 요청을 통해 서버로부터 요청된다
@ 일반적으로 TCP/IP 통신 프로토콜 기반으로 동장한다.
@ HTTP를 통해 전달되는 자료는 http:로 시작하는 URL(인터넷 주소)로 조회할 수 있으며, 사용하는 포트는 80번이다.
@ 상태가 없는 (stateless) 프로토콜: 데이터를 주고받기 위해 행해지는 각각의 데이터 요청이 서로 독립적으로 관리되는것(이전 데이터 요청과 다음 데이터 요청이 서로 관련 없다)
@ 단반향성 : 하나의 요청에 하나의 응답을 하는 방식으로 동작
```
단점
```
@ HTTP는 데이터를 평문(사람이 알아볼 수 있는 정보)으로 전송해 도청 및 데이터 변조의 위험이 있다.
@ 중간에서 패킷을 가로채어 내용을 엿볼 수 있고, 필요에 따라 수정할 수도 있기에 보안에 취약하다
@ 이를 보안하기 위해 나온 것이 HTTPS(Hypertext Transfer Protocol Secure)이다
@ HTTPS : HTTP에 SSL(Secure Socket Layer)/TLS(Transport Layer Security)프로토콜을 통해 세션 데이터가 암호화된 상태로 전송된다
```
흐름
```
1. 사용자가 웹 브라우저의 주소창에 https://www.google.com을 입력한다.
2. 브라우저는 입력된 도메인 이름(www.google.com)을 IP 주소로 변환하기 위해 DNS(Domain Name System)서버에 요청을 보낸다. DNS 서버는 해당 도메인의 IP 주소로 응답한다.
3. 브라우저는 받은 IP 주소를 통해 구글 서버와 TCP 연결을 설정한다.
4. TCP 연결이 설정되면, 브라우저는 HTTP 요청 메세지를 구글 서버에 보낸다.
5. 서버가 요청을 처리하고 HTTP 응답을 전송한다.
6. 브라우저가 응답을 받아 화면에 구글 웹 사이트를 표시한다.
```
요청 메서드
```
1. GET : 정보를 요청하기 위해 사용 (조회)
```
```
2. HEAD : GET 요청과 동일하지만, 응답 바디를 제외한 헤더 정보만을 요청
```
```
3. POST : 서버에 데이터를 전송(추가)할 때 사용 (등록)
```
```
4. PUT : 정보를 업데이트(갱신)하기 위해 사용, 정보 변경 (수정)
```
```
5. DELETE : 정보를 삭제하기 위해 사용 (삭제)
```
```
6. OPTIONS : 서버에서 지원하는 HTTP 메서드의 목록을 요청할 때 사용
```
```
7. PATCH : 리소스의 일부분을 수정
```
```
8.CONNECT : 프록시 동작의 터널 접속을 변경
```
## 3 http 상태코드
1XX : Informational(정보제공)
2XX : Success(성공)
3XX : Redirection(리다이렉션)
4XX : Client Error(클라이언트 에러)
5XX : Server Error
```
정보전송 : 100 : Continue (클라이언트로 부터 일부 요청을 받았으면 나머지 정보를 계속 요청함),(계속)
임시응답 : 101 : Switching protocols(프로토콜 전환)
         : 102 : Processing (처리중)
성공 : 200 : OK(요청이 성공적으로 수행되었음),(성공)
     : 201 : Created (PUT 메소드에 의해 원격지 서버에 파일 생성됨),(생성됨)
     : 202 : Accepted(웹 서버가 명령 수신함),(허용됨)
     : 203 : Non-authoritative information (서버가 클라이언트 요구 중 일부만 전송),(신뢰할 수 없는 정보)
     : 204 : No content,(PUT,POST,DELETE 요청의 경우 성공은 했지만 전송할 데이터가 없는 경우),(콘텐츠 없음)
     : 205 : Reset Content (콘텐츠 재설정)
     : 206 : Partial Content (일부 콘텐츠)
     : 207 : Multi-Status (다중 상태)
     : 300 : Multiple Choices (여러 선택 항목)
     : 301 : Moved permanently (요구한 데이터를 변경된 타 URL에 요청함/Redirect된 경우),(영구 이동)
     : 302 : Not temporarliy (요구한 데이터를 변경된 타 URL에 요청함/Redirect된 경우),(다른 위치 찾음)
     : 303 : See Other (다른 위치 보기)
     : 304 : No content, (PUT,POST,DELETE 요청의 경우 성공은 했지만 전송할 데이터가 없는 경우),(수정되지 않음)
     : 305 : Use Proxy (프록시 사용)
     : 306 : Unused (예전 버전에서 사용하다가 현재는 사용하지 않는 상태 코드)
     : 307 : Temporary Redirect (임시 리다이렉션)
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
     : 500 : internal server error (내부 서버 오류)
     : 501 : Not implemented (웹 서버가 처리할 수 없음),(구현되지 않음)
     : 502 : Bad Gateway (불량 게이트웨이)
     : 503 : Service unnailable (서비스 제공 불가)
     : 504 : Gateway timeout (게이트웨이 시간 초과)
     : 505 : HTTP wersion not supported (해당 http 버전 지원되지 않음)
     : 507 : Insufficient Storage (용량 부족)
```
## 4. 프론트엔드, 백엔드의 차이와 하는 일
1. 프론트엔드란?

@ 하는일
```
웹사이트나 앱 등의 사용자 인터페이스(UI)를 개발하는 분야를 말한다.(사용자가 실제로 보고 상호작용하는 부분)
샤용자 경험(UX)을 개선하기 위해 레이아웃, 색상 글꼴 등의 디자인 요소를 조율하고, 사용자가 버튼을 클릭하거나 입력한 정보를 처리하는 등의 기능을 구현한다
웹사이트나 앱의 반응성을 향상시키기 위해 다양한 디바이스에서 동작하는 코드를 작성하는 등의 작업도 수행한다.
```
@ 프로그램
```
언어 : HTML,CSS,JavaScript
에디터 : Visual Studio Code,Sublime Text,Atom 등
웹 브라우저 : Google Chrome,Mozilla Firefox,Microsoft Edge 등
그래픽 에디터(디자인 요소) : Adobe Photoshop,Sketch,Figma 등
버전 관리 도구 : Git, SVN 등
2. 백앤드란?
@ 하는일
```
데이터베이스,서버,애플리케이션 서버 등의 기술을 사용하여 웹사이트나 앱의 로직과 기능을 개발하는 분야를 말한다
사용자가 입력한 정보를 처리하고, 데이터를 저장하고, 인증 및 보안과 같은 중요한 기능을 담당한다.
API(Application Programming Interface)를 개발하여 프론트 앤드와 데이터베이스 간의 통신을 관리한다.
```
@ 프로그램
```
언어 : JAVA,Python,C++,PHP,Node,js 등
데이터베이스 관리 시스템(DBMS) : MySQL,PostgreSQL,Oracle,MongoDB 등
웹 서버 : Apache,Nginx,Mircrosoft IIS 등
3. 프론트앤드와 백앤드의 차이
@ 기본적인 개념
```
프론트앤드 : 모바일 애플리케이션이나 웹 등을 할때 두눈으로 접하는 인터페이스
백앤드 : 두 눈으로는 보이지 않는 인터페이스 외의 부분
```
@ 개발이 이루어지는 분야
```
프론트앤드 : 인터페이스와 사용자 경험
백앤드 : 서버의 구축과 데이터베이스 관리
