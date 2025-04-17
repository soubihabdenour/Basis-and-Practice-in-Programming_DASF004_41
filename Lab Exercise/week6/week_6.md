# Week 6: Arrays, Randomness, and Control Flow

## **Overview**

Welcome to Week 7 of C programming! This week, we’ll explore arrays, randomness, and special control flow keywords. By the end of this tutorial, you will:

- Understand how to declare and use 1D and 2D arrays
- Generate and use random numbers using `rand()`
- Use `break`, `continue`, and `goto` for controlling loops
- Understand how to use variable-length arrays (VLAs)
- Print and understand memory addresses using `%p`

### **Time Breakdown**

- Control Flow (`break`, `continue`, `goto`)
- 1D Arrays and Address Printing
- Random Number Generation with `rand()`
- 2D Arrays and Variable-Length Arrays
- Exercises & Q/A

---

## **1.Control Flow Keywords: break, continue, goto**

Control flow keywords help change the normal execution of loops.

### **Example 1:** Skip 0s and stop at 999

```c
#include <stdio.h>

int main(void) {
    int num;

    while (1) {
        scanf("%d", &num);

        if (num == 0) continue;
        if (num == 999) break;

        printf("You entered: %d\n", num);
    }

    return 0;
}
```

### **Example Output:**

```
1
You entered: 1
2
You entered: 2
3
You entered: 3
0
2
You entered: 2
3
You entered: 3
4
You entered: 4
999
```

---

## **2. 1D Arrays & Address Printing**

Arrays store a collection of variables. Using `%p` allows you to see memory addresses.

### **Example 2:** Print array values and addresses

```c
#include <stdio.h>

int main(void) {
    int arr[3] = {1, 2, 3};

    for (int i = 0; i < 3; i++) {
        printf("arr[%d] = %d, address = %p\n", i, arr[i], &arr[i]);
    }

    return 0;
}
```

### **Example Output:**

```
arr[0] = 1, address = 0x16b3e0564
arr[1] = 2, address = 0x16b3e0568
arr[2] = 3, address = 0x16b3e056c
```

---

## **3. Random Number Generation**

`rand()` generates pseudorandom integers. Use `srand(time(0))` to ensure different results on each run.

### **Example 3:** Generate 10 random numbers

```c
#include <stdio.h>
#include <stdlib.h>
#include <time.h>

int main(void) {
    srand(time(0));

    for (int i = 0; i < 10; i++) {
        printf("%d \n", rand() % 10); // random number from 0 to 9
    }

    return 0;
}
```

### **Example Output:**

```
0
9
1
0
3
8
1
2
4
```

---

## **4. 2D Arrays and Variable-Length Arrays**

You can create 2D arrays with fixed or variable dimensions using int `M[r][c]`.

### **Example 4:** Generate 10 random numbers

```c
#include <stdio.h>

int main(void) {
    int r = 2, c = 3;
    int M[r][c];

    printf("Enter 6 integers:\n");
    for (int i = 0; i < r; i++)
        for (int j = 0; j < c; j++)
            scanf("%d", &M[i][j]);

    printf("Matrix:\n");
    for (int i = 0; i < r; i++) {
        for (int j = 0; j < c; j++)
            printf("%d ", M[i][j]);
        printf("\n");
    }

    return 0;
}
```

### **Example Output:**

```
1 2 3 4 5 6
Matrix:
1 2 3
4 5 6
```

---

## **Exercise 1: Count how many even numbers are in an array.**

1. Ask the user to enter 10 integers into a 1D array.
2. Print how many of them are even.

### **Example Output:**

```
Number of even values: 4
```

## **Exercise 2: Calculate the sum of a 2D array.**

1. Ask the user to input a 3x3 matrix
2. Print the total sum of all elements.

### **Example Output:**

```
Sum: 45
```

## **Exercise 3: CFill an array with random numbers and find the maximum.**

1. Use `rand()` to generate 10 random numbers
2. Print the largest number

### **Example Output:**

```
Max: 92
```

## **Exercise 4: Work with Variable-Length Arrays.**

1. Ask the user how many elements they want to enter
2. Create a VLA and store those values
3. Print them in entered order

### **Example Output:**

```
5
1 2 3 4 5
1 2 3 4 5
```

---

## **Bonus Challenge: Matrix Diagonal Sum**

Ask the user to input a 3x3 matrix and print the sum of the diagonal elements.

---

## **Summary & Wrap-Up**

This week, we covered:

- Using `break`, `continue`, and `goto` to control loops
- How arrays and pointers relate
- Using `rand()` and variable-length arrays

### **Next Week:** Midterm!

Happy coding! 🚀
