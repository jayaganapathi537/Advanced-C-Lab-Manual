EXP NO:1 C PROGRAM FOR ARRAY OF STRUCTURE TO CHECK ELIGIBILITY FOR THE VACCINE.

Aim:
To write a C program for array of structure to check eligibility for the vaccine person age above 6 years of age.

Algorithm:
1.	Declare structure eligible with age (integer) and n (character array)
2.	Declare variable e of type eligible
3.	Input age and name using scanf, store in e
4.	If e.age <= 6
-	Print "Vaccine Eligibility: No"
Else
-	Print "Vaccine Eligibility: Yes"
5.	Print details (e.age, e.n)
6.	Return 0
 
Program:

```c
#include <stdio.h>
struct Person {
    char name[50];
    int age;
};

int main() {
    int n, i;
    printf("Enter the number of persons: ");
    scanf("%d", &n);
    struct Person persons[n];
    for (i = 0; i < n; i++) {
        printf("\nEnter details for person %d:\n", i + 1);
        printf("Name: ");
        scanf("%s", persons[i].name);
        printf("Age: ");
        scanf("%d", &persons[i].age);
    }
    printf("\nVaccine Eligibility List:\n");
    for (i = 0; i < n; i++) {
        if (persons[i].age > 6) {
            printf("%s is eligible for the vaccine.\n", persons[i].name);
        } else {
            printf("%s is NOT eligible for the vaccine.\n", persons[i].name);
        }
    }

    return 0;
}

```


Output:

![image](https://github.com/user-attachments/assets/3b359143-cb49-4d29-bec8-faa39a143579)



Result:
Thus, the program is verified successfully. 



EXP NO:2 C PROGRAM FOR PASSING STRUCTURES AS FUNCTION ARGUMENTS AND RETURNING A STRUCTURE FROM A FUNCTION
Aim:
To write a C program for passing structure as function and returning a structure from a function

Algorithm:
1.	Define structure numbers with members a and b.
2.	Declare variable n of type numbers.
3.	Prompt the user to enter values for a and b.
4.	Input values for a and b into n using scanf.
5.	Call the add function with n as an argument.
6.	Print the result returned by the add function.
7.	Return 0
 
Program:
```c
#include <stdio.h>
struct Person {
    char name[50];
    int age;
};
struct Person checkEligibility(struct Person p) {
    if (p.age > 6) {
        printf("%s is eligible for the vaccine.\n", p.name);
    } else {
        printf("%s is NOT eligible for the vaccine.\n", p.name);
    }
    return p;
}

int main() {
    struct Person person1;
    printf("Enter name: ");
    scanf("%s", person1.name);

    printf("Enter age: ");
    scanf("%d", &person1.age);
    struct Person result = checkEligibility(person1);
    printf("\nReturned details:\n");
    printf("Name: %s\n", result.name);
    printf("Age: %d\n", result.age);

    return 0;
}
```
Output:

![image](https://github.com/user-attachments/assets/b492759d-7be9-4dd9-a048-5e0bbf049b51)


Result:
Thus, the program is verified successfully


 
EXP.NO:3 C PROGRAM TO READ A FILE NAME FROM USER AND WRITE THAT FILE USING FOPEN()

Aim:
To write a C program to read a file name from user

Algorithm:
1.	Include the necessary header file stdio.h.
2.	Begin the main function.
3.	Declare a file pointer p.
Declare a character array name to store the file name.
4.	Prompt the user to enter a file name.
Use scanf to input the file name into the name array.
5.	Print a message indicating that the file with the specified name has been created successfully.
6.	Use fopen to open a file with the name provided by the user in write mode ("w").
-	If successful, continue to the next step.
-	If unsuccessful, print an error message and exit the program with a non-zero status.
1.	Print a message indicating that the file has been opened successfully.
2.	Use fclose to close the file.
3.	Print a message indicating that the file has been closed.
4.	End the main function.
5.	Return 0 to indicate successful program execution.
 
Program:
```c
#include <stdio.h>

int main() {
    char filename[100];
    printf("Enter the file name: ");
    scanf("%s", filename);
    printf("You entered: %s\n", filename);

    return 0;
}
```
Output:
![image](https://github.com/user-attachments/assets/a543561c-ecf6-4009-8255-063afb613760)






Result:
Thus, the program is verified successfully
 


EXP NO:4   PROGRAM TO READ A FILE NAME FROM USER, WRITE THAT FILE AND INSERT TEXT IN TO THAT FILE
Aim:
To write a C program to read, a file and insert text in that file
Algorithm:
1.	Include the necessary header file stdio.h.
2.	Begin the main function.
3.	Declare a file pointer p.
Declare character arrays name and text. Declare an integer variable num.
4.	Prompt the user to enter a file name and the number of strings.
Use scanf to input the file name into the name array and the number of strings into the num variable.
5.	Use fopen to open a file with the name provided by the user in write mode ("w").
-	If successful, continue to the next step.
-	If unsuccessful, print an error message and exit the program with a non-zero status.
6.	Print a message indicating that the file has been opened successfully.
1.	Use a loop to input strings from the user and write them to the file using fputs.
2.	Use fclose to close the file.
3.	Print a message indicating that data has been added successfully.
4.	End the main function.
5.	Return 0 to indicate successful program execution.
 
Program:
```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    FILE *file;
    char filename[100];
    char ch;
    char text[500];
    printf("Enter the file name: ");
    scanf("%s", filename);
    file = fopen(filename, "r");
    if (file == NULL) {
        printf("File does not exist or cannot be opened.\n");
        return 1;
    }
    printf("\nCurrent contents of the file:\n");
    while ((ch = fgetc(file)) != EOF) {
        putchar(ch);
    }
    fclose(file);
    file = fopen(filename, "a");
    if (file == NULL) {
        printf("Error opening file for appending.\n");
        return 1;
    }
    printf("\nEnter text to append to the file: ");
    getchar();
    fgets(text, sizeof(text), stdin);
    fputs(text, file);
    fclose(file);

    printf("Text appended successfully!\n");

    return 0;
}

```


Output:

![image](https://github.com/user-attachments/assets/1f90a1fe-d88d-4564-b7a9-ad9a18bf4322)




Result:
Thus, the program is verified successfully



Ex No 5 : C PROGRAM TO DISPLAY STUDENT DETAILS USING STRUCTURE

Aim:
The aim of this program is to dynamically allocate memory to store information about multiple subjects (name and marks), input the details for each subject, and then display the stored information. Finally, it frees the allocated memory to prevent memory leaks.

Algorithm:
1.Input the number of subjects.

2.Read the integer value n from the user, which represents the number of subjects.

3.Dynamically allocate memory:

4.Use malloc to allocate memory for n subjects. Each subject has a name (array of characters) and marks (integer).

5.If memory allocation fails (i.e., the pointer s is NULL), display an error message and exit the program.

6.Input the details of each subject

7.Use a for loop to read the name and marks of each subject using scanf. For each subject, store the name as a string and marks as an integer in the dynamically allocated memory.

8.Display the details of each subject

9.Use another for loop to print the name and marks of each subject.

10.Free the allocated memory

11.After all operations are done, call free(s) to release the dynamically allocated memory.

12.Return from the main function

13.End the program by returning 0.

Program:
```c
#include <stdio.h>
#include <stdlib.h>
struct Subject {
    char name[50];
    float marks;
};

int main() {
    struct Subject *subjects;
    int n, i;
    printf("Enter the number of subjects: ");
    scanf("%d", &n);
    subjects = (struct Subject *) malloc(n * sizeof(struct Subject));

    if (subjects == NULL) {
        printf("Memory allocation failed!\n");
        return 1;
    }
    for (i = 0; i < n; i++) {
        printf("\nEnter details for subject %d:\n", i + 1);
        printf("Name: ");
        scanf("%s", subjects[i].name);
        printf("Marks: ");
        scanf("%f", &subjects[i].marks);
    }
    printf("\nEntered Subject Details:\n");
    for (i = 0; i < n; i++) {
        printf("Subject %d: Name = %s, Marks = %.2f\n", i + 1, subjects[i].name, subjects[i].marks);
    }
    free(subjects);

    return 0;
}
```

Output:
![image](https://github.com/user-attachments/assets/7d541857-8b73-4cf5-8336-f12ce739e58f)






Result:
Thus, the program is verified successfully
