# EX-26-AREA-OF-RECTANGLE-USING- POINTER
## AIM
To write a C Program to find area of rectangle using pointer.

## ALGORITHM
1.	Start the program.
2.	Read two numbers.
3.	Calculate the area of rectangle using the formula area=(x)(*y)
4.	Display the result.
5.	Stop the program.

## PROGRAM
```c
#include <stdio.h>

int main() {
    float length, breadth, area;
    float *pLength, *pBreadth;
    pLength = &length;
    pBreadth = &breadth;
    printf("Enter the length of the rectangle: ");
    scanf("%f", pLength);
    printf("Enter the breadth of the rectangle: ");
    scanf("%f", pBreadth);
    area = (*pLength) * (*pBreadth);
    printf("Area of the rectangle = %.2f\n", area);
    return 0;
}
```
## OUTPUT
		       	
![image](https://github.com/user-attachments/assets/f1ebd429-15d1-4e90-8b8f-f8ac5eb5e193)


## RESULT
Thus the program to find area of rectangle using pointer has been executed successfully
 
 


# EX-27-DYNAMIC-MEMORY-ALLOCATION
## AIM
To write a C Program to print 'WELCOME' using malloc() and free().

## ALGORITHM
1.	Start the program.
2.	Read a string variable.
3.	Allocate memory using malloc().
4.	Display the string.
5.	Remove the allocated memory using free().
6.	Stop the program.

## PROGRAM
```c
#include <stdio.h>
#include <stdlib.h>
int main() {
    char *str;
    str = (char *)malloc(8 * sizeof(char));
    if (str == NULL) {
        printf("Memory allocation failed!\n");
        return 1;
    }
    str[0] = 'W';
    str[1] = 'E';
    str[2] = 'L';
    str[3] = 'C';
    str[4] = 'O';
    str[5] = 'M';
    str[6] = 'E';
    str[7] = '\0';
    printf("%s\n", str);
    free(str);
    return 0;
}
```
## OUTPUT


![image](https://github.com/user-attachments/assets/264f61ab-6b9f-4b64-83c0-9da6a48a6757)



## RESULT
Thus the program to print 'WELCOME' using malloc() and free() has been executed successfully.



# EX-28-STUDENT-INFORMATION-USING-STRUCTURE

## AIM

To write a C Program to store the student information and display it using structure.

## ALGORITHM

1.	Start the program.
2.	Create a student structure with name, roll number and marks as members.
3.	Using structure variable read the structure members and print them.
4.	Stop the program.

## PROGRAM
```c
#include <stdio.h>
struct Student {
    char name[50];
    int age;
    int rollNumber;
    float marks;
};
int main() {
    struct Student s;
    printf("Enter student name: ");
    fgets(s.name, sizeof(s.name), stdin);
    printf("Enter student age: ");
    scanf("%d", &s.age);
    printf("Enter student roll number: ");
    scanf("%d", &s.rollNumber);
    printf("Enter student marks: ");
    scanf("%f", &s.marks);
    printf("\n--- Student Details ---\n");
    printf("Name       : %s", s.name);
    printf("Age        : %d\n", s.age);
    printf("Roll Number: %d\n", s.rollNumber);
    printf("Marks      : %.2f\n", s.marks);
    return 0;
}
```

## OUTPUT
![image](https://github.com/user-attachments/assets/435e336d-ab94-4f4d-81e3-66c22941ec09)

## RESULT

Thus the program to store the student information and display it using structure has been executed successfully
 
 


# EX-29-EMPLOYEE-STRUCTURE-SALARY-CALCULATION

## AIM

To write a C Program to read and store the data of 3 employees and calculate their Gross Salary using the concept of structure.

## ALGORITHM

1.	Start the program.
2.	Create an employee structure with name, id and salary details as members.
3.	Using structure variable read the structure members.
4.	Calculate the gross salary and print the details.
5.	Stop the program.

## PROGRAM
```c
#include <stdio.h>
struct Employee {
    char name[50];
    int id;
    float basicSalary;
    float hra; 
    float da;  
    float grossSalary;
};

int main() {
    struct Employee emp[3]; 
    int i;
    for (i = 0; i < 3; i++) {
        printf("\nEnter details for Employee %d\n", i + 1);

        printf("Enter Name: ");
        scanf(" %[^\n]", emp[i].name); 

        printf("Enter ID: ");
        scanf("%d", &emp[i].id);

        printf("Enter Basic Salary: ");
        scanf("%f", &emp[i].basicSalary);

        printf("Enter HRA: ");
        scanf("%f", &emp[i].hra);

        printf("Enter DA: ");
        scanf("%f", &emp[i].da);

        emp[i].grossSalary = emp[i].basicSalary + emp[i].hra + emp[i].da;
    }

    printf("\n--- Employee Details ---\n");
    for (i = 0; i < 3; i++) {
        printf("\nEmployee %d\n", i + 1);
        printf("Name         : %s\n", emp[i].name);
        printf("ID           : %d\n", emp[i].id);
        printf("Basic Salary : %.2f\n", emp[i].basicSalary);
        printf("HRA          : %.2f\n", emp[i].hra);
        printf("DA           : %.2f\n", emp[i].da);
        printf("Gross Salary : %.2f\n", emp[i].grossSalary);
    }
    return 0;
}
```

 ## OUTPUT
![image](https://github.com/user-attachments/assets/526624dd-1b62-482b-be4e-452cb32fc853)
![image](https://github.com/user-attachments/assets/6e134af6-cba7-4438-bb85-46e6b6a4496c)

 

## RESULT

Thus the C program to read and store the data of 3 employees and calculate their Gross Salary using the concept of structure
 




# EX – 30 -STUDENTS MARK -TOTAL &AVERAGE USING STRUCURE

## AIM
Create a C program to calculate the total and average of student using structure.

## ALGORITHM 

Step 1: Start the program.

Step 2: Define a struct student with:
•	name: a character array (size 10) for the student's name (not used in the logic).
•	rollno: an integer for the student's roll number (also unused).
•	subject[5]: an array to store marks of 5 subjects.
•	total: an integer to store total marks.

Step 3: Declare an array s[2] of type struct student for 2 students. Also declare variables n, i, and j for input 
             and iteration.
	     
Step 4: Input Loop (i = 0 to 1):
•	Read an integer n (but it's not used later — possibly intended for roll number or placeholder).
•	Loop j = 0 to 4:
o	Read 5 subject marks into s[i].subject[j].

Step 5: Total Marks Calculation Loop (i = 0 to 1):
•	Initialize s[i].total to 0.
•	Loop j = 0 to 4:
o	Add each subject mark to s[i].total.

Step 6: Override Total (Hardcoded):
•	Set s[0].total = 374;
•	Set s[1].total = 383;
           This step overwrites the computed totals. It seems like testing or hardcoded totals — unnecessary if you’re 
                 already calculating them.
		 
Step 7: Output Loop (i = 0 to 1):
•	Print s[i].total for each student.

Step 8: End the program.

## PROGRAM
```c
#include <stdio.h>
struct Student {
    char name[50];
    int rollNumber;
    float marks[5]; 
    float total;
    float average;
};
int main() {
    struct Student s;
    int i;
    printf("Enter student name: ");
    fgets(s.name, sizeof(s.name), stdin);
    printf("Enter student roll number: ");
    scanf("%d", &s.rollNumber);
    printf("Enter marks for 5 subjects:\n");
    s.total = 0;
    for (i = 0; i < 5; i++) {
        printf("Subject %d: ", i + 1);
        scanf("%f", &s.marks[i]);
        s.total += s.marks[i];
    }
    s.average = s.total / 5;
    printf("\n--- Student Result ---\n");
    printf("Name        : %s", s.name);
    printf("Roll Number : %d\n", s.rollNumber);
    printf("Total Marks : %.2f\n", s.total);
    printf("Average Marks: %.2f\n", s.average);
    return 0;
}
```

## OUTPUT
![image](https://github.com/user-attachments/assets/b48116c7-a79a-47b0-8d0b-6e24eff3d30e)


 

## RESULT

Thus the C program to calculate the total and average of student using structure has been executed successfully.
	


