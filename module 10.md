# EXP NO:16 C PROGRAM TO SEARCH A GIVEN ELEMENT IN THE GIVEN LINKED LIST.

## Aim:
To write a C program to search a given element in the given linked list.

## Algorithm:
1.	Define the structure for a node in a linked list.
2.	Define the search function to find a specific character in the linked list.
3.	Initialize the head of the linked list as needed.
4.	Call the search function and perform other linked list operations as needed.
 
## Program:
```c
#include <stdio.h>
#include <stdlib.h>

struct Node
{
    char data;
    struct Node *next;
};

void search(struct Node *head, char key)
{
    struct Node *temp = head;
    int position = 1;

    while (temp != NULL)
    {
        if (temp->data == key)
        {
            printf("Element %c found at position %d\n", key, position);
            return;
        }

        temp = temp->next;
        position++;
    }

    printf("Element %c not found in the linked list\n", key);
}

int main()
{
    struct Node *head = NULL;
    struct Node *second = NULL;
    struct Node *third = NULL;
    char key;

    head = (struct Node *)malloc(sizeof(struct Node));
    second = (struct Node *)malloc(sizeof(struct Node));
    third = (struct Node *)malloc(sizeof(struct Node));

    head->data = 'A';
    head->next = second;

    second->data = 'B';
    second->next = third;

    third->data = 'C';
    third->next = NULL;

    printf("Linked List: A -> B -> C\n");

    printf("Enter element to search: ");
    scanf(" %c", &key);

    search(head, key);

    free(head);
    free(second);
    free(third);

    return 0;
}
```

## Output:
<img width="327" height="122" alt="image" src="https://github.com/user-attachments/assets/0645ed24-5df0-4785-8cc2-3fe34e867f13" />

## Result:
Thus, the program to search a given element in the given linked list is verified successfully.


# EXP NO:17  PROGRAM TO INSERT A NODE IN A LINKED LIST.

## Aim:
To write a C program to insert a node in a linked list.

## Algorithm:
1.	Define the structure for a node in a linked list
2.	Define the insert function to insert a new node with character data at the end of the linked list.
3.	Initialize the head of the linked list as needed.
4.	Call the insert function and perform other linked list operations as needed.
 
## Program:
```c
#include <stdio.h>
#include <stdlib.h>

struct Node
{
    char data;
    struct Node *next;
};

void insert(struct Node **head, char value)
{
    struct Node *newNode;
    struct Node *temp;

    newNode = (struct Node *)malloc(sizeof(struct Node));

    newNode->data = value;
    newNode->next = NULL;

    if (*head == NULL)
    {
        *head = newNode;
    }
    else
    {
        temp = *head;

        while (temp->next != NULL)
        {
            temp = temp->next;
        }

        temp->next = newNode;
    }
}

void display(struct Node *head)
{
    struct Node *temp = head;

    while (temp != NULL)
    {
        printf("%c -> ", temp->data);
        temp = temp->next;
    }

    printf("NULL\n");
}

int main()
{
    struct Node *head = NULL;
    char value;

    insert(&head, 'A');
    insert(&head, 'B');

    printf("Before insertion:\n");
    display(head);

    printf("Enter character to insert: ");
    scanf(" %c", &value);

    insert(&head, value);

    printf("After insertion:\n");
    display(head);

    return 0;
}
```

## Output:
<img width="307" height="176" alt="image" src="https://github.com/user-attachments/assets/a412419c-c5cb-4d2d-998c-a5a7b7edb01e" />

## Result:
Thus, the program to insert a node in a linked list is verified successfully.


# EXP NO:18 C PROGRAM TO TRAVERSE A DOUBLY LINKED LIST

## Aim:
To write a C program to traverse a doubly linked list.

## Algorithm:
1.	Initialize a temporary pointer (temp) to the head of the list.
2.	Use a while loop to traverse the list until the end (temp == NULL) is reached.
3.	Inside the loop, print the data of the current node.
4.	Move to the next node by updating the temp pointer to point to the next node (temp = temp->next).
 
## Program:
```c
#include <stdio.h>
#include <stdlib.h>

struct Node
{
    int data;
    struct Node *prev;
    struct Node *next;
};

int main()
{
    struct Node *head = NULL;
    struct Node *second = NULL;
    struct Node *third = NULL;
    struct Node *temp;

    head = (struct Node *)malloc(sizeof(struct Node));
    second = (struct Node *)malloc(sizeof(struct Node));
    third = (struct Node *)malloc(sizeof(struct Node));

    head->data = 10;
    head->prev = NULL;
    head->next = second;

    second->data = 20;
    second->prev = head;
    second->next = third;

    third->data = 30;
    third->prev = second;
    third->next = NULL;

    temp = head;

    printf("Doubly Linked List:\n");

    while (temp != NULL)
    {
        printf("%d ", temp->data);
        temp = temp->next;
    }

    printf("\n");

    free(head);
    free(second);
    free(third);

    return 0;
}
```

## Output:
<img width="217" height="92" alt="image" src="https://github.com/user-attachments/assets/0ec0f980-597e-4df5-bd01-70377115a18e" />

