# TCP
TCP란 뭐야?
TCP는 인터넷에서 데이터를 안전하게 주고받을 수 있게 도와주는 규칙이야.
 예를 들어, 너가 카카오톡 메시지를 보내거나, 웹사이트에 접속할 때 이 TCP가 뒤에서 "잘 도착했는지", "빠뜨린 건 없는지" 확인해주는 거야.

1. 연결 지향 (Connection-Oriented)
TCP는 데이터를 보내기 전에 반드시 "우리 통신해도 될까?" 라고 연결을 먼저 설정해.
?? 예시
너랑 친구가 전화하려면:
너가 전화 걸고(SYN)


친구가 전화 받음(SYN-ACK)


너가 "알겠어!" 라고 함(ACK)


이걸 3-Way Handshake 라고 해. 연결이 만들어지면 데이터 보내기 시작해.

 2. 세그먼트 (Segment)
TCP는 데이터를 한 번에 몽땅 안 보내.
 조각조각 나눠서(세그먼트) 보내고, 순서대로 다시 조립해줘.
 이 조각마다 **번호(시퀀스 번호)**가 있어서 누락되면 다시 요청할 수 있어.

3. 신뢰성 있는 전송
TCP는 "잘 도착했는지 확인"을 중요하게 생각해.
순서 보장: 도착한 순서가 엉망이면 원래 순서로 다시 맞춰줘.


재전송: 도중에 빠졌으면 다시 보냄.


중복 제거: 같은 데이터 여러 번 오면 한 번만 처리.


오류 확인: 데이터가 손상됐는지 검사함 (체크섬 사용)



4. 전이중 방식 (Full Duplex)
TCP는 양방향 통신이 가능해.
 너도 말하고, 친구도 동시에 말할 수 있는 거야. (전화랑 똑같아!)

5. 스트림 전송 (Stream)
TCP는 데이터를 마치 물 흐르듯이 끊김 없이 전달해.
 "한 줄씩 보낸다"가 아니라 그냥 흐르게 보낸다고 생각하면 돼.
 → 개발자는 따로 메시지 단위로 쪼개줘야 해!

6. 포트 (Port)
한 컴퓨터 안에서도 여러 앱이 동시에 통신할 수 있어야 해.
 그래서 각각의 통신을 구분하려고 포트 번호를 써.
80번 포트: 웹서버 (HTTP)


443번 포트: 보안 웹서버 (HTTPS)


동적 포트: 클라이언트가 임의로 쓰는 번호



7. TCP 상태 천이 (State Machine)
TCP는 연결이 만들어지고 종료될 때까지 여러 상태를 거쳐.
 대표적인 상태들:
상태
설명
LISTEN
서버가 연결 요청을 기다림
SYN-SENT
클라이언트가 SYN 보냄
ESTABLISHED
연결 완료, 데이터 송수신 가능
FIN-WAIT
연결 종료 중
CLOSED
연결이 완전히 종료됨

이건 TCP 상태 천이도라고 하는데, 실제 개발 중 문제가 생기면 로그에서 자주 보게 돼.



# TCP의 개념에 관한 문제
문제 1
TCP는 데이터를 전송하기 전에 어떤 과정을 먼저 수행하는가?

A. 데이터 암호화
B. 연결 설정
C. 포트 검사
D. 세그먼트 나누기

정답: B. 연결 설정

해설:
TCP는 연결지향 프로토콜이기 때문에, 데이터를 보내기 전에 반드시 상대방과의 연결을 먼저 설정(3-way handshake) 해야 해요.
# TCP 제어기법
문제2
Q. 다음 중 TCP의 특징으로 올바른 것은 무엇인가?

A. 비연결형이며 메시지 기반이다
B. 신뢰성이 낮고 순서를 보장하지 않는다
C. 연결지향이며 데이터의 순서를 보장한다
D. 브로드캐스트를 기본으로 지원한다

정답: C. 연결지향이며 데이터의 순서를 보장한다

