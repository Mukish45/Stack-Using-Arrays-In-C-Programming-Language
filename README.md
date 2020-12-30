# Stack-Using-Arrays-In-C-Programming-Language
C program to implement stack using arrays
#include<stdio.h>
#define N 5

int stack[N],x;
int top = -1;

void push();
void pop();
void isEmpty();
void size();
void topElement();
void display();
void printline();

void main()
{
    int a;
    do
    {
        printf("\n 1.Push 2.Pop 3. Is Empty 4. Size 5. Top Element 6. Display 0. Stop : ");
        scanf("%d", &a);
        printline();
        switch(a)
        {
        case 1:
            push();
            break;
        case 2:
            pop();
            break;
        case 3:
            isEmpty();
            break;
        case 4:
            size();
            break;
        case 5:
            topElement();
            break;
        case 6:
            display();
            break;
        case 0:
            printf("\nExit condition\n");
            break ;
        default:
            printf("\nInvalid choice\n");
        }
    }
    while(a!=0);
}

void push()
{
    if(top>=N-1)
    {
        printf("\nOverflow condition\n\n");
    }
    else
    {
        printf("\n\nEnter the element:");
        scanf("%d", &x);
        top++;
        stack[top]=x;
    }
    printline();
}

void pop()
{
    int y;
    if(top<=-1)
    {
        printf("\n\nUnderflow condition\n\n");
    }
    else
    {
        y = stack[top];
        top--;
        printf("\nPopped item is %d", y);
    }
    printline();
}

void isEmpty()
{
    if(top<=-1)
    {
        printf("\nStack is empty\n");
    }
    else
    {
        printf("\nStack has some elements\n");
    }
    printline();
}

void size()
{
    if(top<=-1)
    {
        printf("\n Underflow condition\n");
    }
    else
    {
        printf("\nThe size of the stack is: %d\n", top+1);
    }
    printline();
}

void topElement()
{
    if(top==-1)
    {
        printf("\nStack is empty\n");
    }
    else{
    int item;
    item = stack[top];
    printf("\nTop element is %d\n", item);
    }
    printline();
}

void display()
{
    int i;
    if(top==-1)
    {
        printf("\n\n Stack is empty\n");
    }
    else
    {
        printf("\nElements of the stack are:");
        for(i=top; i>=0; i--)
            {
                printf("%d  ", stack[i]);
        }
    }
    printf("\n");
    printline();
}

void printline()
{
    printf("\n--------------------------------------------------------------\n");
}
