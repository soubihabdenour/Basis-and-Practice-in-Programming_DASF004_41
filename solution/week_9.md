# Week 9: Pointers and Pointer Operations - Solutions

## **Exercises Solutions**

### **Exercise 1:  change multiple values in a function using pointers.**

1. Initialize 4 int variables.
2. Write a function that adds 1 to each variable.
3. print the result

```c
#include<stdio.h>

void change(int *a, int *b, int *c, int *d){
    (*a)++;
    (*b)++;
    (*c)++;
    (*d)++;
}

int main(){
    int a=1,b=2,c=3,d=4;
    printf("=====before change=====\n");
    printf("a = %d, b = %d, c = %d, d = %d\n",a,b,c,d);
    change(&a,&b,&c,&d);
    printf("=====after change=====\n");
    printf("a = %d, b = %d, c = %d, d = %d\n",a,b,c,d);
}
```

### **Example Output:**

```
=====before change=====
a = 1, b = 2, c = 3, d = 4
=====after change=====
a = 2, b = 3, c = 4, d = 5
```

---

### **Exercise 2:  Find Maximum Value Using Pointers **
Write a program to find the maximum value in an array using pointers.  
You can initialize the array in the way you want:  
Eg.) int array[6] ={3, 2, 4, 22, 15, 6, 8};

```c
#include <stdio.h>

int main(void) {
    int arr[5] = {10, 20, 30, 15, 25};
    int *p = arr;
    int max = -1;

    for (int i = 1; i < 5; i++) {
        if (*(p + i) > max) {
            max = *(p + i);
        }
    }

    printf("Maximum value = %d\n", max);
    return 0;
}
```

### **Example Output:**

```
Maximum value = 22
```

---

### **Exercise 3: Find an Alphabet in a word **

1. Please get an alphabet from a user.
2. Please get a word from a user.
3. Check if the word includes the alphabet 'using pointer'.
   (Please find it using pointer arithmetic, not array index access.) 
4. Print if the alphabet is found.

```c
#include<stdio.h>
#include<string.h>
#define MAX 30

int main(){
    char ary[MAX];
    char alpha;
    printf("Please input the alphabet you want: ");
    scanf(" %c",&alpha);
    printf("Please input the word you want: ");
    scanf(" %s",ary);

    char *ptr=ary;
    for(int i=0;i<strlen(ary);i++){
        //printf("now alpha is %c\n",*ptr);
        if(*ptr==alpha) {
            printf("found %c!\n",*ptr);
            return 0;
        }
        ptr++;
    }
    printf("cannot find %c!\n",alpha);
}
```

### **Example Output:**

```
Please input the alphabet you want: i
Please input the word you want: apple
cannot find i!
```
```
Please input the alphabet you want: a
Please input the word you want: grammer
found a!
```

