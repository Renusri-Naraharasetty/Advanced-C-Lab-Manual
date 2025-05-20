EXP NO:6 C PROGRAM PRINT THE LOWERCASE ENGLISH WORD CORRESPONDING TO THE NUMBER
Aim:
To write a C program print the lowercase English word corresponding to the number
Algorithm:
1.	Start
- Initialize an integer variable n.
2.	Input Validation
3.	Switch Statement cases.
-	Case 5: Print "seventy one"
-	Case 6: Print "seventy two"
-	Case 13: Print "seventy three"
-	...
-	Case 13: Print "seventy nine"
-	Default: Print "Greater than 13"
4.	Exit the program.
 
Program:

```
#include <stdio.h>
int main()
{
    int n;
    scanf("%d",&n);
    switch(n){
        case 71:
            printf("seventy one");
            break;
        case 72:
            printf("seventy two");
            break;
        case 73:
            printf("seventy three");
            break;
        case 74:
            printf("seventy four");
            break;
        case 75:
            printf("seventy five");
            break;
        case 76:
            printf("seventy six");
            break;
        case 77:
            printf("seventy seven");
            break;
        case 78:
            printf("seventy eight");
            break;
        case 79:
            printf("seventy nine");
            break;
        default:
            printf("Greater than 79");
    }
}
```



Output:

![image](https://github.com/user-attachments/assets/0bee390a-8bbb-4e86-9f41-6dfc169d952f)







Result:
Thus, the program is verified successfully
 
EXP NO:7 C PROGRAM TO PRINT TEN SPACE-SEPARATED INTEGERS     IN A SINGLE  LINE DENOTING THE FREQUENCY OF EACH DIGIT FROM 0 TO 3 .
Aim:
To write a C program to print ten space-separated integers in a single line denoting the frequency of each digit from 0 to 3.
Algorithm:
1.	Start
2.	Declare char array a[50] outer loop for each digit from 0 to 3
3.	Initialize counter c to 0
4.	For each character in the string print count c for current digit, followed by a space
5.	Increment h to move to the next digit
6.	End
 
Program:
```
#include <stdio.h>
#include <ctype.h>
int main() {
    char s[1000];       
    int digits[10] = {0};  
    scanf("%s", s);      
    for (int i = 0; s[i] != '\0'; i++) {
        if (isdigit(s[i])) {
            digits[s[i] - '0']++; 
        }
    }
    for (int i = 0; i < 10; i++) {
        printf("%d ", digits[i]);
    }
}

```




Output:

![image](https://github.com/user-attachments/assets/98bd8b92-9ece-4b79-b38e-5fda78d00078)

Result:
Thus, the program is verified successfully

EXP NO:8 C PROGRAM TO PRINT ALL OF ITS PERMUTATIONS IN STRICT LEXICOGRAPHICAL ORDER.
Aim:
To write a C program to print all of its permutations in strict lexicographical order.

Algorithm:
1.	Start
2.	Declare variables s (pointer to an array of strings) and n (number of strings)

3.	Memory Allocation
Dynamically allocate memory for s to store an array of strings
4.	Input
Read the number of strings n from the user Dynamically allocate memory for each string in s
5.	Permutation Generation Loop
6.	Memory Deallocation
Free the memory allocated for each string in s Free the memory allocated for s
7.	End
 
Program:
```
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

#define MAX 100

int compare(const void *a, const void *b) {
    return strcmp(*(const char **)a, *(const char **)b);
}

void swap(char **a, char **b) {
    char *temp = *a;
    *a = *b;
    *b = temp;
}

// Function to generate next lexicographical permutation
int next_permutation(char *arr[], int n) {
    int i = n - 2;

    // Find rightmost character which is smaller than its next character
    while (i >= 0 && strcmp(arr[i], arr[i + 1]) >= 0)
        i--;

    if (i < 0)
        return 0; // Last permutation

    // Find the smallest character on right side of i and greater than arr[i]
    int j = n - 1;
    while (strcmp(arr[j], arr[i]) <= 0)
        j--;

    swap(&arr[i], &arr[j]);

    // Reverse the suffix
    int left = i + 1, right = n - 1;
    while (left < right) {
        swap(&arr[left], &arr[right]);
        left++;
        right--;
    }

    return 1;
}

void print_permutation(char *arr[], int n) {
    for (int i = 0; i < n; i++) {
        printf("%s", arr[i]);
        if (i < n - 1) printf(" ");
    }
    printf("\n");
}

int main() {
    int n;
    scanf("%d", &n);
    char *arr[MAX];

    for (int i = 0; i < n; i++) {
        arr[i] = (char *)malloc(101 * sizeof(char));
        scanf("%s", arr[i]);
    }

    // Sort initially to start from the first lexicographic permutation
    qsort(arr, n, sizeof(char *), compare);

    print_permutation(arr, n);

    while (next_permutation(arr, n)) {
        print_permutation(arr, n);
    }

    // Free memory
    for (int i = 0; i < n; i++)
        free(arr[i]);

    return 0;
}

```

Output:

![image](https://github.com/user-attachments/assets/cf592105-4177-4dfc-99bf-cfc5f4c2eecf)







Result:
Thus, the program is verified successfully
 
EXP NO:9 C PROGRAM PRINT A PATTERN OF NUMBERS FROM 1 TO N AS
SHOWN BELOW.
Aim:
To write a C program to print a pattern of numbers from 1 to n as shown below.
Algorithm:
1.	Start
2.	Declare integer variables n, i, j, min
3.	Read the value of n from the user
4.	Calculate the length of the side of the square matrix: len = n * 2 - 1
5.	Matrix Generation Loop
6.	Calculate min as the minimum distance to the borders
7.	End
 
Program:
```
#include <stdio.h>
int main()
{
    int n;
    scanf("%d",&n);
    int size=2*n-1;
    for(int i=0;i<size;i++){
        for(int j=0;j<size;j++){
            int min=i<j?i:j;
            min=min<size-i-1?min:size-i-1;
            min=min<size-j-1?min:size-j-1;
            printf("%d ",n-min);
        }
        printf("\n");
    }
    return 0;
}
```

Output:

![image](https://github.com/user-attachments/assets/11348457-1746-4236-9b38-14dc38d031bb)

Result:
Thus, the program is verified successfully

EXP NO:10 C PROGRAM TO FIND A SQUARE  OF NUMBER USING FUNCTION WITHOUT ARGUMENTS WITH RETURN TYPE

Aim:

Given a five digit integer n, print the sum of its digits.

Algorithm:
1.Start
2.Declare variables a and sum ← 0
3.Read input number a
4.Repeat while a ≠ 0:
    a. Add a % 10 to sum
    b. Update a ← a / 10 (integer division)
5.Print sum
6.End

Program:
```
#include<stdio.h>
int main()
{
    int a,sum=0;
    scanf("%d",&a);
    while(a!=0)
    {
        sum+=a%10;
        a/=10;
    }
    printf("%d",sum);
}
```




Output:

![image](https://github.com/user-attachments/assets/5d18b370-12fa-4531-9fc5-330859c96f07)







Result:
Thus, the program is verified successfully



