해설:
TCP는 연결지향(Connection-Oriented) 프로토콜로, 데이터를 신뢰성 있게 전송하고 순서도 보장해요.
비연결형, 메시지 기반, 브로드캐스트 등은 주로 UDP의 특징이에요.
개발에서 TCP를 어떻게 써?
TCP는 보통 소켓 프로그래밍에서 사용해.
예: Python TCP 서버 만들기 (간단 예시)
python
복사편집
import socket

server = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
server.bind(('localhost', 5000))
server.listen(1)
print("서버 대기 중...")

conn, addr = server.accept()
print("클라이언트 연결됨:", addr)

data = conn.recv(1024)
print("받은 데이터:", data.decode())

conn.send(b'Hello Client!')
conn.close()

예: 클라이언트 코드
python
복사편집
client = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
client.connect(('localhost', 5000))
client.send(b'Hello Server!')
print(client.recv(1024).decode())
client.close()

이렇게 서버/클라이언트 연결 → 데이터 주고받기 → 연결 종료 과정을 TCP가 관리해줘.

요약하면
항목
설명
연결 방식
연결지향(3-way handshake)
데이터 단위
세그먼트
특징
신뢰성, 순서 보장, 재전송
전송 방식
전이중(양방향 동시에 가능)
포트
통신을 앱 단위로 구분
상태
여러 단계의 상태천이
개발 활용
소켓 프로그래밍, HTTP 등 대부분 TCP 기반

1. TCP를 왜 쓰는가?
TCP는 "안정적이고 순서가 맞는 통신"이 필요한 경우에 사용합니다.
TCP를 써야 하는 대표적인 상황:
상황
이유
웹 서버/클라이언트 통신 (HTTP/HTTPS)
웹페이지는 빠짐없이 정확히 로드돼야 함
파일 전송 (FTP, SFTP 등)
모든 데이터가 손실 없이 도착해야 함
채팅 서비스
메시지 순서가 중요하고, 누락되면 안 됨
DB 서버 통신 (MySQL, PostgreSQL 등)
데이터 정확성이 중요함


2. TCP 개발 예시 (소켓 프로그래밍)
TCP를 직접 사용할 때는 소켓(Socket) 을 이용해서 서버-클라이언트를 구현합니다.
Python 예시 (간단한 채팅 구조)
서버 (server.py)
python
복사편집
import socket

server_socket = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
server_socket.bind(('localhost', 12345))
server_socket.listen()

print("서버 대기 중...")

conn, addr = server_socket.accept()
print("클라이언트 연결됨:", addr)

data = conn.recv(1024)
print("받은 데이터:", data.decode())

conn.sendall(b'안녕하세요, 클라이언트님!')
conn.close()

클라이언트 (client.py)
python
복사편집
import socket

client_socket = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
client_socket.connect(('localhost', 12345))

client_socket.sendall(b'안녕하세요, 서버님!')
response = client_socket.recv(1024)
print("서버 응답:", response.decode())

client_socket.close()

이 코드에서 TCP가 자동으로 처리해주는 기능들:
연결 설정 (3-way handshake)
데이터 손실 방지
순서 보장
재전송 처리

3. 개발 활용 팁
언어별 TCP 활용 기술
언어
기술
Python
socket, asyncio, selectors
Java
Socket, ServerSocket, NIO
JavaScript (Node.js)
net 모듈 사용
C
socket(), connect(), send(), recv() 함수 직접 사용
Go
net 패키지 (net.Listen, net.Dial)


4. 실전에서 활용되는 TCP 관련 기술 스택
기술
설명
HTTP/1.1, HTTP/2
TCP 기반의 웹 통신 프로토콜
gRPC
HTTP/2 + TCP 기반 고성능 RPC 시스템
TLS (HTTPS)
TCP 위에 보안 계층을 추가한 것
FTP, SMTP, POP3
파일/메일 전송에 TCP 사용
MySQL, PostgreSQL, Redis
TCP를 통해 클라이언트와 DB 연결


5. 활용 시 주의할 점
TCP는 기본적으로 블로킹 방식이므로, 고성능 서버 개발 시에는 비동기(Async), 멀티스레드, 이벤트 루프 등을 같이 사용해야 해요.
스트림 기반이라 메시지 경계를 직접 처리해야 할 수 있어요. (구분자 사용, 길이 앞에 붙이기 등)

