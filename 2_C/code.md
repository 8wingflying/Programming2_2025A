## code1.c
```c
#include <stdio.h>

int main(void) {
	float miles;

	printf("A88168 也可以改成中文Please enter miles:");
	scanf("%f", &miles);

	float kilometers = miles * 1.6;

	printf("%f Kilometers", kilometers);
}

```
## code2.c
```c
#include <stdio.h>
int main() {
    int intType;
    float floatType;
    double doubleType;
    char charType;

    // sizeof evaluates the size of a variable
    printf("Size of int: %zu bytes\n", sizeof(intType));
    printf("Size of float: %zu bytes\n", sizeof(floatType));
    printf("Size of double: %zu bytes\n", sizeof(doubleType));
    printf("Size of char: %zu byte\n", sizeof(charType));
    
    return 0;
}

```

## code2B.c
```c
#include <stdio.h>

int main(void) {
    printf("ASCII 編碼與解碼 初初階\n");
    printf("顯示字元 %c\n", 'A');
    printf("顯示為十進位整數 %d\n", 'A');
    printf("顯示為八進位整數 %o\n", 'A');
    printf("顯示為十六進位整數 %X\n", 'A');
    printf("顯示為十六進位整數 %x\n", 'A');
    
    return 0;
}
```
## code3.c 格式化輸入與輸出 | 算術運算子（Arithmetic Operators）
```
#include <stdio.h>
#include <math.h> 

int main()
{
   float a = 1.0, b = 6.0, c=4.0;
   printf ("%.4f", sqrt(a+b*c));
   return 0;
}
```
- sqrt()函數是定義在<math.h> ==> 所以必須要#include <math.h>
- 更多數學運算範例請參看
  - https://blog.hubspot.com/website/math-functions-c
  - https://www.w3schools.com/c/c_math.php
## code4.c bitwise運算子（Logical Operators）
```c
#include <stdio.h>
int main(int argc, char **argv)
{
    int x=9;
    int y=5;
    int result=(x^y);
    int result2=(x&&y);
    int result3=(x&y);
    printf("this is the smallest number %d \n", result);
    return 0;
}
```
```c
#include <stdio.h>
int main(int argc, char **argv)
{
    int x=9;
    int y=5;
    int result=y^((x^y)&-(x<y));
    printf("this is the smallest number %d \n", result);
    return 0;
}
```

## code5.c 遞增和遞減運算字（Increment and Decrement Operators）
```c
#include <stdio.h>
int main()
{
   int a = 11111;
   printf("%d", a);
   a++;
   printf("%d", a);
   return 0;
}
```
```c
#include <stdio.h>
int main()
{
   int a = 11111, b = 22222;
   printf("%d", (a++)+(++b));
   return 0;
}
```
```c
#include <stdio.h>
int main()
{
   int a = 11111, b = 22222;
   printf("%d", (a++)+(a+(++b)));
   return 0;
}
```
# 選擇性敘述 ==> 各類型 if switch
## code6.c  if
```
#include<stdio.h>
 
int main()
{
    int num;
 
    printf("請輸入一個正整數 : ");
    scanf("%d",&num);
 
    if (num%2==0)
      printf("你輸入的偶數");
}
```
## code7.c  if ..else ..
```
#include<stdio.h>
 
int main()
{
    int num;
 
    printf("請輸入一個正整數 : ");
    scanf("%d",&num);
 
    if (num%2==0)
      printf("你輸入的偶數\n");
    else
      printf("你輸入的奇數\n");
}
```

## code8.c  `? :` 運算子(三元運算子)
```c
#include<stdio.h>
 
int main()
{
    int num;
 
    printf("請輸入一個正整數 : ");
    scanf("%d",&num);
 
    (num%2==0)?printf("偶數"):printf("奇數");
}
```
## code9.c  if-else流程控制
```
試寫一個C程式，能判定輸入年份是否為閏年(leap year) 。
閏年判定方式：是4的倍數，但不是100的倍數：或者是400的倍數
　　例如：1800閏年，2000是閏年，2001不是閏年
```
```c
#include <stdio.h>
int main()
{
   int year;
   printf("判斷是否為閏年的C程式:請輸入你要的......年份"); 
   scanf("%d",&year);	

   if(((year%4==0)&&(year%100!=0))||(year%400==0))
       printf("%d 年是閏年.",year);
   else
       printf("%d 年不是閏年r",year);    

   return 0;
 }
```
## code10.c  switch流程控制
```
#include <stdio.h>

int main()
{
   int x = 3;
   switch (x+1) {
     case 3:
       printf ("3  ");
     case 4:
       printf ("4  ");
     case 5:
       printf ("5  ");
       break;
     case 6:
       printf ("6  ");
     default:
       printf ("x");
     }
   return 0;
}
```
# 迴圈設計 
## code11.c
```
迴圈設計
題目:在console端輸入n == > 輸出:1+2+3+….+n的結果
使用三種loop技術撰寫
```
```c
//FOR LOOP

#include <stdio.h>
int main() {
    int n, i, sum = 0;

    printf("Enter a positive integer: ");
    scanf("%d", &n);

    for (i = 1; i <= n; ++i) {
        sum += i;  // sum = sum +i
    }

    printf("Sum = %d", sum);
    return 0;
}

```

```c
//while loop

#include <stdio.h>
int main() {
    int n, i, sum = 0;

    printf("Enter a positive integer: ");
    scanf("%d", &n);

    i = 1;
    while (i <= n) {
       sum += i;
       ++i;
    }


    printf("Sum = %d", sum);
    return 0;
}

```
```c

//DO While LOOP

#include <stdio.h>
int main() {
    int n, i, sum = 0;

    printf("Enter a positive integer: ");
    scanf("%d", &n);

    i = 1;
    do{
      sum += i;
      ++i;
    } while (i <= n);

    printf("Sum = %d", sum);
    return 0;
}
```
- 補充作業:在console端輸入n == > 輸出:n!=1*2*3*….*n的結果
  - 使用三種loop技術撰寫
  - 3!=3*2*1 =6

## code12.c
```

```


## code13.c
```

```
## code14.c
```

```
## code15.c
```

```
## code16.c
```

```
## code17.c
```

```

## code18.c
```

```
## code19.c
```

```
## code20.c
```

```

## code21.c
```

```

## code22.c
```

```


## code23.c
```

```
## code24.c
```

```
## code25.c
```

```
## code26.c
```

```
## code27.c
```

```

## code28.c
```

```
## code29.c
```

```
## code30.c
```

```

## code31.c
```

```

## code32.c
```

```


## code33.c
```

```
## code34.c
```

```
## code35.c
```

```
## code36.c
```

```
## code37.c
```

```

## code38.c
```

```
## code39.c
```

```
## code40.c
```

```
## code41.c
```

```

## code42.c
```

```


## code43.c
```

```
## code44.c
```

```
## code45.c
```

```
## code46.c
```

```
## code47.c
```

```

## code48.c
```

```
## code49.c
```

```
## code50.c
```

```

