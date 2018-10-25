# for 399
#include <stdio.h>
#include <stdlib.h>
int main(void)
{
   int i,sum=0;
   
   for(i=1;i<=399;i=i+2)			
      sum+=i;
      
   printf("1+3+5+7+....+399=%d\n",sum);	
   
   system("pause");
   return 0;
}
