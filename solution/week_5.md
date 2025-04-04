# W5 Answers

### 🔍 Exercise 1: Make a swap function
1. Input two numbers
2. change the value of each variable
3. print the result 



```c
#include<stdio.h>

void I_can_swap_num(int *a, int *b) {
    int temp=*a;
    *a=*b;
    *b=temp;
}

void main(){
    int num1,num2;
    printf("Please enter two numbers: ");
    scanf("%d %d", &num1, &num2);
    printf("Before swap num: num1 = %d, num2 = %d\n", num1, num2);
    I_can_swap_num(&num1, &num2);
    printf("After swap num: num1 = %d, num2 = %d\n", num1, num2);
}
```

---

### 🔍 Exercise 2: Make a program hadling 1-dimension matrix (array)

You need to write these functinos:

- void set_matrix(int ary[], int len);  
-set the matrix in ascending order from 0 to len

- void reverse_matrix(int ary[], int len);  
-Reverse the order of the array  

- void print_matrix(int ary[], int len);  
-Print out all numbers in the array  

Hint* 
1. Size of array varies everytime. Use a sizeof() function to get a length of array
2. Array is handled in the way of Call By Reference. You don't need to care about pointer!


```c
#include<stdio.h>
#define ARYSIZE 9
void set_matrix(int ary[], int len){
    for(int i=0; i< len; i++){
        ary[i] = i;
    }
}
void reverse_matrix(int ary[], int len){
    for(int i=0; i<len/2; i++){
        int temp = ary[i];
        ary[i] = ary[len - 1 - i];
        ary[len - 1 - i] = temp;
    }
} 

void print_matrix(int ary[], int len){
    printf("Matrix: ");
    for(int i=0; i<len; i++){
        printf("%d ", ary[i]);
    }
    printf("\n");
}

int main(){
    int a[ARYSIZE];
    int length=sizeof(a)/sizeof(a[0]);

    set_matrix(a,length);
    printf("===== After set_matrix function =====\n");
    print_matrix(a,length);

    reverse_matrix(a,length);
    printf("===== After reverse_matrix function =====\n");
    print_matrix(a,length);

    return 0;
}
```

---

### 🔍 Exercise 3: Write a program that calculate the Factorial using recursive function and for/while loop.


```c
#include<stdio.h>

int factorial(int n){
    if(n==0 || n==1){
        return 1;
    }
    return n * factorial(n-1);
}

int forloop_factorial(int n){
    int result = 1;
    for(int i=2; i<=n; i++){
        result *= i;
    }
    return result;
}

int main(){
    int num;
    printf("Please enter a number: ");
    scanf("%d", &num);
    printf("Factorial of %d using recursive function is %d\n", num, factorial(num));
    printf("Factorial of %d using for loop is %d\n", num, forloop_factorial(num));

    return 0;
}
```

---

