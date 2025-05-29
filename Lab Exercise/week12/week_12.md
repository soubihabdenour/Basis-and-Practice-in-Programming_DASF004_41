# Week 12: Dynamic Allocation

## **Overview**
Welcome to Week 12 of C programming! This week, we will explore dynamic allocation. By the end of this tutorial, you will:
- Understand malloc, calloc, realloc, and free
- Structure Pointer
### **Time Breakdown**
- **Basic concecpt of Dynamic allocation**
- **malloc, calloc, realloc, and free**
- **Structure Pointer**
- **Exercises & Q/A**

---

## **1. Malloc **
It allocates space dynamically in run time.
### **Example:** 
```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    int *arr;
    int n;

    printf("size of array: ");
    scanf("%d", &n);

    arr = (int *)malloc(n * sizeof(int));  
    if (arr == NULL) {
        printf(" failed to allocate\n");
        return 1;
    }

    for (int i = 0; i < n; i++) {
        arr[i] = i * 10;
    }

    printf("array : ");
    for (int i = 0; i < n; i++) {
        printf("%d ", arr[i]);
    }

    free(arr); 
    return 0;
}


```
### **Example Output:**
```
size of array: 5
array : 0 10 20 30 40 
```

---

## **2. Calloc **
It's almost same with malloc but it reset space with 0.

### **Example:** 

```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    int *arr;
    int n;

    printf("Size of array: ");
    scanf("%d", &n);

    arr = (int *)calloc(n, sizeof(int)); 
    if (arr == NULL) {
        printf(" failed to allocate\n");
        return 1;
    }

    printf("array: ");
    for (int i = 0; i < n; i++) {
        printf("%d ", arr[i]);
    }

    free(arr);
    return 0;
}
```


### **Example Output:**
```
Size of array: 5
array: 0 0 0 0 0 
```

---

## **3. realloc **
It tries to resize the existing memory space.  
If it can’t, it allocates a new space, copies the data, and frees the old one.

### **Example:**
```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    int *arr;
    int n = 3;

    arr = (int *)malloc(n * sizeof(int));
    if (arr == NULL) {
        printf("failed to allocate\n");
        return 1;
    }

    for (int i = 0; i < n; i++) arr[i] = i + 1;

    printf("original array: ");
    for (int i = 0; i < n; i++) printf("%d ", arr[i]);
    printf("\n");
    n = 6;
    int *temp = realloc(arr, n * sizeof(int));  // 크기 확장
    if (temp == NULL) {
        printf("\n failed to reallocate\n");
        free(arr);
        return 1;
    }
    arr = temp;

    for (int i = 3; i < n; i++) arr[i] = (i + 1) * 10;

    printf("new array:");
    for (int i = 0; i < n; i++) printf("%d ", arr[i]);
    printf("\n");
    free(arr);
    return 0;
}



```
### **Example Output:**
```
original array: 1 2 3 
new array:1 2 3 40 50 60 
```
---

## **4. Allocation Using Structure Pointer **


### **Example:** How to define and use a Pointer
```c
#include <stdio.h>
#include <stdlib.h>

typedef struct {
    char name[30];
    int age;
} Person;

int main() {
    Person *p;
    int n;
    printf("Number of People: ");
    scanf("%d",&n);
    p= (Person *)malloc(sizeof(Person) * n);
    if (p == NULL) {
        printf("failed to allocate\n");
        return 1;
    }
    for(int i=0;i<n;i++){
        printf("name: ");
        scanf("%s", p[i].name);
        printf("age: ");
        scanf("%d", &p[i].age);
    }

    for(int i=0;i<n;i++){
        printf("%dth name: %s, age: %d\n", i,p[i].name, p[i].age);
    }

    free(p);
    return 0;
}


```
### **Example Output:**
```
Number of People: 3
name: Kim
age: 20
name: Lee
age: 10
name: Park
age: 24
0th name: Kim, age: 20
1th name: Lee, age: 10
2th name: Park, age: 24
```

---

### **Exercise 1: Make a dynamic array and find the largest and smallest number. **
Write a C program to get a dynamic array of numbers and return the largest and smallest number in the array.  
You should use malloc( ) and free the memory at the end of your application using free( )

   
### **Example Output **
```
Enter the size of the array: 3
Enter 3 elements of  the array: 10 9 22
Largest element present in the given array is : 22
Smallest element present in the given array is : 9
```

### **Exercise 2: Utilizing realloc ** 
Create a program that prompts the user to fill an array with a specified size  
and then allows the user to insert a number at any position.


### **Example Output **
```
Enter size of the array : 5
Enter elements in array : 0 1 2 3 4
Enter element to insert : 9
Enter the element position : 2
Array elements after insertion : 0 1 9 2 3 4 
```

### **Exercise 3: Make a scoreboard **
We want to create a c program that request the number of enrolled subjects to get these subjects name and score.  
Then calculate the average grade in the overall semester.   
You should create a course structure with subject name and mark.

   
### **Example Output **
```
Enter the number of records: 4
Enter subject and marks:
Math 100
Enter subject and marks:
English 80
Enter subject and marks:
Korean 94
Enter subject and marks:
Science 77
Displaying Information:
Math    100
English 80
Korean  94
Science 77
Your averge  = 87
```

---

