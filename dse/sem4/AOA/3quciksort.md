- Aim: To implement and analysis quick sort. Algorithm using Divide and Conquer method
```c
#include<stdio.h>
#include<conio.h>
int  a[40];
void  quicksort(int a[],int LB,int UB);
int  partition(int a[],int LB,int UB);
void  quicksort(int a[],int LB, int UB)
{
int  LOC;
if(LB<UB)
{
LOC=partition(a,LB,UB);
quicksort(a,LB,LOC-1);
quicksort(a,LOC+1,UB);
}
}
int  partition(int a[],int LB,int UB)
{
int  START, PIVOT, END, temp;
PIVOT=a[LB];
START=LB;
END=UB;
while(START<END)
{
while(a[START]<=PIVOT)
{
START++;
}
while(a[END]>PIVOT)
{
END--;
}
if(START<END)
{
temp=a[START];
a[START]=a[END];
a[END]=temp;
}
}
temp=a[LB];
a[LB]=a[END];
a[END]=temp;
return END;
}
void main()
{
int  n, i;
clrscr();
printf("\n enter number of elements: ");
scanf("%d",&n);
printf("\n Enter elements:");
for(i=1;i<=n;i++)
{
printf("\nenter a[%d]:",i);
scanf("%d",&a[i]);
}
quicksort(a,1,n);
printf("\n sorted elements: ");
for(i=1;i<=n;i++)
{
printf("\t%d",a[i]);
}
getch();
}

```
