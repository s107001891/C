# 20181227 指標練習

```
使用下列三種方式存取陣列的元素
[1]使用index存取
[2]使用pointer(指標變數)存取:陣列名稱==>pointer(指標變數)
[3]使用pointer(指標變數)存取:利用一個pointer(指標變數)ptr指向陣列,再移動指標去存取元素(value)

計算一維陣列內所有元素的和 int a[5]={11,22,33,44,55};
取出最大元素
取出最小元素

將每一個陣列元素都加60
將每一個元素都依照位置(i)加上某一值(i+1)*5 ===>a[5]={11+5,22+10,33+15,44+20,55+25}
```
# 20181227 陣列練習

### 一維陣列的基本操作score[4]={99,11,23,44}:完成底下填充[prog9_1.c]
```
#include <stdio.h>
#include <stdlib.h>
int main(void)
{
   /* 宣告整數變數i當作index與整數陣列score */
   int i,score[4]; 	
   
   /* 設定陣列的內容  */   
   score[0]=___;		
   ___________; 	
   ___________;   	
   ___________; 		
   
   /* 使用一個for loop將陣列的內容一一印出  */
   for(i=0;i<=3;i++)
      printf("score[%d]=___\n",i,_______); 
   
   system("pause");
   return 0;
}
```
### 說明底下程式有哪些錯誤:一維陣列的基本操作[prog9_2]
```
#include <stdio.h>
#include <stdlib.h>
int main(void)
{
   int i,score[4]; 
   
   score[0]=118;		
   score[1]=552; 		
   score[3]=809; 		
   
   for(i=0;i<=5;i++)	
      printf("score[%d]=%d\n",i,score[i]);  
   
   system("pause");
   return 0;
}
```
###
```
```
###
```
/* prog9_3, 查詢陣列所佔的記憶空間 */ 
#include <stdio.h>
#include <stdlib.h>
int main(void)
{
   double data[4];	/* 宣告有4個元素的double型態陣列 */
   printf("陣列元素所佔的位元組:%d\n",sizeof(data[0]));
   printf("整個陣列所佔的位元組:%d\n",sizeof(data));
   printf("陣列元素的個數:%d\n",sizeof(data)/sizeof(double));
   
   system("pause");
   return 0;
}
```
###
```
/* prog9_4, 一維陣列內元素的設值 */
#include <stdio.h>
#include <stdlib.h>
int main(void)
{
   int i,age[3];
   for(i=0;i<3;i++)
   {
      printf("請輸入age[%d]的值:",i);
      scanf("%d",&age[i]);	  /* 由鍵盤輸入數值給陣列age裡的元素 */
   }
   for(i=0;i<3;i++)
      printf("age[%d]=%d\n",i,age[i]);

   system("pause");
   return 0;
}
```
###
```
/* prog9_5, 比較陣列元素值的大小 */
#include <stdio.h>
#include <stdlib.h>
int main(void)
{
   int A[5]={74,48,30,17,62};
   int i,min,max;
   min=max=A[0];		/* 將max與min均設為陣列的第一個元素 */
   
   for(i=0;i<5;i++)
   {
      if(A[i]>max) 	/* 判斷A[i]是否大於max */
         max=A[i];	
      if(A[i]<min) 	/* 判斷A[i]是否小於min */
         min=A[i];	
   }
   printf("陣列裡元素的最大值為%d\n",max);
   printf("陣列裡元素的最小值為%d\n",min);
   
   system("pause");
   return 0;
}


```
###
```
/* prog9_6, 輸入未定個數的資料到陣列裡 */
#include <stdio.h>
#include <stdlib.h>
#define MAX 10		/* 定義MAX為10 */
int main(void)
{
   int score[MAX];	/* 宣告有10個元素的整數陣列 */
   int i=0,num;
   int sum=0;		/* 宣告用來成績總和的變數sum */
	
   printf("請輸入成績，要結束請輸入0:\n");
   do 
   {
      printf("請輸入成績:");
      scanf("%d",&score[i]);
   }while(score[i++]>0);  		/* 輸入成績，輸入0時結束 */
   num=i-1;
   for(i=0;i<num;i++)
      sum+=score[i];				/* 計算平均成績 */
   printf("平均成績為 %.2f\n",(float)sum/num);
   system("pause");
   return 0;
}
```

