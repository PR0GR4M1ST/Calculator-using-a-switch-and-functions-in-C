#include <stdio.h>
#include <conio.h>
#include <stdlib.h>

int add(int a, int b)
{ return a + b; }

int sub(int a, int b)
{ return a - b; }

int mul(int a, int b)
{ return a * b; }

int div(int a, int b)
{ return a / b; }

int main()
{
    int num1, num2, choice;

    printf("[0] Exit\v[1] Add\v[2] Subtract\v[3] Multiply\v[4] Divide");
    scanf("%d", &choice);

    int(*f)(int, int);
    switch (choice)
    {
    case 0:
        return 0;
        break;

    case 1:
        f = &add;
        break;

    case 2:
        f = &sub;
        break;

    case 3:
        f = &mul;
        break;

    case 4:
        f = &div;
        break;

    default:
        printf("That is not a valid choice.");
        return 0;
    }

    printf("Enter 1st number:\n");
    scanf("%d", &num1);
    printf("Enter 2nd number:\n");
    scanf("%d", &num2);

    printf("%d", f(num1, num2));
}
