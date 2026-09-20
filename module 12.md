# EXP NO 26: C PROGRAM TO DISPLAY STACK ELEMENTS USING LINKED LIST.

## Aim:
To write a C program to display stack elements using linked list.

## Algorithm:
1.	Define a structure Node with two members: data to store the integer value and next to point to the next node in the linked list.
2.	Declare a global variable head representing the starting node of the linked list.
3.	Define a function display to print the elements of the linked list.
4.	Declare a pointer p and initialize it with the head of the linked list.
5.	Use a while loop to traverse the linked list:
6.	Print the data of the current node.
7.	Move to the next node using the next pointer.
 
## Program:
```c
#include <stdio.h>
#include <stdlib.h>

struct Node
{
    int data;
    struct Node *next;
};

struct Node *head = NULL;

void display()
{
    struct Node *p = head;

    if (p == NULL)
    {
        printf("Stack is empty.\n");
        return;
    }

    printf("Stack elements are:\n");

    while (p != NULL)
    {
        printf("%d\n", p->data);
        p = p->next;
    }
}

int main()
{
    struct Node *n1, *n2, *n3;

    n1 = (struct Node *)malloc(sizeof(struct Node));
    n2 = (struct Node *)malloc(sizeof(struct Node));
    n3 = (struct Node *)malloc(sizeof(struct Node));

    n1->data = 30;
    n1->next = n2;

    n2->data = 20;
    n2->next = n3;

    n3->data = 10;
    n3->next = NULL;

    head = n1;

    printf("Displaying stack elements:\n");
    display();

    return 0;
}
```

## Output:
<img width="286" height="165" alt="image" src="https://github.com/user-attachments/assets/82a4e087-88ac-4b3f-ad6c-932a2d39083e" />

## Result:
Thus, the program to display stack elements using linked list is verified successfully. 


# EXP.NO 27: C PROGRAM TO POP AN ELEMENT FROM THE GIVEN STACK USING LINKED LIST.

## Aim:
To write a C program to pop an element from the given stack using liked list.

## Algorithm:
1.	Check for Empty Stack
2.	If head is equal to NULL, Print "Stack is empty."
3.	Else Proceed to the next step.
4.	Set head to point to the next node in the stack.
 
## Program:
```c
#include <stdio.h>
#include <stdlib.h>

struct Node
{
    int data;
    struct Node *next;
};

struct Node *head = NULL;

void pop()
{
    struct Node *p;

    if (head == NULL)
    {
        printf("Stack is empty.\n");
        return;
    }

    p = head;

    printf("Popped element = %d\n", head->data);

    head = head->next;

    free(p);
}

void display()
{
    struct Node *p = head;

    printf("Stack elements are:\n");

    while (p != NULL)
    {
        printf("%d\n", p->data);
        p = p->next;
    }
}

int main()
{
    struct Node *n1, *n2, *n3;

    n1 = (struct Node *)malloc(sizeof(struct Node));
    n2 = (struct Node *)malloc(sizeof(struct Node));
    n3 = (struct Node *)malloc(sizeof(struct Node));

    n1->data = 30;
    n1->next = n2;

    n2->data = 20;
    n2->next = n3;

    n3->data = 10;
    n3->next = NULL;

    head = n1;

    printf("Before POP operation:\n");
    display();

    pop();

    printf("\nAfter POP operation:\n");
    display();

    return 0;
}
```

## Output:
<img width="246" height="310" alt="image" src="https://github.com/user-attachments/assets/3827e338-c0f9-465f-a7f3-e4db743f0290" />

## Result:
Thus, the program to pop an element from the given stack using liked list is verified successfully.

 
# EXP NO:28 C PROGRAM TO DISPLAY QUEUE ELEMENTS USING LINKED LIST.

## Aim:
To write a C program to display queue elements using linked list.

## Algorithm:
1.	Check if Queue is Empty
2.	Display Queue Elements
3.	Print the data of the current node pointed to by front
4.	Update front to point to the next node.
5.	End the display function.
 