요약: TCP 개발 활용법 핵심 정리
항목
설명
개발 목적
신뢰성 높은 통신 구현
사용 방식
소켓 프로그래밍 (Server-Client)
개발 언어
대부분 언어에서 지원 (Python, Java, C 등)
활용 분야
웹, 채팅, 게임 서버, DB 통신 등
추가 고려사항
성능 최적화(멀티스레드/비동기), 메시지 구분 처리 필요

# TCP를 개발에 활용하는 방법에 관한 문제
문제 1
Q. 다음 중 TCP를 사용하는 이유로 가장 적절한 것은 무엇인가?

A. 빠른 전송 속도를 우선시하기 위해
B. 데이터가 순서 없이 도착해도 상관없는 경우
C. 신뢰성 있게 데이터를 주고받고 싶을 때
D. 여러 기기에 동시에 데이터를 보내고 싶을 때

정답: C. 신뢰성 있게 데이터를 주고받고 싶을 때

해설:
TCP는 데이터의 손실, 순서 오류, 중복 전송을 방지해주는 신뢰성 높은 통신이 특징이에요.
속도 위주(B), 순서 무관(A), 브로드캐스트(D)는 UDP의 특징에 가깝습니다.

문제 2
Q. TCP를 이용해 서버-클라이언트 간 통신을 개발할 때 주로 사용하는 프로그래밍 기술은 무엇인가?

A. RESTful API
B. 소켓 프로그래밍
C. 브라우저 DOM 조작
D. 세션 쿠키 관리

정답: B. 소켓 프로그래밍

해설:
TCP를 직접 사용할 때는 소켓(Socket) 을 이용해서 서버와 클라이언트를 연결하고 통신합니다.
REST API는 TCP 위에 있는 HTTP에서 사용하는 방식이고, DOM 조작은 웹 UI 기술입니다.
1. 연결지향 (Connection-Oriented)
TCP는 데이터를 전송하기 전에 반드시 송신자와 수신자 사이에 연결을 먼저 설정해야 해요.
 이걸 전화 연결에 비유할 수 있어요.
예: 카카오톡으로 메시지를 보내기 전에 상대와 연결을 먼저 맺는 것


이 연결은 3-Way Handshake라는 절차를 통해 이루어져요.

2. 3방향 / 4방향 핸드쉐이크
3-Way Handshake (연결 설정)
SYN: 클라이언트가 서버에 연결 요청


SYN-ACK: 서버가 수락 및 응답


ACK: 클라이언트가 응답 확인 → 연결 완료


연결이 만들어져야 데이터 전송이 시작돼요.

4-Way Handshake (연결 종료)
클라이언트가 FIN → 종료 요청
서버가 ACK → 응답
서버가 FIN → 종료 요청
클라이언트가 ACK → 응답 → 연결 종료
연결을 서로 순서 있게 종료하는 절차예요.

3. 세그먼트 (Segment)
TCP는 데이터를 작게 쪼개서 보내요.
 이 조각 하나하나가 세그먼트예요.
각 세그먼트에는 번호(시퀀스 번호) 가 붙어 있어서,

순서 보장과 재전송에 사용돼요.
예: 한 문장을 여러 개의 봉투에 담아 보내고, 도착한 뒤 원래 문장으로 재조립하는 것

4. 신뢰성 (Reliability)
TCP는 데이터가 손실되거나 순서가 바뀌거나 중복돼도 다시 정리해서 정확하게 전달해줘요.
이를 위해 다음과 같은 기능을 제공해요:
재전송 (Timeout 또는 누락 확인 시)
ACK 응답 확인
오류 검출 (Checksum)
순서 재조립
즉, 데이터가 정확히 도착했는지를 항상 체크하고 보장해주는 프로토콜이에요.

5. 전이중 방식 (Full Duplex)
TCP는 양방향으로 동시에 통신할 수 있어요.
예: 전화처럼 나도 말하고 너도 동시에 말할 수 있음

