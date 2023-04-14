
- Aim: To implement and analysis merge sort. Algorithm using Divide and Conquer method
```c
#include<stdio.h>
#include<conio.h>
void  merge_sort(int low,int high,int a[],int b[])
{
Int  mid,i,j,k;
if(high<=low)
{
return;
}
mid=(low+high)/2;
i=low;
j=mid+1;

merge_sort(low,mid,a,b);
merge_sort(mid+1,high,a,b);
for(k=low;k<=high;k++)
{
if(i==mid+1){
b[k]=a[j];
j++;
}
else if(j==high+1)
{
b[k]=a[i];
i++;
}
else if(a[i]<a[j])
{
b[k]=a[i];
i++;
}
else
{
b[k]=a[j];
j++;
}
}
for(k=low;k<=high;k++)
{
a[k]=b[k];
}
}
void main()
{
Int  a[100], b[100], n, i, d, swap;
clrscr();
printf("Enter number of elements in the array:\n");
scanf("%d",&n);
printf("Enter %d integers\n",n);
for(i=0;i<n;i++)
scanf("%d",&a[i]);
merge_sort(0,n-1,a,b);
printf("Printing the sorted array:\n");
for(i=0;i<n;i++)
printf("\t%d",a[i]);
getch();

```
