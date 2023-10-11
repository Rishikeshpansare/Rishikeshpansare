include<stdio.h>
#include<conio.h>
#define MAXSIZE 100
typedefstruct
{
int data[MAXSIZE];
int top;
}STACK;
STACK *s;

voidinitstack(STACK *s)
{
s->top=-1;
}

intisEmpty(STACK *s)
{
if(s->top==-1)
 {
return 1;
 }
return 0;
}

intisFull(STACK *s)
{
if(s->top==MAXSIZE-1)
 {
return 1;
 }
return 0;
}

void Push(STACK *s,intnum)
{
if(isFull(s))
 {
printf("Stack is Full");
 }
else
 {
s->top=s->top+1;
s->data[s->top]=num;
 }
}

int Pop(STACK *s)
{
intnum;
if(isEmpty(s))
 {
printf("Stack is Empty");
 }
else
 {
num=s->data[s->top];
s->top=s->top-1;
returnnum;
 }
return 0;
}

void Display(STACK *s)
{
int i;
for(i=s->top;i>=0;i--)
 {
printf("\n%d",s->data[i]);
 }
}

void main()
{
intnum,ch;
 STACK s;
initstack(&s);
do
 {
printf("\nThe menu are:\n");
printf("1:Push\n");
printf("2:Pop\n");
printf("3:Display\n");
printf("4:Exit\n");
printf("Enter your Choice:\n");
scanf("%d",&ch);
switch(ch)
  {
case 1:printf("\nEnter a no");
	scanf("%d",&num);
	Push(&s,num);
	break;
case 2:printf("\npoped element is %d",Pop(&s));
	break;
case 3:Display(&s);
	break;
default:printf("\nEnter correct Choice\n");
  }
}while(ch!=4);
}



