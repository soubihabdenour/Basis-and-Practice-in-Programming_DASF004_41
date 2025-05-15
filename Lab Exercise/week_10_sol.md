# Week 10: File Input and Output (File I/O) - Solutions

## **Exercise Solutions**

### **Exercise 1: Write Names to File**

1. Ask the user to input 3 names.
2. Write them line by line to `names.txt`.
3. Open the file and print all names.

```c
#include <stdio.h>

int main(void) {
    FILE *fp = fopen("names.txt", "w");
    char name[30];
    for (int i = 0; i < 3; i++) {
        scanf("%s", name);
        fprintf(fp, "%s\n", name);
    }
    fclose(fp);

    fp = fopen("names.txt", "r");
    printf("names.txt contents:\n");
    while (fgets(name, sizeof(name), fp) != NULL) {
        printf("%s", name);
    }
    fclose(fp);
    return 0;
}
```

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

```c
#include <stdio.h>

int main(void) {
    FILE *fp = fopen("nums.txt", "r");
    int x, sum = 0;
    while (fscanf(fp, "%d", &x) == 1) {
        sum += x;
    }
    printf("Total sum = %d\n", sum);
    fclose(fp);
    return 0;
}
```

### **Example Output:**

```
File: 10 20 30
Total sum = 60
```

---

### **Exercise 3: Read Last Character**

1. Open a text file and move to the last byte using `fseek()`.
2. Print the last character.

```c
#include <stdio.h>

int main(void) {
    FILE *fp = fopen("example.txt", "r");
    fseek(fp, -1, SEEK_END);
    char ch = fgetc(fp);
    printf("Last character: %c\n", ch);
    fclose(fp);
    return 0;
}
```

### **Example Output:**

```
Last character: !
```

---

### **Exercise 4: Store Multiple Students**

1. Define a `Student` structure with `name` and `score`.
2. Store 2 student records to a binary file.
3. Reopen and print both students.

```c
#include <stdio.h>

struct Student {
    char name[20];
    int score;
};

int main(void) {
    struct Student s[2] = {{"Alice", 90}, {"Bob", 85}};
    FILE *fp = fopen("students.dat", "wb");
    fwrite(s, sizeof(struct Student), 2, fp);
    fclose(fp);

    struct Student r[2];
    fp = fopen("students.dat", "rb");
    fread(r, sizeof(struct Student), 2, fp);
    fclose(fp);

    for (int i = 0; i < 2; i++) {
        printf("Student %d: %s %d\n", i + 1, r[i].name, r[i].score);
    }
    return 0;
}
```

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

```c
#include <stdio.h>

int main(void) {
    FILE *fp = fopen("text.txt", "r");
    char ch;
    int chars = 0, words = 0, lines = 0, in_word = 0;

    while ((ch = fgetc(fp)) != EOF) {
        chars++;
        if (ch == '\n') lines++;
        if (ch == ' ' || ch == '\n' || ch == '\t') {
            in_word = 0;
        } else if (!in_word) {
            in_word = 1;
            words++;
        }
    }
    fclose(fp);

    printf("Characters: %d\n", chars);
    printf("Words: %d\n", words);
    printf("Lines: %d\n", lines);
    return 0;
}
```

### **Example Output:**

```
Characters: 35
Words: 6
Lines: 2
```