반이중(Half Duplex)은 한 번에 한 방향만 가능 (예: 무전기)


TCP는 이 전이중 방식을 사용해 클라이언트와 서버가 동시에 데이터 송수신 가능합니다.

6. 스트림 전송 서비스 (Byte Stream)
TCP는 데이터를 연속된 바이트 스트림으로 처리해요.
메시지 단위로 보내는 것이 아니라, 흐르듯이 데이터를 전송함


구분이 없는 연속된 데이터 덩어리라서, 애플리케이션이 직접 메시지 경계를 구분해야 해요


예:
python
복사편집
conn.send(b'Hello')
conn.send(b'World')

수신자는 HelloWorld를 한 번에 받을 수도 있고, Hello 따로 World 따로 받을 수도 있어요.

7. 잘 알려진 포트 / 동적 포트
잘 알려진 포트 (Well-known Port)
0~1023번 포트
HTTP(80), HTTPS(443), FTP(21) 등 주요 프로토콜에 고정된 포트 번호
동적 포트 (Dynamic Port)
49152~65535

클라이언트가 연결할 때 자동으로 임시 할당

서버와 연결할 때는 이 포트로 요청 보내고 응답 받음

예:
서버는 80번 포트에서 대기

클라이언트는 54321번 포트를 열고 통신 시작

8. TCP 상태 천이 (TCP State Machine)
TCP 연결은 다음과 같은 상태(State) 를 거쳐 변화합니다:
주요 상태 흐름:
상태
설명
LISTEN
서버가 연결 요청 기다리는 중
SYN-SENT
클라이언트가 SYN 보낸 후 대기 중
SYN-RECEIVED
서버가 SYN 받고 SYN-ACK 보낸 상태
ESTABLISHED
연결 완료, 데이터 송수신 가능
FIN-WAIT-1 / 2
종료 요청 보낸 상태
CLOSE-WAIT
상대가 종료 요청, 내가 처리 준비 중
LAST-ACK
마지막 ACK 보내는 중
TIME-WAIT
마지막 ACK 보낸 후 대기 (재전송 대비)
CLOSED
연결 완전히 종료

TCP 상태 변화는 네트워크 연결의 생명주기(Lifecycle) 를 보여주는 개념이에요.

정리 요약표
개념
요약 설명
연결지향
통신 전에 연결을 먼저 맺음 (3-way handshake)
3/4방향 핸드쉐이크
연결 시작(3단계), 종료(4단계) 절차
세그먼트
데이터를 잘라 보내는 TCP 단위
신뢰성
재전송, 오류 검출, 순서 보장 등
전이중
양방향 동시 송수신 가능
스트림 전송
바이트 흐름 방식으로 데이터 전송
포트
서비스 구분 (HTTP 80, 동적 포트 49152+)
상태천이
연결 생성~종료까지의 TCP 상태 변화

문제 1. (TCP 연결 및 상태)
Q. TCP 연결 설정과 종료에 사용되는 핸드쉐이크 절차로 올바른 것은?
A. 3-Way Handshake: SYN → SYN-ACK → ACK, 4-Way Handshake: FIN → ACK → FIN → ACK
 B. 3-Way Handshake: ACK → SYN → FIN, 4-Way Handshake: SYN → ACK → FIN → ACK
 C. 3-Way Handshake: FIN → ACK → SYN, 4-Way Handshake: SYN → FIN → ACK → FIN
 D. 3-Way Handshake: SYN → ACK → FIN, 4-Way Handshake: ACK → FIN → SYN → ACK
정답: A

문제 2. (TCP 세그먼트와 전송 방식)
Q. 다음 중 TCP의 데이터 전송 특징으로 올바른 것은?
A. TCP는 데이터를 메시지 단위로 전송하며, 수신자가 경계를 자동으로 인식한다
 B. TCP는 데이터를 바이트 스트림으로 전송하며, 애플리케이션이 데이터 구분을 처리해야 한다
 C. TCP는 데이터 전송 시 전이중 방식을 지원하지 않는다
 D. TCP는 동적 포트 번호를 0~1023번 범위에서 할당한다
정답: B
