
- AIM: To implement and analysi's of selection soed using C
```c

#include<stdio.h>
#include<conio.h>
void main()
{
int a[80],i,j,min,n,temp,k;
clrscr();
printf("\n enter your number:");
scanf("%d",&n);
for(i=0;i<n;i++)
{
printf("\n enter %d elements:",i+1);
scanf("%d",&a[i]);
}
for(i=0;i<n-1;i++)
{
int min=i;
for(j=i+1;j<n;j++)
{
if(a[j]<a[min])
{
min=j;
}
}
if(min!=i)
{
temp=a[i];
a[i]=a[min];
a[min]=temp;
}
printf("\n oputput after %d pass:",i+1);
for(k=0;k<n;k++)
{
printf("\t%d",a[k]);
}
}
getch();
}
```