## Program:
```c
#include <stdio.h>
#include <stdlib.h>

struct Node
{
    int data;
    struct Node *next;
};

struct Node *front = NULL;
struct Node *rear = NULL;

void display()
{
    struct Node *p = front;

    if (front == NULL)
    {
        printf("Queue is empty.\n");
        return;
    }

    printf("Queue elements are:\n");

    while (p != NULL)
    {
        printf("%d ", p->data);
        p = p->next;
    }

    printf("\n");
}

int main()
{
    struct Node *n1, *n2, *n3;

    n1 = (struct Node *)malloc(sizeof(struct Node));
    n2 = (struct Node *)malloc(sizeof(struct Node));
    n3 = (struct Node *)malloc(sizeof(struct Node));

    n1->data = 10;
    n1->next = n2;

    n2->data = 20;
    n2->next = n3;

    n3->data = 30;
    n3->next = NULL;

    front = n1;
    rear = n3;

    printf("Displaying queue elements:\n");
    display();

    return 0;
}
```

## Output:
<img width="286" height="113" alt="image" src="https://github.com/user-attachments/assets/2dbc9345-4c8b-4bdf-9b31-50c85e6b1352" />

## Result:
Thus, the program to display queue elements using linked list is verified successfully.


# EXP NO:29 C PROGRAM TO INSERT ELEMENTS IN QUEUE USING LINKED LIST

## Aim:
To write a C program to insert elements in queue using linked list

## Algorithm:
1.	Allocate Memory for New Node
2.	Set Data and Next Pointer
3.	Check if Queue is Empty
4.	Set both front and rear to point to the new node p.
5.	Set the next pointer of the current rear to point to the new node p.
6.	End of Enqueue Operation
 
## Program:
```c
#include <stdio.h>
#include <stdlib.h>

struct Node
{
    int data;
    struct Node *next;
};

struct Node *front = NULL;
struct Node *rear = NULL;

void enqueue(int value)
{
    struct Node *p;

    p = (struct Node *)malloc(sizeof(struct Node));

    p->data = value;
    p->next = NULL;

    if (front == NULL)
    {
        front = p;
        rear = p;
    }
    else
    {
        rear->next = p;
        rear = p;
    }

    printf("Element %d inserted into queue.\n", value);
}

void display()
{
    struct Node *p = front;

    printf("Queue elements are:\n");

    while (p != NULL)
    {
        printf("%d ", p->data);
        p = p->next;
    }

    printf("\n");
}

int main()
{
    int value;

    printf("Enter first element: ");
    scanf("%d", &value);
    enqueue(value);

    printf("Enter second element: ");
    scanf("%d", &value);
    enqueue(value);

    printf("Enter third element: ");
    scanf("%d", &value);
    enqueue(value);

    printf("\n");
    display();

    return 0;
}
```

## Output:
<img width="346" height="270" alt="image" src="https://github.com/user-attachments/assets/ffb45052-03f7-46d0-b9e2-bf2872dfd26e" />

## Result:
Thus, the program to insert elements in queue using linked list is verified successfully.


# EXP NO:30 C FUNCTION TO FIND THE PEEK OF QUEUE USING LINKED LIST.

## Aim:
The aim of this function is to retrieve the "peek" (the front element) of a queue implemented using a linked list

## Algorithm:
1.	Check if the queue is empty:
o	If the queue is empty (i.e., the front pointer is NULL), return an error or a message indicating that the queue is empty.
2.	Access the front element:
o	If the queue is not empty, return the data stored in the front node of the linked list (i.e., the element at the head of the queue).

## Program:
```c
#include <stdio.h>
#include <stdlib.h>

struct Node
{
    int data;
    struct Node *next;
};

struct Node *front = NULL;
struct Node *rear = NULL;

int peek()
{
    if (front == NULL)
    {
        printf("Queue is empty.\n");
        return -1;
    }

    return front->data;
}

void enqueue(int value)
{
    struct Node *p;

    p = (struct Node *)malloc(sizeof(struct Node));

    p->data = value;
    p->next = NULL;

    if (front == NULL)
    {
        front = p;
        rear = p;
    }
    else
    {
        rear->next = p;
        rear = p;
    }
}

void display()
{
    struct Node *p = front;

    printf("Queue elements are:\n");

    while (p != NULL)
    {
        printf("%d ", p->data);
        p = p->next;
    }

    printf("\n");
}

int main()
{
    int result;

    enqueue(10);
    enqueue(20);
    enqueue(30);

    display();

    result = peek();

    if (result != -1)
    {
        printf("Peek element of the queue = %d\n", result);
    }

    return 0;
}
```

## Output:
<img width="340" height="112" alt="image" src="https://github.com/user-attachments/assets/c7f4ddf1-003a-457b-95c0-770721ae2af8" />

## Result:
Thus, the program to retrieve the "peek" (the front element) of a queue implemented using a linked list is verified successfully.

