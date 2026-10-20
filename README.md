# Student-Management-System
A simple Student Management Record system developed using C language for my PPS project. It stores student name, present year, roll number, department, section, marks, grade, and CGPA.


here is my code

#include <stdio.h>

struct Student
{
    char name[50];
    int year, rollno, marks;
    char department[30], section[10], grade[5];
    float cgpa;
};

void main()
{
    struct Student s[100];
    int n = 0, choice, i;

    do
    {
        printf("\n1. Add Student");
        printf("\n2. Display Students");
        printf("\n3. Exit");
        printf("\nEnter your choice: ");
        scanf("%d", &choice);

        switch (choice)
        {
            case 1:
                printf("Enter number of students: ");
                scanf("%d", &n);

                for (i = 0; i < n; i++)
                {
                    printf("\nEnter details of student %d\n", i + 1);

                    printf("Name: ");
                    scanf(" %[^\n]", s[i].name);

                    printf("Present Year: ");
                    scanf("%d", &s[i].year);

                    printf("Roll No: ");
                    scanf("%d", &s[i].rollno);

                    printf("Department: ");
                    scanf(" %[^\n]", s[i].department);

                    printf("Section: ");
                    scanf("%s", s[i].section);

                    printf("Marks: ");
                    scanf("%d", &s[i].marks);

                    printf("Grade: ");
                    scanf("%s", s[i].grade);

                    printf("CGPA: ");
                    scanf("%f", &s[i].cgpa);
                }
                break;

            case 2:
                for (i = 0; i < n; i++)
                {
                    printf("\nStudent %d Details\n", i + 1);
                    printf("Name: %s\n", s[i].name);
                    printf("Present Year: %d\n", s[i].year);
                    printf("Roll No: %d\n", s[i].rollno);
                    printf("Department: %s\n", s[i].department);
                    printf("Section: %s\n", s[i].section);
                    printf("Marks: %d\n", s[i].marks);
                    printf("Grade: %s\n", s[i].grade);
                    printf("CGPA: %.2f\n", s[i].cgpa);
                }
                break;

            case 3:
                printf("Thank you!");
                break;

            default:
                printf("Invalid choice!");
        }

    } while (choice != 3);
}
