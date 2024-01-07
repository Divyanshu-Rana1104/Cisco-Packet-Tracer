#include <stdio.h>
#include <ctype.h>
int main()
{
 // Input
 char inputChar;
 printf("Enter a character: ");
 scanf("%c", &inputChar);
 // Check if it's an alphabet, digit, or special symbol
 if (isalpha(inputChar)) {
 printf("The input character is an alphabet.\n");
 } else if (isdigit(inputChar)) {
 printf("The input character is a digit.\n");
 } else {
 printf("The input character is a special symbol.\n");
 }
 return 0;
}
OUTPUT
CODE
#include <stdio.h>
int main() {
 double side1, side2, side3;
 // Input the lengths of the three sides
 printf("Enter the length of side 1: ");
 scanf("%lf", &side1);
 
 printf("Enter the length of side 2: ");
 scanf("%lf", &side2);
 
 printf("Enter the length of side 3: ");
 scanf("%lf", &side3);
 // Check if it forms a valid triangle
 if (side1 + side2 > side3 && side1 + side3 > side2 && side2 + side3 > side1) {
 printf("The given sides form a valid triangle.\n");
 // Check the type of triangle
 if (side1 == side2 && side2 == side3) {
 printf("It is an equilateral triangle.\n");
 } else if (side1 == side2 || side1 == side3 || side2 == side3) {
 printf("It is an isosceles triangle.\n");
 } else {
 printf("It is a scalene triangle.\n");
 }
 } else {
 printf("The given sides do not form a valid triangle.\n");
 }
 return 0;
}
OUTPUT
CODE
#include <stdio.h>
int main() {
 int marks1, marks2, marks3, marks4, marks5;
 float percentage;
 int semesterFee = 125000;
 float scholarship = 0;
 float netAmountPayable;
 char grade;
 // Input marks for each subject
 printf("Enter marks for subject 1: ");
 scanf("%d", &marks1);
 printf("Enter marks for subject 2: ");
 scanf("%d", &marks2);
 printf("Enter marks for subject 3: ");
 scanf("%d", &marks3);
 printf("Enter marks for subject 4: ");
 scanf("%d", &marks4);
 printf("Enter marks for subject 5: ");
 scanf("%d", &marks5);
 // Calculate the percentage
 int totalMarks = marks1 + marks2 + marks3 + marks4 + marks5;
 percentage = (float)totalMarks / 5.0;
 // Determine the scholarship based on the percentage
 if (percentage < 50) {
 scholarship = 0;
 } else if (percentage >= 51 && percentage <= 60) {
 scholarship = 0.05 * semesterFee;
 } else if (percentage >= 61 && percentage <= 74) {
 scholarship = 0.20 * semesterFee;
 } else if (percentage >= 75 && percentage <= 84) {
 scholarship = 0.30 * semesterFee;
 } else {
 scholarship = 0.50 * semesterFee;
 }
 // Calculate the net amount payable
 netAmountPayable = semesterFee - scholarship;
 // Determine the grade
 if (percentage >= 85) {
 grade = 'A';
 } else if (percentage >= 75) {
 grade = 'B';
 } else if (percentage >= 60) {
 grade = 'C';
 } else if (percentage >= 50) {
 grade = 'D';
 } else {
 grade = 'F';
 }
 // Display the results
 printf("Percentage: %.2f%%\n", percentage);
 printf("Scholarship amount: Rs. %.2f\n", scholarship);
 printf("Net amount payable: Rs. %.2f\n", netAmountPayable);
 printf("Grade: %c\n", grade);
 return 0;
}
OUTPUT
CODE
#include <stdio.h>
int main() {
 int year;
 // Input the year
 printf("Enter a year: ");
 scanf("%d", &year);
 // Check if it's a leap year
 if ((year % 4 == 0 && year % 100 != 0) || (year % 400 == 0)) {
 printf("%d is a leap year.\n", year);
 } else {
 printf("%d is not a leap year.\n", year);
 }
 return 0;
}
OUTPUT
CODE
#include <stdio.h>
int main() {
 int n;
 int count = 0;
 int num = 0;
 // Input the value of 'n'
 printf("Enter the value of n: ");
 scanf("%d", &n);
 // Print the first 'n' palindrome numbers
 printf("First %d palindrome numbers are:\n", n);
 while (count < n) {
 int originalNum = num;
 int reversedNum = 0;
 // Reverse the number
 while (num > 0) {
 int remainder = num % 10;
 reversedNum = reversedNum * 10 + remainder;
 num /= 10;
 }
 // Check if it's a palindrome
 if (originalNum == reversedNum) {
 printf("%d ", originalNum);
 count++;
 }
 num = originalNum + 1; // Move to the next number
 }
 printf("\n");
 return 0;
}
OUTPUT
CODE
#include <stdio.h>
#include <string.h>
int main() {
 int decimalNumber;
 // Input the decimal number
 printf("Enter a decimal number: ");
 scanf("%d", &decimalNumber);
 // Convert to binary
 int binaryNumber = 0;
 int base = 1;
 int temp = decimalNumber;
 while (temp > 0) {
 int remainder = temp % 2;
 binaryNumber = binaryNumber + remainder * base;
 temp = temp / 2;
 base = base * 10;
 }
 // Convert to octal
 int octalNumber = 0;
 base = 1;
 temp = decimalNumber;
 while (temp > 0) {
 int remainder = temp % 8;
 octalNumber = octalNumber + remainder * base;
 temp = temp / 8;
 base = base * 10;
 }
 // Convert to hexadecimal
 char hexadecimalNumber[100];
 int index = 0;
 temp = decimalNumber;
 while (temp > 0) {
 int remainder = temp % 16;
 if (remainder < 10) {
 hexadecimalNumber[index] = remainder + '0';
 } else {
 hexadecimalNumber[index] = remainder - 10 + 'A';
 }
 temp = temp / 16;
 index++;
 }
 hexadecimalNumber[index] = '\0';
 // Reverse the hexadecimal string manually
 int start = 0;
 int end = strlen(hexadecimalNumber) - 1;
 while (start < end) {
 char tempChar = hexadecimalNumber[start];
 hexadecimalNumber[start] = hexadecimalNumber[end];
 hexadecimalNumber[end] = tempChar;
 start++;
 end--;
 }
 // Display the results
 printf("Binary: %d\n", binaryNumber);
 printf("Octal: %d\n", octalNumber);
 printf("Hexadecimal: %s\n", hexadecimalNumber);
 return 0;
}
 
