- Aim: To implement and analysis Insertion Sort using c.
```c
#include<stdio.h>
#include<conio.h>
void main()
{
int i,j,count,temp,number[25];
clrscr();
printf("\nEnter how many elements you want to enter:");
scanf("%d",&count);
printf("Enter %d element:",count);
for(i=0;i<count;i++)
{
	scanf("%d",&number[i]);
}
for(i=1;i<count;i++)
{
	temp=number[i];
	j=i-1;
	while((temp<number[j])&&(j>=0))
	{
		number[j+1]=number[j];
		j=j-1;
	}
	number[j+1]=temp;
}
printf("\nsorted elements:");
for(i=0;i<count;i++)
{
	printf("\n%d",number[i]);
}
getch();
}
```

