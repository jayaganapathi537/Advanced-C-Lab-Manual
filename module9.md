EXP NO:11 C PROGRAM TO DISPLAY STACK ELEMENTS USING AN ARRAY.

Aim:
To write a C program to display stack elements using an array.
Algorithm:
1.	Include Necessary Header Files
2.	Declare Global Variables
3.	Define the Display Function
4.	Main Function (or Other Relevant Code)
5.	Initialize the stack and top as needed.
6.	Perform stack operations (push, pop, etc.).
7.	Use the display function to visualize the stack's contents
 
Program:
```c
#include <stdio.h>
#define MAX 5 

struct Stack {
    int arr[MAX];
    int top;
};

void initStack(struct Stack* stack) {
    stack->top = -1;
}

int isFull(struct Stack* stack) {
    return stack->top == MAX - 1;
}

int isEmpty(struct Stack* stack) {
    return stack->top == -1;
}

void push(struct Stack* stack, int value) {
    if (isFull(stack)) {
        printf("Stack is full! Cannot push %d\n", value);
    } else {
        stack->arr[++stack->top] = value;
        printf("Pushed %d into the stack\n", value);
    }
}

int pop(struct Stack* stack) {
    if (isEmpty(stack)) {
        printf("Stack is empty! Cannot pop.\n");
        return -1;
    } else {
        return stack->arr[stack->top--];
    }
}
void display(struct Stack* stack) {
    if (isEmpty(stack)) {
        printf("Stack is empty! Nothing to display.\n");
    } else {
        printf("Stack elements are:\n");
        for (int i = stack->top; i >= 0; i--) {
            printf("%d ", stack->arr[i]);
        }
        printf("\n");
    }
}

int main() {
    struct Stack stack;
    initStack(&stack);
    push(&stack, 10);
    push(&stack, 20);
    push(&stack, 30);
    display(&stack);
    printf("Popped element: %d\n", pop(&stack));
    display(&stack);

    return 0;
}
```
Output:
![image](https://github.com/user-attachments/assets/a602b664-7bbd-4cf3-845e-974937cb01f6)


Result:
Thus, the program to display stack elements using an array is verified successfully.
 

EXP NO:12  PROGRAM TO PUSH THE GIVEN ELEMENT IN TO A STACK USING ARRAY.
Aim:
To create a C program to push the given element in to a stack using array.
Algorithm:
1.	Declare global variables for the stack size, top index, and the stack itself.
2.	Define the push function to add a floating-point number to the stack.
3.	Initialize the stack size, top index, and the stack itself.
4.	Call the push function as needed.
 
Program:
```c
#include <stdio.h>
#define MAX 5 
struct Stack {
    int arr[MAX];
    int top;
};

void initStack(struct Stack* stack) {
    stack->top = -1;  
}

int isFull(struct Stack* stack) {
    return stack->top == MAX - 1;
}

void push(struct Stack* stack, int value) {
    if (isFull(stack)) {
        printf("Stack is full! Cannot push %d\n", value);
    } else {
        stack->arr[++stack->top] = value;  // Increment top and add value to stack
        printf("Pushed %d into the stack\n", value);
    }
}
void display(struct Stack* stack) {
    if (stack->top == -1) {
        printf("Stack is empty! Nothing to display.\n");
    } else {
        printf("Stack elements are:\n");
        for (int i = stack->top; i >= 0; i--) {
            printf("%d ", stack->arr[i]);
        }
        printf("\n");
    }
}

int main() {
    struct Stack stack;
    int value;

    initStack(&stack);

    push(&stack, 10);
    push(&stack, 20);
    push(&stack, 30);

    display(&stack);

    printf("Enter a number to push: ");
    scanf("%d", &value);
    push(&stack, value);

    display(&stack);

    return 0;
}
```

Output:
![image](https://github.com/user-attachments/assets/e8ee8057-2ddc-4c1c-b7e9-037c0463a91c)

Result:
Thus, the program to push the given element in to a stack using array is verified successfully


 
EXP NO:13 C PROGRAM TO DISPLAY QUEUE ELEMENTS USING ARRAY.
Aim:
To write a C program to display queue elements using array

Algorithm:
1.	Declare global variables for the queue, rear, front, and iteration.
2.	Define the display function to print the elements of the queue.
3.	Initialize the queue, rear, and front as needed.
4.	Call the display function and perform other queue operations as needed.
 
Program:
```c
#include <stdio.h>
#define MAX 5 
struct Queue {
    int arr[MAX];
    int front;
    int rear;
};

void initQueue(struct Queue* queue) {
    queue->front = -1;
    queue->rear = -1;
}

int isFull(struct Queue* queue) {
    return queue->rear == MAX - 1;
}

int isEmpty(struct Queue* queue) {
    return queue->front == -1 || queue->front > queue->rear;
}

void enqueue(struct Queue* queue, int value) {
    if (isFull(queue)) {
        printf("Queue is full! Cannot enqueue %d\n", value);
    } else {
        if (queue->front == -1) {
            queue->front = 0;  
        }
        queue->arr[++queue->rear] = value;
        printf("Enqueued %d into the queue\n", value);
    }
}

int dequeue(struct Queue* queue) {
    if (isEmpty(queue)) {
        printf("Queue is empty! Cannot dequeue.\n");
        return -1; 
    } else {
        return queue->arr[queue->front++];  
    }
}

void display(struct Queue* queue) {
    if (isEmpty(queue)) {
        printf("Queue is empty! Nothing to display.\n");
    } else {
        printf("Queue elements are:\n");
        for (int i = queue->front; i <= queue->rear; i++) {
            printf("%d ", queue->arr[i]);
        }
        printf("\n");
    }
}

int main() {
    struct Queue queue;

    initQueue(&queue);

    enqueue(&queue, 10);
    enqueue(&queue, 20);
    enqueue(&queue, 30);

    display(&queue);

    printf("Dequeued element: %d\n", dequeue(&queue));

    display(&queue);

    return 0;
}
```
Output:
![image](https://github.com/user-attachments/assets/fa5dbead-4efd-4f2f-8217-cb820348d760)

Result:
Thus, the program to display queue elements using array is verified successfully.


 
EXP NO:14 C PROGRAM TO INSERT ELEMENTS IN QUEUE USING ARRAY.
Aim:
To write a C program to insert elements in queue using array.

Algorithm:
1.	Declare global variables for the size, rear, front, and the queue itself.
2.	Define the enqueue function to add a float to the queue.
3.	Initialize the rear, front, and size of the queue as needed.
4.	Call the enqueue function as needed.

Program:
```c
#include <stdio.h>
#define MAX 5
struct Queue {
    int arr[MAX];
    int front;
    int rear;
};
void initQueue(struct Queue* queue) {
    queue->front = -1;
    queue->rear = -1;
}
int isFull(struct Queue* queue) {
    return queue->rear == MAX - 1;
}

int isEmpty(struct Queue* queue) {
    return queue->front == -1 || queue->front > queue->rear;
}

void enqueue(struct Queue* queue, int value) {
    if (isFull(queue)) {
        printf("Queue is full! Cannot enqueue %d\n", value);
    } else {
        if (queue->front == -1) {
            queue->front = 0; 
        queue->arr[++queue->rear] = value;
        printf("Enqueued %d into the queue\n", value);
    }
}
void display(struct Queue* queue) {
    if (isEmpty(queue)) {
        printf("Queue is empty! Nothing to display.\n");
    } else {
        printf("Queue elements are:\n");
        for (int i = queue->front; i <= queue->rear; i++) {
            printf("%d ", queue->arr[i]);
        }
        printf("\n");
    }
}

int main() {
    struct Queue queue;
    int value;
    initQueue(&queue);
    enqueue(&queue, 10);
    enqueue(&queue, 20);
    enqueue(&queue, 30);
    enqueue(&queue, 40);
    enqueue(&queue, 50);
    display(&queue);
    printf("Enter a number to enqueue: ");
    scanf("%d", &value);
    enqueue(&queue, value);
    display(&queue);

    return 0;
}
```

Output:
![image](https://github.com/user-attachments/assets/1ce81c60-9b1c-408d-9cae-75fc1ef8d9f7)


Result:
Thus, the program to insert elements in queue using array is verified successfully.



 
EXP NO:15 C FUNCTION TO DELETE ELEMENTS IN QUEUE USING ARRAY



Aim:

To create a function in C that deletes an element from a queue implemented using an array.

Algorithm:

1.	Check if the Queue is Empty
o	If the front pointer is -1, it means the queue is empty, and there are no elements to delete. Print a message indicating that the queue is empty.
2.	Delete the Front Element
o	If the queue is not empty, the element at the front index is deleted.
o	Increment the front pointer by 1 to remove the element and point to the next element in the queue.
3.	Check if the Queue Becomes Empty After Deletion:
o	After deletion, check if the front pointer has passed the rear pointer (front > rear). If this is true, reset both front and rear to -1, indicating that the queue is now empty.
4.	End the Function.



Program:
```c
#include <stdio.h>
#define MAX 5 
struct Queue {
    int arr[MAX];
    int front;
    int rear;
};

void initQueue(struct Queue* queue) {
    queue->front = -1;
    queue->rear = -1;
}

int isFull(struct Queue* queue) {
    return queue->rear == MAX - 1;
}

int isEmpty(struct Queue* queue) {
    return queue->front == -1 || queue->front > queue->rear;
}

void enqueue(struct Queue* queue, int value) {
    if (isFull(queue)) {
        printf("Queue is full! Cannot enqueue %d\n", value);
    } else {
        if (queue->front == -1) {
            queue->front = 0; 
        }
        queue->arr[++queue->rear] = value; 
        printf("Enqueued %d into the queue\n", value);
    }
}

int dequeue(struct Queue* queue) {
    if (isEmpty(queue)) {
        printf("Queue is empty! Cannot dequeue.\n");
        return -1; 
    } else {
        int value = queue->arr[queue->front];
        queue->front++;
        if (queue->front > queue->rear) {
            queue->front = queue->rear = -1;
        }
        return value;
    }
}

void display(struct Queue* queue) {
    if (isEmpty(queue)) {
        printf("Queue is empty! Nothing to display.\n");
    } else {
        printf("Queue elements are:\n");
        for (int i = queue->front; i <= queue->rear; i++) {
            printf("%d ", queue->arr[i]);
        }
        printf("\n");
    }
}

int main() {
    struct Queue queue;
    int value;

    initQueue(&queue);

    enqueue(&queue, 10);
    enqueue(&queue, 20);
    enqueue(&queue, 30);
    enqueue(&queue, 40);
    enqueue(&queue, 50);

    display(&queue);

    printf("Dequeued element: %d\n", dequeue(&queue));

    display(&queue);

    printf("Dequeued element: %d\n", dequeue(&queue));
    display(&queue);

    return 0;
}
```

Output:
![image](https://github.com/user-attachments/assets/eed97835-607c-46a5-a2dc-25dd98c149e7)



Result:
Thus, the function that deletes an element from a queue implemented using an array is verified successfully.
