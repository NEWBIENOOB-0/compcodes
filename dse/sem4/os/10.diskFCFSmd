-  Program to demonstrate disk scheduling using FCFS

```c
#include <stdio.h>
#include <stdlib.h>
void main() {
    //variable declaration
    int queuesize=8;
    int startcylinder=53;
    int i,j;
    int seektime=0;
    //Input
    int requestcylinder[8]={98,183,37,122,14,124,65,67};   
    //processing
    for(i=0;i<queuesize;i++){
        printf("processing %d\n",requestcylinder[i]);
        seektime=seektime+abs(requestcylinder[i]-startcylinder);
        startcylinder=requestcylinder[i];
    }
    //output
    printf("Total seek time = %d ",seektime);
}

```
