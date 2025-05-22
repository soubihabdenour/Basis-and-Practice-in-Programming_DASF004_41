# Week 11: Strings and String Functions

## **Overview**

Welcome to Week 11 of C programming! This week, we will explore how to declare and manipulate strings in C.  
By the end of this tutorial, you will:

- Understand how strings are stored in memory (`char[]` and `char *`)
- Use input/output functions like `fgets`, `puts`, and `scanf`
- Work with common string functions such as `strlen`, `strcat`, `strcmp`, `strncpy`
- Convert strings to numbers using `atoi`, `atof`, etc.

### **Time Breakdown**

- String declaration and usage
- Pointer vs Array in strings
- Built-in string functions
- String-to-number conversion
- Exercises & Q/A

---

## **Examples**

### **Example 1: Basic String Input and Output**

```c
#include <stdio.h>

int main(void) {
    char str[100];
    printf("Enter a sentence: ");
    fgets(str, sizeof(str), stdin);
    printf("You typed: ");
    puts(str);
    return 0;
}
```

---

### **Example 2: Pointer vs Array**

```c
#include <stdio.h>

int main(void) {
    char arr[] = "Hello";
    char *ptr = "World";
    puts(arr);
    puts(ptr);
    return 0;
}
```

---

### **Example 3: String Functions**

```c
#include <stdio.h>
#include <string.h>

int main(void) {
    char a[20] = "Hi";
    char b[] = " there";
    strcat(a, b);
    printf("Concatenated: %s\n", a);
    printf("Length: %lu\n", strlen(a));
    return 0;
}
```

---

### **Example 4: String to Number**

```c
#include <stdio.h>
#include <stdlib.h>

int main(void) {
    char str[] = "123";
    int num = atoi(str);
    printf("Converted: %d\n", num);
    return 0;
}
```

---

## **Exercises**

### **Exercise 1: Read and Count Characters**

1. Ask the user to enter a sentence using `fgets()`.
2. Print the sentence and also display how many characters it has using `strlen()`.

### **Example Output:**

```
Enter a sentence: I like pizza.
You typed: I like pizza.
Length: 14
```

---

### **Exercise 2: Modifying char[] vs char\* Strings**

1. Declare a string using `char arr[]` and another using `char *ptr`.
2. Try modifying the first character of both. Print the results and observe which one works.

### **Example Output:**

```
Modified arr: Xello
Modifying ptr caused a crash or is not allowed.
```

---

### **Exercise 3: Use String Functions Together**

1. Ask the user to enter two words.
2. Compare them using `strcmp()` and print the result.
3. Concatenate them using `strcat()`.

### **Example Output:**

```
Enter first word: Hello
Enter second word: World
Comparison result: not equal
Joined: HelloWorld
```

---

### **Exercise 4: Convert and Sum Two Numbers**

1. Ask the user to enter two numbers as strings.
2. Convert them to integers using `atoi()`.
3. Print their sum.

### **Example Output:**

```
Enter two numbers: 12 34
Sum: 46
```

---

## **Exercise 5: Count Words**

1.Count how many words are in a sentence. Words are separated by spaces.

### **Example Output:**

```
Enter a sentence: I like C programming a lot
Words counted: 5
```
