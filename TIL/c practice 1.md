# 여기는 예문적고 연습하는 곳
```
#inlcude <stdio.h>
int main(){
	int a=1234;
	float b=1.235;
	printf("%d\n",a);
	}
```
```
#include<stdio.h>
int main(){
	putchar('H');
	putchar('i');
}
```
```
#include<stdio.h>
int main(){
	puts("Happy");
}
```
```
#include<stdio.h>
int main(){
	int x,y;
	scanf_s("%d",&x);
	scanf_s("%d",&y);
	printf("%d+%d=%d\n",x,y,x+y);
}
```
```
#include <stdio.h>
int main(void){
	char ch;
	printf("1개의 영문자 입력하시오:");
	ch=getchar();
	printf(Typed: "%c\n",ch);
}
```
```
#include<stdio.h>
int main(){
	char ch[20];
	printf("당신의 이름을 영문으로 쓰시오:");
	gets(ch);
	printf("ch=%s\n",ch);
	return 0;
}
```
```
#include<stdio.h>
	int main(){
	int x,y,z;
	x = 2;
	y = x;
	z = 5 - x;
	printf("%%d\n %d\n %d\n",x,y,z);
	}
```
p.101