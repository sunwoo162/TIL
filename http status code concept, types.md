# http �����ڵ� ����, ����
## http �����ڵ��?
```
Ư�� HTTP��û�� ���������� �Ϸ�Ǿ����� �˷��ִ� �ڵ��̴�.
```
## ���� ���Ǵ� �ڵ�
#### 1XX : Informational(��������) 
```
�ֱٿ��� �� ������ �ʴ´�
```
#### 2XX : Success(����) 
```
: 200 : OK(��û�� ���������� ����Ǿ���),(����)
: 201 : Created (PUT �޼ҵ忡 ���� ������ ������ ���� ������),(������)
: 202 : Accepted(�� ������ ��� ������),(����)
: 204 : No content,(PUT,POST,DELETE ��û�� ��� ������ ������ ������ �����Ͱ� ���� ���),(������ ����)
```
#### 3XX : Redirection(�����̷���)(��û�� �Ϸ��Ϸ��� �߰��ൿ �ʿ�)
```
: 301 : Moved permanently (�䱸�� �����͸� ����� Ÿ URL�� ��û��/Redirect�� ���),(���� �̵�)
: 302 : Found (�����̷�Ʈ ��û �޼ҵ尡 GET���� ���ϰ� ������ ���ŵ� �� ����)
: 307 : Temporary Redirect (Ŭ���̾�Ʈ�� ��û�� ���ҽ��� �ٸ� URI�� ������ ���� ��û�� ������ �޼ҵ带 ����ؼ� ��û�ؾ� �� �� ������ Ŭ���̾�Ʈ�� �Cû�� ���� ����)
: 308 : Permanent Redirect (�䱸�� �����͸� ����� Ÿ URL�� ��û�ϰ� ��û ����� �״�� ������)
```
#### 4XX : Client Error(Ŭ���̾�Ʈ ����) 
```
: 400 : Bad Request (������� �߸��� ��û�� ó���� �� ����),(�߸��� ��û)
: 401 : Unauthorized (������ �ʿ��� �������� ��û�� ���),(���� ����)
: 403 : Forbidden (���� ����, �����͸� ������ ��û �� ������ ������ ���� ���� ����),(������)
: 404 : Not found, (��û�� ������ ����),(ã�� �� ����)
```
#### 5XX : Server Error(���� ����)
```
: 500 : internal server error (���� ���� ����)
: 503 : Service unnailable (���� ���� �Ұ�)(��û ó�� �غ�X)
```
## ��ü �ڵ�
#### 1XX : Informational(��������) 
```
�������� : 100 : Continue (Ŭ���̾�Ʈ�� ���� �Ϻ� ��û�� �޾����� ������ ������ ��� ��û��),(���)
�ӽ����� : 101 : Switching protocols(�������� ��ȯ)
         : 102 : Processing (ó����)
```
#### 2XX : Success(����) 
```
���� : 200 : OK(��û�� ���������� ����Ǿ���),(����)
     : 201 : Created (PUT �޼ҵ忡 ���� ������ ������ ���� ������),(������)
     : 202 : Accepted(�� ������ ��� ������),(����)
     : 203 : Non-authoritative information (������ Ŭ���̾�Ʈ �䱸 �� �Ϻθ� ����),(�ŷ��� �� ���� ����)
     : 204 : No content,(PUT,POST,DELETE ��û�� ��� ������ ������ ������ �����Ͱ� ���� ���),(������ ����)
     : 205 : Reset Content (������ �缳��)
     : 206 : Partial Content (�Ϻ� ������)
     : 207 : Multi-Status (���� ����)
```
#### 3XX : Redirection(�����̷���)(��û�� �Ϸ��Ϸ��� �߰��ൿ �ʿ�)
```
     : 300 : Multiple Choices (���� ���� �׸�)
     : 301 : Moved permanently (�䱸�� �����͸� ����� Ÿ URL�� ��û��/Redirect�� ���),(���� �̵�)
     : 302 : Not temporarliy (�䱸�� �����͸� ����� Ÿ URL�� ��û��/Redirect�� ���),(�ٸ� ��ġ ã��)
     : 303 : See Other (�ٸ� ��ġ ����)
     : 304 : No content, (PUT,POST,DELETE ��û�� ��� ������ ������ ������ �����Ͱ� ���� ���),(�������� ����)
     : 305 : Use Proxy (���Ͻ� ���)
     : 306 : Unused (���� �������� ����ϴٰ� ����� ������� �ʴ� ���� �ڵ�)
     : 307 : Temporary Redirect (�ӽ� �����̷���)
     : 308 : Permanent Redirect (�䱸�� �����͸� ����� Ÿ URL�� ��û�ϰ� ��û ����� �״�� ������)
   ```
#### 4XX : Client Error(Ŭ���̾�Ʈ ����) 
```
     : 400 : Bad Request (������� �߸��� ��û�� ó���� �� ����),(�߸��� ��û)
     : 401 : Unauthorized (������ �ʿ��� �������� ��û�� ���),(���� ����)
     : 402 : Payment required(�����),(���� �ʿ�)
     : 403 : Forbidden (���� ����, �����͸� ������ ��û �� ������ ������ ���� ���� ����),(������)
     : 404 : Not found, (��û�� ������ ����),(ã�� �� ����)
     : 405 : Method not allowed (������ �ʴ� http method �����),(������ ���� �޼ҵ�)
     : 406 : Not Acceptable (������ �� ����)
     : 407 : Proxy authentication required (������ ���� �䱸��),(���Ͻ� ���� �ʿ�)
     : 408 : Request timeout (��û �ð� �ʰ�)
     : 409 : Conflict (�浹)
     : 410 : Gone (���������� ��� ����),(�����)
     : 411 : Length Required (���� �ʿ�)
     : 412 : Precondition gailed (��ü ���� ����),(���� ���� ����)
     : 413 : Request Entity Too Large (��û ��ü�� �ʹ� ŭ)
     : 414 : Request-URI too long (��û URL ���̰� �� �����)
     : 415 : Unsupported Media Type (�������� �ʴ� �̵�� ����)
     : 416 : Range Not Satisfiable (ó���� �� ���� ��û ����)
     : 417 : Expectation Failed (���� ����)
     : 422 : Unprocessable Entity (ó���� �� ���� ��ƼƼ)
     : 423 : Locked (���)
     : 424 : Failed Dependency (���� ����� ����)
     : 426 : Upgraded Required (���׷��̵� �ʿ���)
     : 428 : Precondition Required (���� ���� �ʿ���)
     : 429 : Too Many Requests (�ʹ� ���� ��û)
     : 431 : Reauest Header Fields Too Large (�ʹ� ū ���)
     : 444 : Connection Closed Without Response (���� ���� ���� ����)
     : 452 : Unavailable For Legal Reasons (���� ������ �Ұ�)
   ```
#### 5XX : Server Error(���� ����)
```
     : 500 : internal server error (���� ���� ����)
     : 501 : Not implemented (�� ������ ó���� �� ����),(�������� ����)
     : 502 : Bad Gateway (�ҷ� ����Ʈ����)
     : 503 : Service unnailable (���� ���� �Ұ�)(��û ó�� �غ�X)
     : 504 : Gateway timeout (����Ʈ���� �ð� �ʰ�)
     : 505 : HTTP wersion not supported (�ش� http ���� �������� ����)
     : 507 : Insufficient Storage (�뷮 ����)
   ```