## Result:
Thus, the program to traverse a doubly linked list is verified successfully. 



# EXP NO:19 C PROGRAM TO INSERT AN ELEMENT IN DOUBLY LINKED LIST

## Aim:
To write a C program to insert an element in doubly linked list

## Algorithm:
1.	Create a new node (newNode) and allocate memory for it.
2.	Set the data of the new node to the provided value.
3.	If the list is empty, set the new node as the head.
4.	If the list is not empty, traverse the list to find the last node.
5.	Set the new node's prev pointer to the last node and update the last node's next pointer to the new node.
 
## Program:
```c
#include <stdio.h>
#include <stdlib.h>

struct Node
{
    int data;
    struct Node *prev;
    struct Node *next;
};

void insert(struct Node **head, int value)
{
    struct Node *newNode;
    struct Node *temp;

    newNode = (struct Node *)malloc(sizeof(struct Node));

    newNode->data = value;
    newNode->next = NULL;
    newNode->prev = NULL;

    if (*head == NULL)
    {
        *head = newNode;
    }
    else
    {
        temp = *head;

        while (temp->next != NULL)
        {
            temp = temp->next;
        }

        temp->next = newNode;
        newNode->prev = temp;
    }
}

void display(struct Node *head)
{
    struct Node *temp = head;

    while (temp != NULL)
    {
        printf("%d ", temp->data);
        temp = temp->next;
    }

    printf("\n");
}

int main()
{
    struct Node *head = NULL;
    int value;

    insert(&head, 10);
    insert(&head, 20);

    printf("Before insertion:\n");
    display(head);

    printf("Enter element to insert: ");
    scanf("%d", &value);

    insert(&head, value);

    printf("After insertion:\n");
    display(head);

    return 0;
}
```

## Output:
<img width="301" height="188" alt="image" src="https://github.com/user-attachments/assets/69492522-6dd8-4737-bf82-168dde8dffee" />

## Result:
Thus, the program to insert an element in doubly linked list is verified successfully.


# EXP NO:20 C FUNCTION TO DELETE A GIVEN ELEMENT IN THE GIVEN LINKED LIST

## Aim:
To write a C function that deletes a given element from a linked list.

## Algorithm:
1.	Check if the Linked List is Empty:
o	If the head of the linked list is NULL, print a message indicating the list is empty and exit the function.
2.	Traverse the Linked List:
o	Start from the head node and iterate through the list to find the node that contains the given element (data).
3.	Handle Deletion of the First Node:
o	If the element to be deleted is found in the head node:
	Update the head of the linked list to point to the next node (i.e., head = head->next).
	Free the memory allocated to the node to be deleted.
	Exit the function.
4.	Traverse and Delete from the Middle or End:
o	If the element is not in the head node, continue traversing the list by checking each node’s next pointer.
o	When the node with the element is found, update the previous node’s next pointer to point to the next node of the node to be deleted (prev->next = current->next).
o	Free the memory allocated to the node to be deleted.
5.	Handle the Case when the Element is Not Found:
o	If the element is not found in any node, print a message indicating the element is not present in the list.
6.	End the Function.

## Program:
```c
#include <stdio.h>
#include <stdlib.h>

struct Node
{
    int data;
    struct Node *next;
};

void deleteElement(struct Node **head, int value)
{
    struct Node *current = *head;
    struct Node *prev = NULL;

    if (*head == NULL)
    {
        printf("Linked List is empty\n");
        return;
    }

    if (current->data == value)
    {
        *head = current->next;
        free(current);

        printf("Element %d deleted successfully\n", value);
        return;
    }

    while (current != NULL && current->data != value)
    {
        prev = current;
        current = current->next;
    }

    if (current == NULL)
    {
        printf("Element %d is not present in the list\n", value);
        return;
    }

    prev->next = current->next;
    free(current);

    printf("Element %d deleted successfully\n", value);
}

void display(struct Node *head)
{
    struct Node *temp = head;

    while (temp != NULL)
    {
        printf("%d -> ", temp->data);
        temp = temp->next;
    }

    printf("NULL\n");
}

int main()
{
    struct Node *head = NULL;
    struct Node *second = NULL;
    struct Node *third = NULL;
    int value;

    head = (struct Node *)malloc(sizeof(struct Node));
    second = (struct Node *)malloc(sizeof(struct Node));
    third = (struct Node *)malloc(sizeof(struct Node));

    head->data = 10;
    head->next = second;

    second->data = 20;
    second->next = third;

    third->data = 30;
    third->next = NULL;

    printf("Before deletion:\n");
    display(head);

    printf("Enter element to delete: ");
    scanf("%d", &value);

    deleteElement(&head, value);

    printf("After deletion:\n");
    display(head);

    free(head);
    free(second);
    free(third);

    return 0;
}
```

## Output:
<img width="445" height="233" alt="image" src="https://github.com/user-attachments/assets/04151849-1c37-47b5-b17c-3178c95f413d" />

## Result:
Thus, the function that deletes a given element from a linked list is verified successfully.