###
```
/* prog9_7, 陣列的界限檢查 */
#include <stdio.h>
#include <stdlib.h>
#define MAX 5		/* 定義MAX為5 */
int main(void)
{
   int score[MAX]; 	/* 宣告score陣列，可存放MAX個整數 */
   int i=0,num;
   float sum=0.0f;
   
   printf("請輸入成績，要結束請輸入0:\n");
   do
   {
      if(i==MAX)		/* 當i的值為MAX時，表示陣列已滿，即停止輸入 */
      {
         printf("陣列空間已使用完畢!!\n"); 
         i++;			/* 此行先將i值加1，因為23行會把i的值減1掉 */
         break;
      }
      printf("請輸入成績:");
      scanf("%d",&score[i]);
   }while(score[i++]>0);   /* 輸入成績，輸入0時結束 */
   num=i-1;
   for(i=0;i<num;i++)
      sum+=score[i];		/* 計算平均成績 */
   printf("平均成績為 %.2f\n",sum/num);
   
   system("pause");
   return 0;
}
```
### 循序搜尋演算法[prog9_8 陣列的搜尋]
```
搜尋演算法有許多類型:
Linear Search循序搜尋
Binary Search
Jump Search
Interpolation Search
Exponential Search
Sublist Search (Search a linked list in another list)
Fibonacci Search
The Ubiquitous Binary Search
Recursive program to linearly search an element in a given array
Recursive function to do substring search
Unbounded Binary Search Example (Find the point where a monotonically increasing function becomes positive first time)
https://www.geeksforgeeks.org/searching-algorithms/
https://en.wikipedia.org/wiki/Search_algorithm
```
```
#include <stdio.h>
#include <stdlib.h>
#define SIZE 6		/* 定義SIZE為6 */
int main(void)
{
   int i,num,flag=0;
   int A[SIZE]={33,75,69,41,33,19};
		
   printf("陣列A元素的值為:");
   for(i=0;i<SIZE;i++)			
      printf("%d ",A[i]); 			/* 印出陣列的內容 */
   
   printf("\n請輸入欲搜尋的整數:");		
   scanf("%d",&num); 				/* 輸入欲搜尋的整數 */
   
   for(i=0;i<SIZE;i++)
      if(A[i]==num)	/* 判斷陣列元素是否與輸入值相同 */
      {
         printf("找到了! A[%d]=%d\n",i,A[i]);
         flag=1;		/* 設flag為1，代表有找到相同的數值 */
      }
   if(flag==0)
      printf("沒有找到相同值!!\n");
   
   system("pause");
   return 0;
}
```
###
```
/* prog9_9, 二維陣列的輸入輸出 */
#include <stdio.h>
#include <stdlib.h>
int main(void)
{
   int i,j,sale[2][4],sum=0;
		
   for(i=0;i<2;i++)
      for(j=0;j<4;j++)
      {
         printf("業務員%d的第%d季業績:",i+1,j+1);
         scanf("%d",&sale[i][j]); 		/* 輸入銷售量 */
      }
   
   printf("***Output***");
   for(i=0;i<2;i++)				/* 輸出銷售量並計算總銷售量 */
   {
      printf("\n業務員%d的業績分別為",i+1);
      for(j=0;j<4;j++)
      {
         printf("%d  ",sale[i][j]);
         sum+=sale[i][j];
      }
   }
   printf("\n2004年總銷售量為%d部車\n",sum);
   
   system("pause");
   return 0;
}
```
### 二維陣列及其運算:prog9_10, 矩陣的相加
```
#include <stdio.h>
#include <stdlib.h>
#define ROW 2		/* 定義ROW為2 */
#define COL 3		/* 定義COL為3 */
int main(void)
{
   int i,j;
   int A[ROW][COL]={{1,2,3},{5,6,8}};	/* 宣告陣列A並設定初值 */
   int B[ROW][COL]={{3,0,2},{3,5,7}};  	/* 宣告陣列B並設定初值 */ 
	
   printf("Matrix A+B=\n");
   for(i=0;i<ROW;i++)			/* 外層迴圈，用來控制列數 */
   {
      for(j=0;j<COL;j++)		/* 內層迴圈，用來控制行數 */
         printf("%3d",A[i][j]+B[i][j]); 		/* 計算二陣列相加 */
      printf("\n");
   }
   system("pause");
   return 0;
}
```
### 三維陣列及其運算
```
/* prog9_11, 三維陣列與初值的設定 */
#include <stdio.h>
#include <stdlib.h>
int main(void)
{
   int A[2][4][3]={{{21,32,65},
                     	{78,94,76},
                    	{79,44,65},
                    	{89,54,73}},
                   	  {{32,56,89},
                    	{43,23,32},
                    	{32,56,78},
                    	{94,78,45}}};
   
   int i,j,k,max=A[0][0][0];	/* 設定max為A陣列的第一個元素 */
		
   for(i=0;i<2;i++)	   		/* 外層迴圈 */
      for(j=0;j<4;j++)		/* 中層迴圈 */
         for(k=0;k<3;k++)		/* 內層迴圈 */
            if(max<A[i][j][k])
                max=A[i][j][k];
   
   printf("max=%d\n",max);	/* 印出陣列的最大值 */
   system("pause");
   return 0;
}
```
### 函數的參數傳遞:Call by value vs Call by address
```
/* prog9_12, 傳遞一維陣列到函數裡 */
#include <stdio.h>
#include <stdlib.h>
#define SIZE 4
void show(int arr[]);		/* 宣告函數show()的原型 */

int main(void)	
{
   int A[SIZE]={5,3,6,1};		/* 設定陣列A的初值 */

   printf("陣列的內容為: ");   
   
   show(A);					
   /* 呼叫函數show:將(A陣列的位址當作參數傳遞給show函數) */

   system("pause");
   return 0;
}

/* 定義show()函數 */
void show(int arr[])			
{
   int i;
   for(i=0;i<SIZE;i++)		
      printf("%d ",arr[i]); 	/* 印出陣列內容 */
   printf("\n");
}
```
### prog9_13, 變數的位址(address)與值(value)
```
/*  */
#include <stdio.h>
#include <stdlib.h>
void func(int);
int main(void)
{
   int a=13;
   printf("於main()裡,a=%d,a的位址=%p\n",a,&a);
   func(a);			/* 這是傳值呼叫的機制 */
   
   system("pause");
   return 0;
}

void func(int a)		/* 自訂函數func() */
{	
   printf("於func()裡,a=%d,a的位址為=%p\n",a,&a);
}
```
### prog9_14, 印出陣列的位址
```
#include <stdio.h>
#include <stdlib.h>
#define SIZE 3	
void func(int arr[]);
int main(void)
{
   int i,A[SIZE]={20,8,13};

   printf("在main()裡，陣列A元素的位址為\n"); 
   for(i=0;i<SIZE;i++)
      printf("A[%d]=%2d,位址為%p\n",i,A[i],&A[i]);
   func(A);				/* 這是傳址呼叫的機制 */
   
   system("pause");
   return 0;
}

void func(int arr[])		/* 自訂函數func() */
{	
   int i;
   printf("\n在func()裡，陣列arr元素的位址為\n");
   for(i=0;i<SIZE;i++)
      printf("arr[%d]=%2d,位址為%p\n",i,arr[i],&arr[i]);
}
```
### prog9_15, 印出陣列的位址
```
#include <stdio.h>
#include <stdlib.h>
#define SIZE 3
int main(void)
{
   int i,A[SIZE]={20,8,13};

   for(i=0;i<SIZE;i++)
      printf("A[%d]=%2d,位址為%p\n",i,A[i],&A[i]);
   printf("陣列A的位址=%p\n",A);    /* 印出陣列A的位址 */
   
   system("pause");
   return 0;
}
```
### prog9_16
```

```
### 氣泡排序法
```
prog9_17, 氣泡排序法
prog9_18, 氣泡排序法之改良版

```
## 字串==字元陣列
## 字串處理的各種練習
### prog9_19
```

```
###
```
/* prog9_20, 印出字元及字串的長度 */
#include <stdio.h>
#include <stdlib.h>
int main(void)
{
   char ch='a';				/* 宣告字元變數ch */
   char str1[]="a";			/* 宣告字串變數str1 */
   char str2[]="Sweet home";	/* 宣告字串變數str2 */   

   printf("字元ch佔了%d個位元組\n",sizeof(ch));
   printf("字串str1佔了%d個位元組\n",sizeof(str1));
   printf("字串str2佔了%d個位元組\n",sizeof(str2));
 
   system("pause");
   return 0;
}
```

