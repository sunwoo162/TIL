# HTML
### HTML 기본구조
```
<!DOCTYPE html>
<html lang="ko">
	<head>
		<meta charset="UTF-8">
		<meta name="viewport" content="width=device-width, initial-scale=1.0">
		<title>웹페이지 문서 제목입니다</title>
		<style>
      h1 {
        background-color: #f0f0f0;
      }
			p {
				color: green;
			}
			img {
				max-width: 100%;
			}
		</style>
		<link rel="stylesheet" href="styles.css">
		<script src="script.js"></script>
	</head>
	<body>
		<h1>본문 제목</h1>
		<p>본문의 첫 번째 단락입니다.</p>
		<p>본문의 두 번째 단락입니다.</p>
		<img src="/_assets/images/example.jpg" alt="예시 이미지">
		<a href="https://uxkm.io/" target="_blank">UXKM 바로가기</a>
	</body>
</html> 
```
### 각 기능 설명

#### HTML5 Doctype 선언
문자 형식 선언은 HTML 문서가 어떤 버전의 HTML 이나 XHTML 로 작성되었는지 웹 브라우저에게 알려줌
```
<!DOCTYPE html>
```
#### 루트 요소
최상위 요소이며, 모든 다른 HTML 요소들을 포함하는 부모 요소이다.
```
<!DOCTYPE html>
<html lang="ko">
  <!-- HTML 문서의 내용 -->
</html>
```
#### 헤드
HTML 문서의 메타데이터와 외부 리소스에 대한 정보를 포함하는 부분
<head>요소는 화면에 직접적으로 보이지 않지만, 웹 브라우저가 문서를 처리하고 표시하는데 중요한 역할을 함
- 문서 제목
제목 표시줄이나 북마크 목록에서 표시된다.
```
<head>
  <title>문서 제목</title>
</head>
```
- 메타데이터
주로 검색 엔진 최적화, 문자 인코딩, 뷰포트 설정등을 지정함
```
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta name="description" content="문서에 대한 간단한 설명">
  <meta name="keywords" content="키워드1, 키워드2, 키워드3">
  <meta name="author" content="작성자 이름">
</head>
```
- 스타일시트 및 외부 리소스
외부 리소스를 문서에 연결한다.
```

<head>
  <style>
    h1 {
      background-color: #f0f0f0;
    }
    p {
      color: green;
    }
  </style>
  <link rel="stylesheet" href="styles.css">
  <script src="script.js"></script>
</head>
```
#### 본문
- 텍스트
제목, 단락, 목록 등의 텍스트 요소를 사용하여 웹 페이지의 구조를 정의 함
```
<body>
  <h1>본문 제목</h1>
  <p>본문의 첫 번째 단락입니다.</p>
  <p>본문의 두 번째 단락입니다.</p>
</body>
```
- 이미지
이미지 파일 따로 만들어서 불러와야함 그래야 삽입됨
```
<body>
  <img src="/_assets/images/example.jpg" alt="예시 이미지">
</body>
```
- 링크
하이퍼 링크
```
<body>
  <a href="https://uxkm.io/" target="_blank">UXKM 바로가기</a>
</body>
```
