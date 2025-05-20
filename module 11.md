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
```
#include <stdio.h>
int max_of_four(int a,int b,int c,int d)
{
    if(a>b && a>c && a>d){
        return a;
    }
    else if(b>a && b>c && b>d){
        return b;
    }
    else if(c>a && c>b && c>d){
        return c;
    }
    else{
        return d;
    }
}
int main()
{
    int n1,n2,n3,n4;
    scanf("%d %d %d %d",&n1,&n2,&n3,&n4);
    printf("%d",max_of_four(n1,n2,n3,n4));
}
```

Output:

![image](https://github.com/user-attachments/assets/cbe9e57a-c87b-421f-9186-d63f1b49e170)


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
```
#include <stdio.h>
void calculate_the_maximum(int n,int k)
{
    int max_and=0;
    int max_or=0;
    int max_xor=0;
    for(int i=1;i<=n;i++){
        for(int j=i+1;j<=n;j++){
            int cur_and=i&j;
            int cur_or=i|j;
            int cur_xor=i^j;
            if(cur_and<k && cur_and>max_and){
                max_and=cur_and;
            }
            if(cur_or<k && cur_or>max_or){
                max_or=cur_or;
            }
            if(cur_xor<k && cur_xor>max_xor){
                max_xor=cur_xor;
            }
        }
    }
    printf("%d\n%d\n%d",max_and,max_or,max_xor);
}
int main()
{
    int a,b;
    scanf("%d %d",&a,&b);
    calculate_the_maximum(a,b);
}
```


Output:


![image](https://github.com/user-attachments/assets/4c3a0688-406a-488b-bf4c-832ac6da4af5)


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
```
#include <stdio.h>
#include <stdlib.h>

int *total_number_of_books;
int **total_number_of_pages;

int main()
{
    int total_number_of_shelves;
    scanf("%d",&total_number_of_shelves);
    
    total_number_of_books=calloc(total_number_of_shelves,sizeof(int));
    total_number_of_pages=malloc(total_number_of_shelves*sizeof(int *));
    
    for(int i=0;i<total_number_of_shelves;i++){
        total_number_of_pages[i]=calloc(1100,sizeof(int));
    }
    
    int total_number_of_queries;
    scanf("%d",&total_number_of_queries);
    
    while(total_number_of_queries--){
        int type_of_query;
        scanf("%d",&type_of_query);
        
        if(type_of_query==1){
            int shelf,pages;
            scanf("%d %d",&shelf,&pages);
            
            int book_index=total_number_of_books[shelf];
            total_number_of_pages[shelf][book_index]=pages;
            total_number_of_books[shelf]++;
        }
        else if(type_of_query==2){
            int shelf,book;
            scanf("%d %d",&shelf,&book);
            printf("%d\n",total_number_of_pages[shelf][book]);
        }
        else if(type_of_query==3){
            int shelf;
            scanf("%d",&shelf);
            printf("%d\n",total_number_of_books[shelf]);
        }
    }
    for(int i=0;i<total_number_of_shelves;i++){
            free(total_number_of_pages[i]);
    }
    free(total_number_of_pages);
    free(total_number_of_books);
}
```


Output:


![image](https://github.com/user-attachments/assets/f3f8fe9c-a48e-4ea4-a180-72a3b2627e84)



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
```
#include <stdio.h>
int marks_summation(int* marks, char gender, int number_of_students){
    int sum=0;
    int start_index;
    if(gender=='b'){
        start_index=0;
    }
    else{
        start_index=1;
    }


    for(int i=start_index;i<number_of_students;i+=2){
        sum+=marks[i];
    }
    return sum;
}
int main()
{
    int number_of_students;
    scanf("%d",&number_of_students);
    int marks[number_of_students];
    for(int i=0;i<number_of_students;i++){
        scanf("%d",&marks[i]);
    }
    char gender;
    scanf(" %c",&gender);
    int result=marks_summation(marks,gender,number_of_students);
    printf("%d\n",result);
}
```

Output:


![image](https://github.com/user-attachments/assets/9c0ccbb8-0e12-4126-a087-f3f692618bd2)


Result:
Thus, the program prints the sum of the integers in the array is verified successfully.


 
EXP NO 25: C PROGRAM TO CALCULATE THE SUM OF ELEMENTS

Aim:

create an array of size  dynamically, and read the values from stdin. Iterate the array calculating the sum of all elements. Print the sum and free the memory where the array is stored.

While it is true that you can sum the elements as they are read, without first storing them to an array, but you will not get the experience working with an array. Efficiency will be required later.

Algorithm:

1.Start
2.Input the number of elements n
3.Dynamically allocate memory for an array of size n
4.Initialize sum ← 0
5.Repeat for i ← 0 to n - 1:
    a. Input arr[i]
    b. Add arr[i] to sum
6.Output the value of sum
7.Free the allocated memory
8.End

Program:
```
#include <stdio.h>
#include<stdlib.h>
int main()
{
    int n;
    scanf("%d",&n);
    int *arr=malloc(n*sizeof(arr));
    int sum=0;
    for(int i=0;i<n;i++){
        scanf("%d",&arr[i]);
        sum+=arr[i];
    }
    printf("%d",sum);
    free(arr);
}
```

Output:


![image](https://github.com/user-attachments/assets/c4591abf-f471-4a3c-b9a3-e33a4cc28a32)




Result:

Thus, the program that counts the number of words in a given sentence is verified 
successfully.