###
```
/* prog9_21, 輸入及印出字串 */
#include <stdio.h>
#include <stdlib.h>
int main(void)
{
   char name[15];	/* 宣告字元陣列name */
		
   puts("What's your name?");
   gets(name);		/* 利用gets()讀入字串，並寫入字元陣列name裡 */
   puts("Hi!");
   puts(name);		/* 印出字元陣列name的內容 */
   puts("How are you?");
   system("pause");
   return 0;
}
```

### 字串處理[prog9_22, 將字串裡小寫字母轉換成大寫]
```
#include <stdio.h>
#include <stdlib.h>
void toUpper(char s[]);	/* 宣告函數toUpper()的原型 */

int main(void)
{
   char str[15];			/* 宣告可容納15個字元的陣列str */
		
   printf("請輸入一個字串: ");
   gets(str);			/* 輸入字串 */
   toUpper(str);			/* 呼叫toUpper() 函數 */
   printf("轉換成大寫後: %s\n",str);		/* 印出str字串的內容 */
   
   system("pause");
   return 0;
}

/* toUpper() 函數核心內容 */
void toUpper(char s[])
{
   int i=0;
   while(s[i]!='\0')		/* 如果s[i] 不等於\0，則執行下面的敘述 */
   {
      if(s[i]>=97 && s[i]<=122) /* 如果是小寫字母 */
         s[i]=s[i]-32;		/* 把小寫字母的ASCII碼減32，變成大寫 */
      i++;
   }
}
```
### 字串處理[將字串裡大寫字母轉換成小寫]
```
#include <stdio.h>
#include <stdlib.h>
void toLower(char s[]);	/* 宣告函數toLower()的原型 */

int main(void)
{
   char str[15];			/* 宣告可容納15個字元的陣列str */
		
   printf("請輸入一個字串: ");
   gets(str);			/* 輸入字串 */
   toLower(str);			/* 呼叫toLower() 函數 */
   printf("轉換成大寫後: %s\n",str);		
   
   system("pause");
   return 0;
}

/* toLower() 函數核心內容 */
void toLower(char s[])
{
   填入你的程式碼......
   }
}
```
### 字串反轉
```

```
## 字串陣列==陣列元素都是存字串

