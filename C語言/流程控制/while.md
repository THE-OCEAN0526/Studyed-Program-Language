# while 述句
- while (表示式) {程式片段}
- 當「表示式」成立時，就執行「程式片段」。
- 
### 連續顯示1~10

```
#include <stdio.h>
int main() {
  int count = 0;
  while(count < 10) {
    count = count + 1;
    printf("%d\n", count);
  }
  return 0;
}
```

### 猜數字練習

```
#include <stdio.h>

int main(){

	int guess;
	int answer = 4;
	int count = 0;
	while(count = 0 || guess!=answer){
		printf("1~10之間猜一個數字: ");
		scanf("%d", &guess);
		count = count + 1 ;
		if (guess < answer){
			printf("太小了\n");
		}else if(guess > answer){
			printf("太大了\n");
		}
	}
		printf("恭喜答對了!! (%d)", count);
	return 0;
}
```

### 求不定整數之總和暨平均

```
#include <stdio.h>
int main(){

	int number;
	int sum = 0;
	int count = 0;
	float average;
	printf("please input the number: \n");
	scanf("%d",&number);
	while(number != 0){
		scanf("%d",&number);
		sum = sum + number;
		count = count + 1;
	}
	printf("the sum is: %d\n",sum);
	average = (float) sum / count;
	printf("the average is: %f\n",average);
	
	return 0;
}

```

# do-while 述句
- do {程式片段} while (表示式);
- 當「表示式」成立時，就執行「程式片段」。
- 至少做一次的重複執行

### 連續顯示1~10

```
#include <stdio.h>
int main() {
  int count = 0;
  do {
  	count = count + 1;
   	printf("%d\n", count);
  } while (count < 10);
  return 0;
}
```

### 猜數字練習

```
#include <stdio.h>

int main(){

int guess;
int answer = 4;
int count = 0;
do {
	printf("1~10之間猜一個數字: ");
	scanf("%d", &guess);
	count = count + 1 ;
	if (guess < answer){
		printf("太小了\n");
	}else if(guess > answer){
		printf("太大了\n");
	}
} while (count = 0 || guess != answer);
	printf("恭喜答對了!! (%d)", count);
	return 0;
}

```
