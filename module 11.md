

EXP NO:21 C PROGRAM TO CREATE A FUNCTION TO FIND THE GREATEST NUMBER
Aim:
To write a C program to create a function to find the greatest number

Algorithm:
1.	Include the necessary header #include <stdio.h>.
2.	Use a series of if and else if statements to compare the values and return the maximum among them.
3.	Declare variables n1, n2, n3, n4, and greater to store user input and the result.
4.	Use scanf to take four integers as input.
5.	Call the max_of_four function with the input integers and store the result in the greater variable
 
Program:
```c
 #include <stdio.h>

int findGreatest(int arr[], int size) {
    int greatest = arr[0]; 
    
    for (int i = 1; i < size; i++) {
        if (arr[i] > greatest) {
            greatest = arr[i];
        }
    }
    return greatest;
}

int main() {
    int n;
    
    printf("Enter the number of elements: ");
    scanf("%d", &n);

    int arr[n];
    printf("Enter %d elements:\n", n);
    for (int i = 0; i < n; i++) {
        scanf("%d", &arr[i]);
    }

    int greatest = findGreatest(arr, n);

    printf("The greatest number is: %d\n", greatest);

    return 0;
}
```
Output:![image](https://github.com/user-attachments/assets/44e1c379-8951-495a-8120-0380c1c1c324)

Result:
Thus, the program  that create a function to find the greatest number is verified successfully.


 
EXP NO:22 C PROGRAM TO PRINT THE MAXIMUM VALUES FOR THE AND, OR AND  XOR COMPARISONS
Aim:
To write a C program to print the maximum values for the AND, OR and XOR comparisons

Algorithm:
1.	Define a function calculate_the_max that takes two integers n and k as parameters.
2.	Declare variables a, o, and x to store the maximum values for AND, OR, and XOR operations, respectively.
3.	Use nested loops to iterate through pairs of integers (i, j) from 1 to n.
4.	Within the loops, check conditions for AND, OR, and XOR operations and update the corresponding maximum values (a, o, x).
5.	Declare variables n and k to store user input.
6.	Use scanf to take two integers as input.
7.	Call the calculate_the_max function with input values.
 
Program:
```c
#include <stdio.h>
int maxAND(int arr[], int size) {
    int max = arr[0] & arr[1];
    for (int i = 0; i < size; i++) {
        for (int j = i + 1; j < size; j++) {
            int and_value = arr[i] & arr[j];
            if (and_value > max) {
                max = and_value;
            }
        }
    }
    return max;
}
int maxOR(int arr[], int size) {
    int max = arr[0] | arr[1];
    for (int i = 0; i < size; i++) {
        for (int j = i + 1; j < size; j++) {
            int or_value = arr[i] | arr[j];
            if (or_value > max) {
                max = or_value;
            }
        }
    }
    return max;
}

int maxXOR(int arr[], int size) {
    int max = arr[0] ^ arr[1];
    for (int i = 0; i < size; i++) {
        for (int j = i + 1; j < size; j++) {
            int xor_value = arr[i] ^ arr[j];
            if (xor_value > max) {
                max = xor_value;
            }
        }
    }
    return max;
}

int main() {
    int n;

    scanf("%d", &n);

    int arr[n];
    printf("Enter %d elements:\n", n);
    for (int i = 0; i < n; i++) {
        scanf("%d", &arr[i]);
    }
    int andMax = maxAND(arr, n);
    int orMax = maxOR(arr, n);
    int xorMax = maxXOR(arr, n);
    printf("Maximum AND value: %d\n", andMax);
    printf("Maximum OR value: %d\n", orMax);
    printf("Maximum XOR value: %d\n", xorMax);

    return 0;
}
```

Output:![image](https://github.com/user-attachments/assets/6c2fc401-452f-4933-b6f8-996c29d2b75f)


Result:
Thus, the program to print the maximum values for the AND, OR and XOR comparisons
is verified successfully.


 
EXP NO:23 C PROGRAM TO WRITE THE LOGIC FOR THE REQUESTS
Aim:
To write a C program to write the logic for the requests

Algorithm:
1.	Declare variables noshel and noque to store the number of shelves and the number of queries, respectively.
2.	Use scanf to take two integers as input for the number of shelves and queries.
3.	Declare a 2D array shelarr to represent shelves and books, and an array nobookarr to store the number of books on each shelf.
4.	Declare variables k and c to keep track of the book index and the total number of books.
5.	Use a for loop to iterate over the queries.
 
Program: 
```c
#include <stdio.h>

int main() {
    int noshel, noque;  
    int k, c;         
    printf("Enter the number of shelves: ");
    scanf("%d", &noshel);
    printf("Enter the number of queries: ");
    scanf("%d", &noque);

    int shelarr[noshel][100]; 
    int nobookarr[noshel]; 
    for (int i = 0; i < noshel; i++) {
        nobookarr[i] = 0;  
    }

    for (int i = 0; i < noshel; i++) {
        printf("Enter the number of books on shelf %d: ", i + 1);
        scanf("%d", &nobookarr[i]);

        printf("Enter the books on shelf %d: ", i + 1);
        for (int j = 0; j < nobookarr[i]; j++) {
            scanf("%d", &shelarr[i][j]);
        }
    }

    for (int q = 0; q < noque; q++) {
        int query_type, shelf_num, book_num;
        printf("Enter query type (1: Search, 2: Add, 3: Remove): ");
        scanf("%d", &query_type);

        switch(query_type) {
            case 1: 
                printf("Enter shelf number to search (1 to %d): ", noshel);
                scanf("%d", &shelf_num);
                printf("Enter book number to search on shelf %d: ", shelf_num);
                scanf("%d", &book_num);
                int found = 0;
                for (int i = 0; i < nobookarr[shelf_num - 1]; i++) {
                    if (shelarr[shelf_num - 1][i] == book_num) {
                        printf("Book %d found on shelf %d\n", book_num, shelf_num);
                        found = 1;
                        break;
                    }
                }
                if (!found) {
                    printf("Book %d not found on shelf %d\n", book_num, shelf_num);
                }
                break;

            case 2:
                printf("Enter shelf number to add a book to (1 to %d): ", noshel);
                scanf("%d", &shelf_num);
                printf("Enter book number to add on shelf %d: ", shelf_num);
                scanf("%d", &book_num);

                shelarr[shelf_num - 1][nobookarr[shelf_num - 1]] = book_num; 
                nobookarr[shelf_num - 1]++; 
                printf("Book %d added to shelf %d\n", book_num, shelf_num);
                break;

            case 3:
                printf("Enter shelf number to remove a book from (1 to %d): ", noshel);
                scanf("%d", &shelf_num);
                printf("Enter book number to remove on shelf %d: ", shelf_num);
                scanf("%d", &book_num);

                int removed = 0;
                for (int i = 0; i < nobookarr[shelf_num - 1]; i++) {
                    if (shelarr[shelf_num - 1][i] == book_num) {
                        for (int j = i; j < nobookarr[shelf_num - 1] - 1; j++) {
                            shelarr[shelf_num - 1][j] = shelarr[shelf_num - 1][j + 1];
                        }
                        nobookarr[shelf_num - 1]--; 
                        printf("Book %d removed from shelf %d\n", book_num, shelf_num);
                        removed = 1;
                        break;
                    }
                }
                if (!removed) {
                    printf("Book %d not found on shelf %d\n", book_num, shelf_num);
                }
                break;

            default:
                printf("Invalid query type\n");
                break;
        }
    }

    return 0;
}
``` 

Output:
![image](https://github.com/user-attachments/assets/287efada-53c4-4bd5-b65b-a966a31b0f79)



Result:
Thus, the program to write the logic for the requests is verified successfully.


 
EXP NO:24 C PROGRAM PRINT THE SUM OF THE INTEGERS IN THE ARRAY.
Aim:
To write a C program print the sum of the integers in the array.

Algorithm:
1.	Declare a variable n to store the number of integers.
2.	Use scanf to take an integer n as input.
3.	Declare an array a of size n to store the integers.
4.	Declare a variable sum and initialize it to zero.
5.	Use a for loop to iterate n times:
6.	Use scanf to input each integer and add it to the sum.
7.	Print the final sum using printf.



Program:
```c
#include <stdio.h>

int main() {
    int n, sum = 0;

    printf("Enter the number of elements in the array: ");
    scanf("%d", &n);

    int arr[n]; 
    printf("Enter %d integers:\n", n);
    for (int i = 0; i < n; i++) {
        scanf("%d", &arr[i]);
    }

    for (int i = 0; i < n; i++) {
        sum += arr[i];
    }

    printf("The sum of the integers in the array is: %d\n", sum);

    return 0;
}
```
Output:
![image](https://github.com/user-attachments/assets/067cf548-0e4f-462a-935a-b9356aea285f)

Result:
Thus, the program prints the sum of the integers in the array is verified successfully.


 
EXP NO 25: C PROGRAM TO COUNT THE NUMBER OF WORDS IN A      SENTENCE



Aim:

To write a C program that counts the number of words in a given sentence.

Algorithm:

1.	Input the sentence: Take a sentence from the user.
2.	Initialize a counter variable: This will keep track of the number of words.
3.	Process each character of the sentence:
o	Iterate through the sentence, checking each character.
o	If a character is not a space, it may belong to a word. If it's the first non-space character after a space or at the start, increment the word count.
4.	Handle spaces and punctuation: Skip over spaces, punctuation marks, and consider each word as a sequence of characters separated by spaces.
5.	Display the result: After processing the sentence, output the total word count.



Program:
```c
#include <stdio.h>
#include <ctype.h>

int countWords(char *str) {
    int count = 0;
    int inWord = 0;

    while (*str) {
        if (isspace(*str)) {
            inWord = 0;
        } else if (!inWord) {
            inWord = 1;
            count++;
        }
        str++;
    }

    return count;
}

int main() {
    char sentence[1000];

    printf("Enter a sentence: ");
    fgets(sentence, sizeof(sentence), stdin); 

    int wordCount = countWords(sentence);
    printf("Number of words in the sentence: %d\n", wordCount);

    return 0;
}
```
Output:![image](https://github.com/user-attachments/assets/5fefa14a-c65b-41a7-b711-65365128b945)


Result:

Thus, the program that counts the number of words in a given sentence is verified 
successfully.