OUTPUT
CODE
#include <stdio.h>
int main() {
 int number, digit;
 // Input the number
 printf("Enter any number: ");
 scanf("%d", &number);
 // Handle the case of a single '0'
 if (number == 0) {
 printf("Zero\n");
 return 0;
 }
 // Print the digits of the number in words
 printf("In words: ");
 int reverse = 0;
 while (number > 0) {
 digit = number % 10;
 reverse = reverse * 10 + digit;
 number /= 10;
 }
 while (reverse > 0) {
 digit = reverse % 10;
 switch (digit) {
 case 0:
 printf("Zero ");
 break;
 case 1:
 printf("One ");
 break;
 case 2:
 printf("Two ");
 break;
 case 3:
 printf("Three ");
 break;
 case 4:
 printf("Four ");
 break;
 case 5:
 printf("Five ");
 break;
 case 6:
 printf("Six ");
 break;
 case 7:
 printf("Seven ");
 break;
 case 8:
 printf("Eight ");
 break;
 case 9:
 printf("Nine ");
 break;
 default:
 printf("Invalid Input");
 }
 reverse /= 10;
 }
 printf("\n");
 return 0;
} 
OUTPUT
CODE
#include <stdio.h>
#include <math.h>
int main() {
 int n;
 double sum = 1, term = 0, fact=1;
 // Input the value of 'n'
 printf("Enter the value of n: ");
 scanf("%d", &n);
 for (int i = 2; i <= n; i++) {
 term =pow(i,i);
 fact*=i;
 sum += (term/fact);
 }
 printf("Sum of the series: %.2lf\n", sum);
 return 0;
}
OUTPUT
CODE
#include <stdio.h>
#include <math.h>
int main() {
 int n;
 double sum = 1, term = 0, fact=1;
 // Input the value of 'n'
 printf("Enter the value of n: ");
 scanf("%d", &n);
 for (int i = 2; i <= n; i++) {
 term =pow(i,i-1);
 fact*=i;
 sum += (term/fact);
 }
 printf("Sum of the series: %.2lf\n", sum);
 return 0;
}
OUTPUT
CODE
#include <stdio.h>
int main() {
 int n;
 int sum = 1, fact = 1;
 // Input the value of 'n'
 printf("Enter the value of n: ");
 scanf("%d", &n);
 for (int i = 2; i <= n; i++) {
 fact *= i;
 if (i % 2 == 0)
 sum -= fact;
 else
 sum += fact;
 }
 printf("Sum of the series: %d\n", sum);
 return 0;
}
OUTPUT
CODE
#include <stdio.h>
int main() {
 int num1, num2;
 // Input two numbers
 printf("Enter two numbers: ");
 scanf("%d %d", &num1, &num2);
 int a = num1, b = num2;
 int temp;
 // Find the HCF (GCD) using Euclidean algorithm
 while (b != 0) {
 temp = b;
 b = a % b;
 a = temp;
 }
 int hcf = a;
 int lcm = (num1 * num2) / hcf;
 // Display the results
 printf("HCF (GCD) of %d and %d is: %d\n", num1, num2, hcf);
 printf("LCM of %d and %d is: %d\n", num1, num2, lcm);
 return 0;
}
OUTPUT
CODE
#include <stdio.h>
int main() {
 int n;
 printf("enter no
\n");
 scanf("%d",&n);
 for(int i=1;i<=n;i++)
 
{
 for(int k=n;k>=i;k--
)
 printf(" ");
 for(int j=1;j<=i;j++)
 printf("%d",j);
 
 for(int l=1;l<i;l++)
 printf("%d",l);
 
 printf("
\n");
 
}
 for(int i=n
-1;i>=1;i--
)
 
{
 for(int k=n;k>=i;k--
)
 printf(" ");
 for(int j=1;j<=i;j++)
 printf("%d",j);
 
 for(int l=i
-1;l>=1;l--
)
 printf("%d",l);
 
 printf("
\n");
 
}
 return 0; }
OUTPUT
 
CODE
#include<stdio.h>
int main() {
 int n,a=0;
 printf("enter no
\n");
 scanf("%d",&n);
 a=n+64;
 for(int i=a;i>=65;i--
)
 
{
 for(int k=65;k<=i;k++)
 printf(" ");
 
 for(int j=a;j>=i;j--
)
 printf("%c",(char)j);
 for(int l=i+1;l<=a;l++)
 printf("%c",(char)l);
 
 printf("
\n");
 
}
 for(int i=66;i<=a;i++)
 
{
 for(int k=65;k<=i;k++)
 printf(" ");
 
 for(int j=a;j>=i;j--
)
 printf("%c",(char)j);
 for(int l=i+1;l<=a;l++)
 printf("%c",(char)l);
 printf("
\n");
 
}
 return 0; }
OUTPUT
 
CODE
#include <stdio.h>
int main() {
 int hour1, minute1, second1;
 int hour2, minute2, second2;
 int sh, sm, ss;
 printf("Enter the first time (HH:MM:SS): ");
 scanf("%d %d %d", &hour1, &minute1, &second1);
 printf("Enter the second time (HH:MM:SS): ");
 scanf("%d %d %d", &hour2, &minute2, &second2);
 ss=(second1 + second2)%60;
 int carry1=(second1+second2)/60;
 
 sm=(minute1 + minute2+carry1)%60;
 int carry2=(minute1+minute2)/60;
 
 sh=(hour1 + hour2 +carry2);
 printf("First time: %02d:%02d:%02d\n", hour1, minute1, second1);
 printf("Second time: %02d:%02d:%02d\n", hour2, minute2, second2);
 printf("Added time: %02d:%02d:%02d\n", sh, sm, ss);
 return 0;
}
OUTPUT
CODE
#include <stdio.h>
// Function to rearrange the array
void rearrangeArray(int arr[], int n) 
{
 for (int i = 0; i < n - 1; i++) {
 for (int j = 0; j < n - i - 1; j++) {
 if (arr[j] > arr[j + 1]) {
 // Swap arr[j] and arr[j + 1]
 int temp = arr[j];
 arr[j] = arr[j + 1];
 arr[j + 1] = temp;
 }
 }
 }
 // Rearrange the sorted array in the specified order
 int temp[n];
 int small = 0, large = n - 1;
 for (int i = 0; i < n; i++) {
 if (i % 2 == 0)
 temp[i] = arr[small++];
 else
 temp[i] = arr[large--];
 }
 // Copy rearranged elements back to the original array
 for (int i = 0; i < n; i++)
 arr[i] = temp[i];
}
// Function to print an array
void printArray(int arr[], int size) {
 for (int i = 0; i < size; i++)
 printf("%d ", arr[i]);
 printf("\n");
}
int main() {
 int arr[] = {5, 8, 1, 4, 2, 9, 3, 7, 6};
 int n = sizeof(arr) / sizeof(arr[0]);
 printf("Original array: ");
 printArray(arr, n);
 rearrangeArray(arr, n);
 printf("Rearranged array: ");
 printArray(arr, n);
 return 0;
}
OUTPUT
CODE
#include <stdio.h>
// Function to check if a matrix is an identity matrix
int isIdentityMatrix(int mat[10][10], int rows, int cols) {
 if (rows != cols) {
 // If the number of rows is not equal to the number of columns, it cannot be an identity matrix
 return 0;
 }
 for (int i = 0; i < rows; i++) {
 for (int j = 0; j < cols; j++) {
 if (i == j && mat[i][j] != 1) {
 // Diagonal elements must be 1
 return 0;
 } else if (i != j && mat[i][j] != 0) {
 // Non-diagonal elements must be 0
 return 0;
 }
 }
 }
 // If all conditions are satisfied, it is an identity matrix
 return 1;
}
// Driver program to test the function
int main() {
 int rows, cols;
 // Get the dimensions of the matrix from the user
 printf("Enter the number of rows and columns (up to 10): ");
 scanf("%d %d", &rows, &cols);
 int mat[10][10];
 // Get the matrix elements from the user
 printf("Enter the elements of the matrix:\n");
 for (int i = 0; i < rows; i++) {
 for (int j = 0; j < cols; j++) {
 scanf("%d", &mat[i][j]);
 }
 }
 // Check if the matrix is an identity matrix and display the result
 if (isIdentityMatrix(mat, rows, cols)) {
 printf("The given matrix is an identity matrix.\n");
 } else {
 printf("The given matrix is not an identity matrix.\n");
 }
 return 0;
}
OUTPUT
CODE
#include <stdio.h>
// Function to take input for a matrix
void inputMatrix(int mat[10][10], int rows, int cols) {
 printf("Enter the elements of the matrix:\n");
 for (int i = 0; i < rows; i++) {
 for (int j = 0; j < cols; j++) {
 printf("Enter element at position (%d, %d): ", i + 1, j + 1);
 scanf("%d", &mat[i][j]);
 }
 }
}
// Function to print a matrix
void printMatrix(int mat[10][10], int rows, int cols) {
 for (int i = 0; i < rows; i++) {
 for (int j = 0; j < cols; j++) {
 printf("%d\t", mat[i][j]);
 }
 printf("\n");
 }
}
// Function to perform matrix multiplication
void multiplyMatrices(int mat1[10][10], int mat2[10][10], int result[10][10], int rows1, int cols1, int rows2, 
int cols2) {
 if (cols1 != rows2) {
 printf("Matrix multiplication is not possible.\n");
 return;
 }
 // Initialize the result matrix with zeros
 for (int i = 0; i < rows1; i++) {
 for (int j = 0; j < cols2; j++) {
 result[i][j] = 0;
 }
 }
 // Perform matrix multiplication
 for (int i = 0; i < rows1; i++) {
 for (int j = 0; j < cols2; j++) {
 for (int k = 0; k < cols1; k++) {
 result[i][j] += mat1[i][k] * mat2[k][j];
 }
 }
 }
}
// Function to calculate the transpose of a matrix
void transposeMatrix(int mat[10][10], int transposed[10][10], int rows, int cols) {
 for (int i = 0; i < rows; i++) {
 for (int j = 0; j < cols; j++) {
 transposed[j][i] = mat[i][j];
 }
 }
}
int main() {
 int mat1[10][10], mat2[10][10], result[10][10], transposedResult[10][10];
 int rows1, cols1, rows2, cols2;
 // Input for the first matrix
 printf("Enter the number of rows and columns for the first matrix: ");
 scanf("%d %d", &rows1, &cols1);
 inputMatrix(mat1, rows1, cols1);
 // Input for the second matrix
 printf("Enter the number of rows and columns for the second matrix: ");
 scanf("%d %d", &rows2, &cols2);
 inputMatrix(mat2, rows2, cols2);
 // Perform matrix multiplication and display result
 multiplyMatrices(mat1, mat2, result, rows1, cols1, rows2, cols2);
 printf("\nMatrix Multiplication Result:\n");
 printMatrix(result, rows1, cols2);
 // Calculate and display the transpose of the resultant matrix
 transposeMatrix(result, transposedResult, rows1, cols2);
 printf("\nTranspose of Resultant Matrix:\n");
 printMatrix(transposedResult, cols2, rows1);
 return 0;
}
OUTPUT
CODE
#include <stdio.h>
void printFrequency(int arr[], int n) {
 printf("Occurrence of each number are:\n");
 for (int i = 0; i < n; i++) {
 int count = 1;
 // Skip if the element is already processed
 if (arr[i] == -1) {
 continue;
 }
 for (int j = i + 1; j < n; j++) {
 if (arr[i] == arr[j]) {
 count++;
 arr[j] = -1; // Mark the element as visited
 }
 }
 printf("%d : %d\n", arr[i], count);
 }
}
int main() {
 int A[] = {2, 3, 4, 5, 4, 3, 1, 7, 8, 9, 8, 5, 1, 4, 5};
 int n = sizeof(A) / sizeof(A[0]);
 printFrequency(A, n);
 return 0;
}
OUTPUT
CODE
#include <stdio.h>
// Function to sort an array using insertion sort
void insertionSort(int arr[], int n) {
 int i, key, j;
 for (i = 1; i < n; i++) {
 key = arr[i];
 j = i - 1;
 while (j >= 0 && arr[j] > key) {
 arr[j + 1] = arr[j];
 j = j - 1;
 }
 arr[j + 1] = key;
 }
}
void printArray(int arr[], int n) {
 int i;
 for (i = 0; i < n; i++)
 printf("%d ", arr[i]);
 printf("\n");
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
 insertionSort(arr, n);
 printf("Sorted array: ");
 printArray(arr, n);
 return 0;
}
OUTPUT
CODE
#include <stdio.h>
// Function to perform binary search
int binarySearch(int arr[], int low, int high, int target) {
 while (low <= high) {
 int mid = low + (high - low) / 2;
 // Check if the target is present at the middle
 if (arr[mid] == target)
 return mid;
 // If target is greater, ignore the left half
 if (arr[mid] < target)
 low = mid + 1;
 // If target is smaller, ignore the right half
 else
 high = mid - 1;
 }
 // Target is not present in the array
 return -1;
}
int main() {
 int n;
 printf("Enter the number of elements: ");
 scanf("%d", &n);
 int arr[n];
 printf("Enter %d sorted elements:\n", n);
 for (int i = 0; i < n; i++) {
 scanf("%d", &arr[i]);
 }
 int target;
 printf("Enter the element to search: ");
 scanf("%d", &target);
 // Perform binary search
 int result = binarySearch(arr, 0, n - 1, target);
 if (result != -1)
 printf("Element found at position %d\n", result+1);
 else
 printf("Element not found in the array\n");
 return 0;
}
OUTPUT
CODE
#include <stdio.h>
#include <string.h>
int lengthOfLongestSubstring(char *s) {
 int n = strlen(s);
 int maxLength = 0; // Length of the longest substring
 int start = 0; // Start index of the current substring
 // Array to store the last index of each character in the string
 int lastIndex[256];
 memset(lastIndex, -1, sizeof(lastIndex));
 for (int end = 0; end < n; end++) {
 // If the current character is already present in the substring,
 // update the start index to the next position of the repeating character
 if (lastIndex[s[end]] != -1) {
 start = (lastIndex[s[end]] > start) ? lastIndex[s[end]] + 1 : start;
 }
 // Update the last index of the current character
 lastIndex[s[end]] = end;
 // Update the maximum length if the current substring is longer
 maxLength = (end - start + 1 > maxLength) ? (end - start + 1) : maxLength;
 }
 return maxLength;
}
int main() {
 char inputString[] = "xyzwwepppw";
 int result = lengthOfLongestSubstring(inputString);
 printf("Input string: \"%s\"\n", inputString);
 printf("Length of the longest substring without repeating characters: %d\n", result);
 return 0;
}
OUTPUT
CODE
#include <stdio.h>
// Define the Employee structure
struct Employee {
 char name[50];
 char department[50];
 int eid;
 float salary;
};
int main() {
 int N;
 // Input the number of employees
 printf("Enter the number of employees: ");
 scanf("%d", &N);
 // Declare an array of Employee structures
 struct Employee employees[N];
 // Input records for N employees
 for (int i = 0; i < N; i++) {
 printf("\nEnter details for Employee %d:\n", i + 1);
 printf("Name: ");
 scanf("%s", employees[i].name);
 printf("Department: ");
 scanf("%s", employees[i].department);
 printf("Employee ID: ");
 scanf("%d", &employees[i].eid);
 printf("Salary: ");
 scanf("%f", &employees[i].salary);
 }
 // Display records of all employees using structure pointer
 printf("\nEmployee Records:\n");
 for (int i = 0; i < N; i++) {
 struct Employee *ptr = &employees[i];
 printf("\nEmployee %d:\n", i + 1);
 printf("Name: %s\n", ptr->name);
 printf("Department: %s\n", ptr->department);
 printf("Employee ID: %d\n", ptr->eid);
 printf("Salary: %.2f\n", ptr->salary);
 }
 return 0;
}
OUTPUT
CODE
#include <stdio.h>
#include <string.h>
// Define the Student structure
struct Student {
 char name[50];
 int rollNumber;
 float marks;
};
// Function to display the menu
void displayMenu() {
 printf("\nMenu:\n");
 printf("1. Insert Student\n");
 printf("2. Display Students\n");
 printf("3. Delete Student\n");
 printf("4. Search Student\n");
 printf("5. Exit\n");
}
// Function to insert a student record
void insertStudent(struct Student students[], int *count) {
 printf("Enter Student Details:\n");
 printf("Name: ");
 scanf("%s", students[*count].name);
 printf("Roll Number: ");
 scanf("%d", &students[*count].rollNumber);
 printf("Marks: ");
 scanf("%f", &students[*count].marks);
 
 (*count)++;
 printf("Student inserted successfully.\n");
}
// Function to display all student records
void displayStudents(struct Student students[], int count) {
 if (count == 0) {
 printf("No students to display.\n");
 return;
 }
 printf("\nStudent Records:\n");
 for (int i = 0; i < count; i++) {
 printf("Name: %s | Roll Number: %d | Marks: %.2f\n", students[i].name, students[i].rollNumber, 
students[i].marks);
 }
}
// Function to delete a student record
void deleteStudent(struct Student students[], int *count, int rollNumber) {
 int found = 0;
 for (int i = 0; i < *count; i++) {
 if (students[i].rollNumber == rollNumber) {
 // Replace the found student with the last student in the array
 students[i] = students[*count - 1];
 (*count)--;
 found = 1;
 printf("Student with Roll Number %d deleted successfully.\n", rollNumber);
 break;
 }
 }
 if (!found) {
 printf("Student with Roll Number %d not found.\n", rollNumber);
 }
}
// Function to search for a student by roll number
void searchStudent(struct Student students[], int count, int rollNumber) {
 int found = 0;
 for (int i = 0; i < count; i++) {
 if (students[i].rollNumber == rollNumber) {
 printf("Student Found:\n");
 printf("Name: %s | Roll Number: %d | Marks: %.2f\n", students[i].name, students[i].rollNumber, 
students[i].marks);
 found = 1;
 break;
 }
 }
 if (!found) {
 printf("Student with Roll Number %d not found.\n", rollNumber);
 }
}
int main() {
 struct Student students[100]; // Assuming a maximum of 100 students
 int choice, count = 0;
 do {
 displayMenu();
 printf("Enter your choice: ");
 scanf("%d", &choice);
 switch (choice) {
 case 1:
 insertStudent(students, &count);
 break;
 case 2:
 displayStudents(students, count);
 break;
 case 3:
 if (count == 0) {
 printf("No students to delete.\n");
 } else {
 int rollToDelete;
 printf("Enter the Roll Number to delete: ");
 scanf("%d", &rollToDelete);
 deleteStudent(students, &count, rollToDelete);
 }
 break;
 case 4:
 if (count == 0) {
 printf("No students to search.\n");
 } else {
 int rollToSearch;
 printf("Enter the Roll Number to search: ");
 scanf("%d", &rollToSearch);
 searchStudent(students, count, rollToSearch);
 }
 break;
 case 5:
 printf("Exiting program.\n");
 break;
 default:
 printf("Invalid choice. Please enter a valid option.\n");
 }
 } while (choice != 5);
 return 0;
}
OUTPUT
CODE
#include <stdio.h>
#include <stdlib.h>
struct node {
 int data;
 struct node *link;
};
typedef struct node Node;
Node *head = NULL;
// Function prototypes
void insbeg(int n);
void insend(int n);
void insspec(int pos);
int del(int d);
void disp();
void revdisprec(Node *h);
void revdisp();
void reverse();
void search(int key);
void sort();
int main() {
 int ch, a, f;
 while (1) {
 system("cls");
 printf("\n\t1. Insert at Beginning\n\t2. Insert at End\n\t3. Insert at Specific position\n\t4. Deletion\n\t5. 
Display\n\t6. Reverse Display(Recursive)\n\t7. Reverse Display(Non-Recursive)\n\t8. Reverse Linked 
List\n\t9. Search\n\t10. Sort (Selection Sort)\n\t11. Exit\n\n\tEnter your choice : ");
 scanf("%d", &ch);
 switch (ch) {
 case 1:
 printf("\n\tenter data to insert : ");
 scanf("%d", &a);
 insbeg(a);
 break;
 case 2:
 printf("\n\tenter data to insert : ");
 scanf("%d", &a);
 insend(a);
 break;
 case 3:
 printf("\n\tenter node position to be inserted : ");
 scanf("%d", &a);
 insspec(a);
 break;
 case 4:
 f = 0;
 if (head == NULL) {
 printf("\n\tlinked list is empty");
 } else {
 printf("\n\tenter node data to be deleted : ");
 scanf("%d", &a);
 f = del(a);
 }
 if (f == 0) {
 printf("\n\tdata not found there");
 } else {
 printf("\n\tdata %d deleted successfully", a);
 }
 break;
 case 5:
 disp();
 break;
 case 6:
 printf("\n\t");
 revdisprec(head); // reverse display using recursive function
 break;
 case 7:
 revdisp(); // reverse display using non-recursive function
 break;
 case 8:
 reverse();
 break;
 case 9:
 printf("\n\tEnter the key to search: ");
 scanf("%d", &a);
 search(a);
 break;
 case 10:
 sort();
 printf("\n\tList sorted using selection sort.");
 break;
 case 11:
 exit(0);
 default:
 printf("\n\n\tInvalid choice");
 }
 }
 return 0;
}
// Function definitions
void insbeg(int n) {
 Node *ins;
 ins = malloc(sizeof(Node));
 ins->data = n;
 ins->link = head;
 head = ins;
}
void insend(int n) {
 Node *ins, *t;
 ins = malloc(sizeof(Node));
 ins->data = n;
 ins->link = NULL;
 if (head == NULL) {
 head = ins;
 return;
 }
 t = head;
 while (t->link != NULL) {
 t = t->link;
 }
 t->link = ins;
}
void insspec(int pos) {
 Node *ins, *p, *n;
 int a, i, nc = 0;
 p = head;
 while (p != NULL) {
 p = p->link;
 nc++;
 }
 if (pos < 1 || pos > (nc + 1)) {
 printf("\n\n\tposition does not exist");
 return;
 }
 ins = malloc(sizeof(Node));
 printf("\n\tenter data to be inserted : ");
 scanf("%d", &(ins->data));
 ins->link = NULL;
 if (pos == 1) {
 ins->link = head;
 head = ins;
 return;
 }
 p = n = head;
 for (i = 0; i < pos - 1; i++) {
 p = n;
 n = p->link;
 }
 p->link = ins;
 ins->link = n;
}
int del(int d) {
 Node *p, *n;
 int f = 0;
 p = n = head;
 if (head->data == d) {
 head = head->link;
 p->link = NULL;
 free(p);
 f = 1;
 return (1);
 }
 while (n != NULL) {
 p = n;
 n = p->link;
 if (n == NULL) {
 break;
 }
 if (n->data == d) {
 p->link = n->link;
 n->link = NULL;
 free(n);
 f = 1;
 return (1);
 }
 }
 return (0);
}
void disp() {
 Node *t;
 if (head == NULL) {
 printf("\n\tlinked list is empty");
 return;
 }
 t = head;
 printf("\n\n\t");
 while (t != NULL) {
 printf("%d ", t->data);
 t = t->link;
 }
}
void revdisprec(Node *h) {
 if (h != NULL) {
 revdisprec(h->link);
 }
 if (h == NULL) {
 return;
 }
 printf("%d ", h->data);
}
void revdisp() {
 Node *p, *t;
 if (head == NULL) {
 printf("\n\tlinked list is empty");
 return;
 }
 t = head;
 printf("\n\n\t");
 while (t->link != NULL) {
 t = t->link;
 }
 while (t != head) {
 p = head;
 while (p->link != t) {
 p = p->link;
 }
 printf("%d ", t->data);
 t = p;
 }
 printf("%d", t->data);
}
void reverse() {
 Node *t, *z, *head1 = NULL;
 z = head;
 while (head != NULL) {
 t = malloc(sizeof(Node));
 t->data = z->data;
 t->link = head1;
 head1 = t;
 head = head->link;
 z->link = NULL;
 free(z);
 z = head;
 }
 head = t;
}
void search(int key) {
 Node *t = head;
 int pos = 1;
 while (t != NULL) {
 if (t->data == key) {
 printf("\n\tKey %d found at position %d", key, pos);
 return;
 }
 t = t->link;
 pos++;
 }
 printf("\n\tKey %d not found in the list", key);
}
void sort() {
 Node *i, *j;
 int temp;
 for (i = head; i != NULL; i = i->link) {
 for (j = i->link; j != NULL; j = j->link) {
 if (i->data > j->data) {
 temp = i->data;
 i->data = j->data;
 j->data = temp;
 }
 }
 }
}
OUTPUT
CODE
#include <stdio.h>
int main() {
 FILE *file;
 char filename[] = "C:\\example\\Data.txt";
 char data[1000];
 // Write data to the file
 file = fopen(filename, "w");
 if (file == NULL) {
 printf("Unable to open the file.\n");
 return 1;
 }
 printf("Enter data to write to the file:\n");
 gets(data); // Note: gets() is used for simplicity, but it's not recommended for real-world usage.
 fputs(data, file);
 fclose(file);
 // Read data from the file
 file = fopen(filename, "r");
 if (file == NULL) {
 printf("Unable to open the file for reading.\n");
 return 1;
 }
 printf("\nData read from the file:\n");
 while (fgets(data, sizeof(data), file) != NULL) {
 printf("%s", data);
 }
 // Counting characters, digits, white spaces, special characters, and lines
 rewind(file); // Move file pointer to the beginning
 int alphabets = 0, digits = 0, spaces = 0, specials = 0, lines = 0;
 char ch;
 while ((ch = fgetc(file)) != EOF) {
 if ((ch >= 'A' && ch <= 'Z') || (ch >= 'a' && ch <= 'z')) {
 alphabets++;
 } else if (ch >= '0' && ch <= '9') {
 digits++;
 } else if (ch == ' ' || ch == '\t') {
 spaces++;
 } else if (ch == '\n' || ch == '\r') {
 lines++;
 } else {
 specials++;
 }
 }
 fclose(file);
 // Display the count of characters, digits, white spaces, special characters, and lines
 printf("\nStatistics of the file content:\n");
 printf("Alphabets: %d\n", alphabets);
 printf("Digits: %d\n", digits);
 printf("White Spaces: %d\n", spaces);
 printf("Special Characters: %d\n", specials);
 printf("Number of Lines: %d\n", lines);
 return 0;
}
OUTPUT
CODE
#include <stdio.h>
// Structure to represent employee data
struct Employee {
 char name[50];
 char department[50];
 int eid;
 float salary;
 int age;
};
int main() {
 FILE *file;
 char filename[] = "D:\\data\\Emp.dat";
 // Writing formatted data to the file
 file = fopen(filename, "w");
 if (file == NULL) {
 printf("Unable to open the file for writing.\n");
 return 1;
 }
 // Input data for an employee
 struct Employee emp;
 printf("Enter employee data:\n");
 printf("Name: ");
 scanf("%s", emp.name);
 printf("Department: ");
 scanf("%s", emp.department);
 printf("Employee ID (Eid): ");
 scanf("%d", &emp.eid);
 printf("Salary: ");
 scanf("%f", &emp.salary);
 printf("Age: ");
 scanf("%d", &emp.age);
 // Write employee data to the file
 fprintf(file, "%s %s %d %.2f %d\n", emp.name, emp.department, emp.eid, emp.salary, emp.age);
 fclose(file);
 // Reading formatted data from the file
 file = fopen(filename, "r");
 if (file == NULL) {
 printf("Unable to open the file for reading.\n");
 return 1;
 }
 // Read and display employee data from the file
 printf("\nEmployee data read from the file:\n");
 fscanf(file, "%s %s %d %f %d", emp.name, emp.department, &emp.eid, &emp.salary, &emp.age);
 printf("Name: %s\n", emp.name);
 printf("Department: %s\n", emp.department);
 printf("Employee ID (Eid): %d\n", emp.eid);
 printf("Salary: %.2f\n", emp.salary);
 printf("Age: %d\n", emp.age);
 fclose(file);
 return 0;
}

