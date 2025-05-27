# Week 10: File Input and Output (File I/O)

## **Overview**

Welcome to Week 10 of C programming!  
This week, we will learn how to work with files in C using the standard file I/O library.  
By the end of this tutorial, you will:

- Open and close files using `fopen()` and `fclose()`
- Read from and write to text files using `fprintf()` and `fscanf()`
- Understand file positioning using `fseek()` and `ftell()`
- Use binary I/O functions `fwrite()` and `fread()`

### **Time Breakdown**

- Text file write and read
- File position and stream control
- Binary file I/O
- Exercises & Q/A

---

## **Examples**

### **Example 1: Write to a File**

Create a text file and write a line of text into it using `fopen()` and `fprintf()`.

```c
#include <stdio.h>

int main(void) {
    FILE *fp = fopen("example.txt", "w");
    if (fp == NULL) {
        printf("Failed to open file.\n");
        return 1;
    }
    fprintf(fp, "Hello, File!\n");
    fclose(fp);
    return 0;
}
```

### **Example Output:**

```
example.txt created with content: Hello, File!
```

---

### **Example 2: Read from a File**

Open a file in read mode and read one line of text using `fgets()`.

```c
#include <stdio.h>

int main(void) {
    FILE *fp = fopen("example.txt", "r");
    if (fp == NULL) {
        printf("File not found.\n");
        return 1;
    }
    char str[100];
    fgets(str, sizeof(str), fp);
    printf("Read from file: %s", str);
    fclose(fp);
    return 0;
}
```

### **Example Output:**

```
Read from file: Hello, File!
```

---

### **Example 3: Use fseek and ftell**

Move the file pointer to the end of a file and determine the file's size using `fseek()` and `ftell()`.

```c
#include <stdio.h>

int main(void) {
    FILE *fp = fopen("example.txt", "r");
    if (fp == NULL) return 1;
    fseek(fp, 0, SEEK_END);
    long pos = ftell(fp);
    printf("File size: %ld bytes\n", pos);
    fclose(fp);
    return 0;
}
```

### **Example Output:**

```
File size: 13 bytes
```

---

### **Example 4: Save & Load Structure in Binary File**

Store a structure in a binary file using `fwrite()`

```c
#include <stdio.h>

struct Student {
    char name[20];
    int score;
};

int main(void) {
    struct Student s1 = {"Alice", 90};
    FILE *fp = fopen("student.dat", "wb");
    fwrite(&s1, sizeof(struct Student), 1, fp);
    fclose(fp);
    return 0;
}
```

### **Example Output:**

```
Binary file student.dat created with one student record.
```

---

## **Exercises**

### **Exercise 1: Write Names to File**

1. Ask the user to input 3 names.
2. Write them line by line to `names.txt`.
3. Open the file and print all names.

### **Example Output:**

```
Enter 3 names:
Alice Bob Charlie
names.txt contents:
Alice
Bob
Charlie
```

---

### **Exercise 2: Read Integers and Sum**

1. Create a file `nums.txt` with integers (space-separated). (In the created nums.txt file: ex: 10 20 30)
2. Read them using `fscanf()` and print the total sum.

### **Example Output:**

```
Total sum = 60
```

---

### **Exercise 3: Read Last Character**

1. Open a text file and move to the last byte using `fseek()`.
2. Print the last character.

### **Example Output:**

```
Last character: !
```

---

### **Exercise 4: Store Multiple Students**

1. Define a `Student` structure with `name` and `score`.
2. Store 2 student records to a binary file.
3. Reopen and print both students.

### **Example Output:**

```
Student 1: Alice 90
Student 2: Bob 85
```

---

## **Bonus Challenge: Text Summary Tool**

- Create text.txt file and try writing anything you want
- Read a text file and count:
  - Number of characters
  - Number of words (space-separated)
  - Number of lines

### **Example Output:**

```
Characters: 35
Words: 6
Lines: 2
```