### 字串陣列[prog9_23]
```
#include <stdio.h>
#include <stdlib.h>
int main(void)
{
   char S[3][10]= {"Tom","Lily","James Lee"};
   int i;
   
   /* 使用for loop一一印出字串陣列內容 */
   for(i=0;i<3;i++)		
      printf("S[%d]=%s\n",i,S[i]);    
      
   printf("\n");
   
   /* 使用for loop一一印出字串陣列元素的內容(value)與位址(address)*/
   for(i=0;i<3;i++)	
   {
      /* 印出字串元素的內容(value) */
      printf("S[%d]=____\n",i,______);
      
      /* 印出字串元素的位址*/    
      printf("address of S[%d][0]=________\n\n",i,_______);
   }
   
   system("pause");
   return 0;
}
```
### 字串陣列的複製[prog9_24]
```
#include <stdio.h>
#include <stdlib.h>
#define MAX 3
#define LENGTH 10
int main(void)
{
   char arr1[MAX][LENGTH]={"Tom","Lily","James Lee"};
   char arr2[MAX][LENGTH];
   int i,j;
   
   /* 使用兩層loop(i,j)將arr1的內容複製到arr2中 */
   for(i=0;i<MAX;i++) 	
   {
      for(j=0;j<LENGTH;j++)
         if(arr1[i][j]=='\0')   /* 如果遇到「\0」,代表讀到字串結束==>要如何處理呀? */
            _______;		  		
         else
            arr2[i][j]=arr1[i][j];
            
        ______________;      /* 最後新陣列要補上「\0」字串結束 */
   }
   
   /* 使用 for loop 印出陣列arr2的內容 */
   for(i=0;i<MAX;i++) 	
      printf("arr2[%d]=%s\n",i,arr2[i]);  
   
   system("pause");
   return 0;
}
```
### 字串陣列的反轉

```
input輸入:char arr1[MAX][LENGTH]={"Tom","Lily","James Lee"};
output輸出:char arr2[MAX][LENGTH]={"m0T","yliL","eeL semaJ"};
```
### 字串陣列的大寫化
### 字串陣列的小寫化
