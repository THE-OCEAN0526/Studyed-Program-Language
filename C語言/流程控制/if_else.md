# 流程控制
- 無條件地執行一次(一般敘述)
- 有條件地執行一次(if敘述)
- 無條件地重複執行(無窮迴圈)
- 有條件地重複執行(while敘述)
- 計次行重複執行(for敘述)
- 選擇性的執行一次(switch敘述)
- 至少執行一次有條件的重複執行(do-while敘述)
### if(表示式) {程式片段}
- 如果「表示式」成立，就執行「程式片段」
- 下面是猜數字的小程式^^
```
int main() {
  int answer = 4;
  int guess;
  printf("輸入你要猜的數字: ");
  scanf("%d", &guess);
  if (guess < answer) {
    printf("To larger!\n");
  }
  if (guess < answer) {
    printf("To smaller!\n");
  }
  if (guess == answer) {
    printf("Correct!\n");
  }
  reture 0;
}

```
- 某吃到飽餐廳的套餐1人300元(無額外的費用)。今日
因周年慶特價方案，每桌消費滿3000原就打八折。試寫
一程式讓服務生輸入一桌消費人數後，輸出該桌顧客應負的總額。
```
#include <stdio.h>
#include <stdlib.h>

int main(){

	int customers ,totle;
	int table;
	
	printf("輸入一桌客人總數: ");
	scanf("%d" ,&customers);
	
	table = 300 * customers;
	if (table < 3000) {
		totle = table;
	} else{
		totle = 300 * customers * 0.8;
	}
	
	printf("totle : %d\n" ,totle);

	system("pause");
	return 0;
}

```
- 輸入某三角形的三邊長(皆為整數)，判斷這三角形是什麼三角形?
1. 直角三角形(Right Triangle)：其中有兩個邊的平方和等於第三邊的平方。
2. 鈍角三角形(Obtuse Triangle)：其中有兩個邊的平方和小於第三邊的平方。
3. 銳角三角形(Acute Triangle)：任兩邊的平方和大於第三邊的平方。
```
#include <stdio.h>

int main(){
	int a, b, c;
	// while loop 讓使用者依序輸入三個整數，直到不是整數跳出迴圈!!
	while(scanf("%d", &a)==1){  
		scanf("%d%d",&b ,&c);
		// 判斷三邊是否成為三角形
		if (a + b >c && a + c > b && b + c > a) {
			// 判斷直角三角形
			if (a*a + b*b == c*c || a*a + c*c == b*b || b*b + c*c == a*a) {
				printf("Right Triangle\n");
				// 判斷銳角三角形
			}else if(a*a + b*b <= c*c || a*a + c*c <= b*b || b*b + c*c <= a*a){
				printf("Obtuse Triangle\n");
				// 判斷頓角三角形
			}else if(a*a + b*b >= c*c || a*a + c*c >= b*b || b*b + c*c >= a*a){
				printf("Acute Triangle\n");
			}
		}else{ // 都不是，那就不是三角形
				printf("Not Triangle\n");
			}
		
	}
	return 0;
}

```

- 對三個變數求最大值
```
#include<stdio.h>
int main(){
	int a,b,c,max; // max是最大值
	scanf("%d%d%d",&a,&b,&c);
	max = a; // 設max為最大值
	if(max < b){ // 比較如果max比b小，就換b為max
		max = b;
	}else if(max < c){ // 再次比較
		max = c;
	}
	printf("最大值為: %d",max);
	return 0;
}
```
- 求最小值
- 跟最大值一樣的邏輯
```
#include<stdio.h>
int main(){
	int a,b,c,min;
	scanf("%d%d%d",&a,&b,&c);
	min = a;
	if(min > b){
		min = b;
	}else if(min > c){
		min = c;
	}
	printf("最小值為: %d",min);
	return 0;
}
```
- 在三個整數中求中位數
1. 求三個整數中第二大的
2. 求三個整數中第二小的
```
#include <stdio.h>

int main(){
	int a,b,c,med;
	printf("輸入三個數: ");
	while(scanf("%d",&a)==1){
		scanf("%d%d", &b, &c);
		med = a;
		if(a<=b && b<=c || c<=b && b<=a){
			med = b;
		}else if(a<=c && c<=b || b<=c && c<=a){
			med = c;
		}
		printf("中位數: %d \n",med);
	}
	
}

```
- 對三個變數做大小排序
- 這裡用的是從小比到大，也可以用從大比到小的方式排序
```
#include <stdio.h>

int main(){
	// 由小排到大 a<=b<=c
	int a,b,c,change;
	while(scanf("%d",&a)==1){
		scanf("%d %d",&b,&c);
		// 如果a大於b做交換 
		if(a>b){
			change = a;
			a = b;
			b = change;
		
		}else if(b>c){
		// 確定a<=b，不確定c最大還是最c小 
		// 如果b大於c做交換 
			change = b;
			b = c;
			c = change;
		}else if(a>c){
		// 如果a大於c做交換 
			change = c;
			c = a;
			a = change;
		}
		printf("順序: %d %d %d\n",a,b,c);
	}
	return 0;
}
```
```
#include <stdio.h>

int main(){
	// 由小排到大 a<=b<=c
	int a,b,c,change;
	while(scanf("%d",&a)==1){
		scanf("%d %d",&b,&c);
		// 如果a大於b做交換 
		if(a>b){
			change = a;
			a = b;
			b = change;
		}
		if(a>c){
		// 如果a大於c做交換 
			change = a;
			a = c;
			c = change;
		}
		if(b>c){
		// 確定a<=b，不確定c最大還是c最小 
		// 如果b大於c做交換 
			change = b;
			b = c;
			c = change;
		}
	
		printf("順序: %d %d %d\n",a,b,c);
	}
	return 0;
}
```
