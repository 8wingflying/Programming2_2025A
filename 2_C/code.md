# 小小測驗
- [程式閱讀題](程式閱讀題.md)
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

## code12.c  多重迴圈範例: 99乘法表
```
#include <stdio.h>
int main() {
    int i,j;   
    for(i=1;i<=9;i++) {
        for(j=1;j<=9;j++)
            printf("%d*%d=%2d\t", i, j, i*j);
        printf("\n");
    }
    return 0;
}
```

# 函數(function)
## code13.c
```
//main()在後 其他函數在前

#include <stdio.h>
 
int ifactorial(int z)
{
	int mul = 1, i = 1;
	while(i <= z)
	{
		mul *= i;
		i++;
	};
	return mul;
}

int  main()
{
    int i = 4;
    printf("%d 的階乘為%d\n", i, ifactorial(i));
    return 0;
}
```

```c
//main()在前 其他函數在後
//要先宣告 ==> int fun(int);

#include <stdio.h>
#include <stdlib.h>

int a=10, fun(int);

int main(void) {

  int b=6;
  printf("a=%d, b=%d, fun(a)=%d\n", a, b, fun(a));
  return 0;
}

int fun(int b) {
  a -=5; b /=2;
  return(a+b);
}
```
## code14.c 函數呼叫
- 函數呼叫:call by value(傳值呼叫) vs call by address(傳址呼叫)| 兩個數字互換的C程式
```c
#include <stdio.h>
/* 函數的宣告 */
void swap (int a, int b);

int main (void) {
  int i = 11, j = 22;
  printf ("i = %d, j = %d\n" , i, j);
  swap (i, j);
  printf ("i = %d, j = %d\n" , i, j);
  return 0;
}

void swap (int a, int b) {
  printf ("互換前:a = %d, b = %d\n" , a, b);
  int temp = a;
  a = b;
  b = temp;
  printf ("互換後:a = %d, b = %d\n" , a, b);
}
```
## code15.c  遞迴函數1
```
遞迴函數(Recursive Function)程式設計:
Recursive function遞迴函數
[1]一個問題的內涵是由本身所定義的話，稱之為遞迴。
[2]遞迴函數是由上而下分析方法的一種特殊的情況，因為子問題本身和原來問題擁有相同的特性，只是範圍改變，範圍逐漸縮小到一個終止條件。
[3]遞迴函數的特性：
a.遞迴函數在每次呼叫時，都可以使問題範圍逐漸縮小。
b.函數需要擁有一個終止條件，以便結束遞迴函數的執行，否則遞迴函數並不會結束，而是持續的呼叫自已。
```
```
常見的遞迴函數:
1.N! 計算 N!階層函數: 4!=4*3*2*1=24  ==> f(n) = n*f(n-1);
2.f(n)=1+2+3+....+n ==>  級數和:1加到n的值  ==> f(n) = n + f(n-1);
3.費式序列Fibonacci Serie
4.二項式係數(Binomial coeff)
5.m與n的最大公因數(GCD).
6.河內塔（Tower of Hanoi）
```
```
小測驗:用遞迴求算1*2+2*3+3*4+…+(n-1)*n之和
```
```
遞迴式:f(n) = n*(n-1)(n-2)......1 = n*f(n-1)
   f(3)=3*f(2)=3*[2*f(1)]=3*[2*{1}]
終止式:f(1)=1
```
```c
#include <stdio.h>
 
double factorial(unsigned int i)
{
   if(i <= 1)
      return 1;
   else   return i * factorial(i - 1);
}

int  main()
{
    int i = 15;
    printf("%d 的階乘為%f\n", i, factorial(i));
    return 0;
}
```
## code16.c  遞迴函數2:費式序列Fibonacci Serie
```
費式序列Fibonacci Series: 0 1 1 2 3 5 8 13 21 34
f(0)=0, f(1)=1, f(n)=f(n-1)+f(n-2)
底下是用迴圈方式計算費式序列Fibonacci Serie
作業:使用遞迴函數方式計算費式序列Fibonacci Serie
```
```c
#include<stdio.h>    
void printFibonacci(int n){    
  static int n1=0,n2=1,n3;    

  if(n>0){    
    n3 = n1 + n2;    
    n1 = n2;    
    n2 = n3;    
    printf("%d ",n3);    
    printFibonacci(n-1);    
    }    
 }    

int main(){    
   int n;
  
   printf("請輸入你要列印幾項費式序列(要整數): ");    
   scanf("%d",&n);    
   printf("費式序列Fibonacci Series: ");    
   printf("%d %d ",0,1);//註解1:先列印前兩個費式序列   
   printFibonacci(n-2);//註解2:在印出其他費式序列   
   return 0;  
 }    
```


## code17.c  變數類型與scope(管轄範圍)
```c
#include <stdio.h>
 
/* 全域(global)變數宣告 */
int g = 20;

void printg()
{
  printf ("value of g in printg= %d\n",  g);
}

void printg2()
{
  /* 區域(local)變數宣告 */
  int g = 99;
  printf ("value of g in printg2= %d\n",  g);
}

int main ()
{
  /* 區域變數宣告 */
  int g = 10;

  printg();
  printf ("value of g in main= %d\n",  g);
 
  return 0;
}
```

