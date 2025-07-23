# HTML
### HTML �⺻����
```
<!DOCTYPE html>
<html lang="ko">
	<head>
		<meta charset="UTF-8">
		<meta name="viewport" content="width=device-width, initial-scale=1.0">
		<title>�������� ���� �����Դϴ�</title>
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
		<h1>���� ����</h1>
		<p>������ ù ��° �ܶ��Դϴ�.</p>
		<p>������ �� ��° �ܶ��Դϴ�.</p>
		<img src="/_assets/images/example.jpg" alt="���� �̹���">
		<a href="https://uxkm.io/" target="_blank">UXKM �ٷΰ���</a>
	</body>
</html> 
```
### �� ��� ����

#### HTML5 Doctype ����
���� ���� ������ HTML ������ � ������ HTML �̳� XHTML �� �ۼ��Ǿ����� �� ���������� �˷���
```
<!DOCTYPE html>
```
#### ��Ʈ ���
�ֻ��� ����̸�, ��� �ٸ� HTML ��ҵ��� �����ϴ� �θ� ����̴�.
```
<!DOCTYPE html>
<html lang="ko">
  <!-- HTML ������ ���� -->
</html>
```
#### ���
HTML ������ ��Ÿ�����Ϳ� �ܺ� ���ҽ��� ���� ������ �����ϴ� �κ�
<head>��Ҵ� ȭ�鿡 ���������� ������ ������, �� �������� ������ ó���ϰ� ǥ���ϴµ� �߿��� ������ ��
	
- ���� ����
���� ǥ�����̳� �ϸ�ũ ��Ͽ��� ǥ�õȴ�.
```
<head>
  <title>���� ����</title>
</head>
```
	
- ��Ÿ������
�ַ� �˻� ���� ����ȭ, ���� ���ڵ�, ����Ʈ �������� ������
```
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta name="description" content="������ ���� ������ ����">
  <meta name="keywords" content="Ű����1, Ű����2, Ű����3">
  <meta name="author" content="�ۼ��� �̸�">
</head>
```
- ��Ÿ�Ͻ�Ʈ �� �ܺ� ���ҽ�
�ܺ� ���ҽ��� ������ �����Ѵ�.
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
#### ����
- �ؽ�Ʈ
����, �ܶ�, ��� ���� �ؽ�Ʈ ��Ҹ� ����Ͽ� �� �������� ������ ���� ��
```
<body>
  <h1>���� ����</h1>
  <p>������ ù ��° �ܶ��Դϴ�.</p>
  <p>������ �� ��° �ܶ��Դϴ�.</p>
</body>
```
- �̹���
�̹��� ���� ���� ���� �ҷ��;��� �׷��� ���Ե�
```
<body>
  <img src="/_assets/images/example.jpg" alt="���� �̹���">
</body>
```
- ��ũ
������ ��ũ
```
<body>
  <a href="https://uxkm.io/" target="_blank">UXKM �ٷΰ���</a>
</body>
```