## code18.c 陣列
```
陣列的存取方式:
1.使用索引(index) 存取陣列資料
2.使用指標(pointer)存取陣列資料
```
```c
#include <stdio.h>
 
int main ()
{
   int n[10]; /* n 是一個包含 10 個整數的陣列 */
   int i,j;
 
   /* 初始化陣列元素 */         
   for ( i = 0; i < 10; i++ )
   {
      n[ i ] = i + 100; /* 設置元素 i 為 i + 100 */
   }
   
   /* 輸出陣列中每個元素的值 */
   for (j = 0; j < 10; j++ )
   {
      printf("Element[%d] = %d\n", j, n[j] );
   }
 
   return 0;
}
```
## code19.c  字串(==字元陣列)與字串處理(不使用指標)
```c
#include <stdio.h>
#include <string.h>
 
int main ()
{
   char str1[9] = "CTFer";
   char str2[9] = "hacker";
   char str3[9];
   char str4[9];
   int  len ;
 
   /* 複製 str1 的內容複製到 str3 */
   strcpy(str3, str1);
   printf("strcpy( str3, str1) :  %s\n", str3 );
 
   /* 連接 str1 和 str2後的結果 存到str1 */
   strcat( str1, str2);
   printf("strcat( str1, str2):   %s\n", str1 );
 
    /* 連接 str2 和 str1後的結果 存到str1   */
   strcat( str2, str1);
   printf("strcat( str2, str1):   %s\n", str2 );
   
   /* 連接後，str1 的總長度 */
   len = strlen(str1);
   printf("strlen(str1) :  %d\n", len );
 
   strcpy(str4, str1);
   printf("strcpy( str4, str1) :  %s\n", str3 );
   str4[3] = '\0';
   printf(str4);
   
   return 0;
}
```
```
ttps://www.onlinegdb.com/online_c_compiler 

執行結果
main.c:38:11: warning: format not a string literal and no format arguments [-Wformat-security]    
    printf(str4 );                                                                                
           ^~~~                                                                                   
strcpy( str3, str1) :  CTFer                                                                      
strcat( str1, str2):   CTFerhacker                                                                
strcat( str2, str1):   erCTFerhacker                                                              
strlen(str1) :  22                                                                                
strcpy( str4, str1) :  cker                                                                       
*** stack smashing detected ***: ./a.out terminated                                               
CTFAborted (core dumped)    
```

```c
//修正後的程式
#include <stdio.h>
#include <string.h>
 
int main ()
{
   char str1[9] = "CTFer";
   char str2[9] = "hacker";
   char str3[9];
   char str4[9];
   int  len ;
 
   /* 複製 str1 的內容複製到 str3 與str 4 */
   strcpy(str4, str1);
   strcpy(str3, str1);
   printf("strcpy( str3, str1) :  %s\n", str3 );
 
   /* 連接 str1 和 str2後的結果 存到str1 */
   strcat( str1, str2);
   printf("strcat( str1, str2):   %s\n", str1 );
 
    /* 連接 str2 和 str1後的結果 存到str1   */
   //strcat( str2, str1);
   //printf("strcat( str2, str1):   %s\n", str2 );
   
   /* 連接後，str1 的總長度 */
   len = strlen(str1);
   printf("strlen(str1) :  %d\n", len );
 
   printf("strcpy( str4, str1) :  %s\n", str4 );
   str4[3] = '\0';
   printf("處理過的字串變成(請說明why?) :  %s\n",str4);
   
   return 0;
}
```
# 指標(pointer)
## code20.c
```
#include <stdio.h>

int main(void) {
    int x= 38;
    int *p=&x;
    
    printf("%p \n" , &x);
    printf("%d \n" , x);
    printf("%d \n" , *&x);
    printf("%d \n" , *p);
    printf("%p \n" , p);
    printf("%p \n" , p+3);

    return 0;
}

```
## 陣列
## code21.c
```

```
## 陣列存取技術:使用索引(index)存取陣列
## code22.c
```c
#include <stdio.h>

int main(void) {
    int a[10] = {3,2,3,4,5,4,7,1,3,2};
    int b[10] = {0,0,0,0,0,0,0,0,0,0};

    for (i = 0 ; i < 10 ; i=i+1)
        b[a[i]-1] = b[a[i]-1] + 1;
   
    printf ("%d" , b[2] ) ;
    return 0;
}
```
## 陣列存取技術:使用指標(pointer)存取陣列
```c
#include <stdio.h>
#include <stdlib.h>
#define SIZE 10

void fun(int *, int);

int main(void) {
  int x[SIZE] = {1,2,3,4,5,6,7,8,9,10};
  fun(x, SIZE);
  printf("\n");
  return 0;
}

void fun(int *a, int size) {
  if (size > 0) {
   fun(a+3, size-3);
   printf("*(a+%d)=%d\n", SIZE-size, *a);
  }
}

```
```c
#include <stdio.h>
int main()
{
  int arr[]= {203, 151 , 164, 154, 194};
  int *p = arr;
  
  *p++ += 10;
  *(p++) += 11;
  *(++p) += 9;
  
  for (int i= 0; i < 5; i++)
     printf("%d ", arr[i]);
  return 0;
}             
```
```c
#include <stdio.h>
int main()
{
  int A[5] = {1, 2, 3, 4, 5};
  int* p = A + 3;
  printf("%d \n", p[1]);
}

```
```
#include <stdio.h>
int main()
{
  int array[5] = {100, 215, 321, 254, 165}; 
  int *k = &array[1]; 

  *k-- += 5; 
  *(++k) += 9; 
  *(k++) += 7; 
  *k++ -= 15; 

  for(int i = 0; i < 5; i++) 
  printf("%d ", array[i]); 
  return 0;
}
```
# 字串(string) == 特殊型的字元陣列

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

