# Week 8: Structures, Typedef, and Enumerations

## **Overview**

Welcome to Week 8 of C programming!
This week, we will learn how to group different types of variables together using structures, define custom types with `typedef`, and create readable constant sets with `enum`.

By the end of this tutorial, you will:

- Understand how to define and use `struct`
- Pass structures to functions
- Use arrays of structures
- Use `typedef` and `enum` for more readable code

### **Time Breakdown**

- Structures and basic usage
- Functions with structures
- Arrays of structures
- Enumerated types and typedef
- Exercises & Q/A

---

## **1. Structures: Basics**

Structures allow grouping variables of different types into a single unit.

### **Example 1: Basic Structure Declaration and Access**

```c
#include <stdio.h>

struct Date {
    int day;
    int month;
    int year;
};

int main(void) {
    struct Date today = {26, 4, 2025};
    printf("Today's date is: %d/%d/%d\n", today.day, today.month, today.year);
    return 0;
}
```

### **Example Output:**

```
Today's date is: 26/4/2025
```

---

## **2. Functions with Structures**

Structures can be passed to functions as arguments.

### **Example 2: Update Date Using Structure and Function**

```c
#include <stdio.h>

struct Date {
    int day;
    int month;
    int year;
};

void addOneDay(struct Date d) {
    d.day += 1;
    printf("Tomorrow's date is: %d/%d/%d\n", d.day, d.month, d.year);
}

int main(void) {
    struct Date today = {26, 4, 2025};
    addOneDay(today);
    return 0;
}
```

### **Example Output:**

```
Tomorrow's date is: 27/4/2025
```

---

## **3. Arrays of Structures**

Structures can be stored in arrays.

### **Example 3: Store Multiple Dates**

```c
#include <stdio.h>

struct Date {
    int day;
    int month;
    int year;
};

int main(void) {
    struct Date events[2] = {{1, 5, 2025}, {10, 6, 2025}};
    for (int i = 0; i < 2; i++) {
        printf("Event %d date: %d/%d/%d\n", i+1, events[i].day, events[i].month, events[i].year);
    }
    return 0;
}
```

### **Example Output:**

```
Event 1 date: 1/5/2025
Event 2 date: 10/6/2025
```

---

## **4. Enumerations and Typedef**

Enums are used to assign readable names to integer constants.

### **Example 4: Enum Usage for Months**

```c
#include <stdio.h>

enum Month {JAN = 1, FEB, MAR, APR, MAY, JUN, JUL, AUG, SEP, OCT, NOV, DEC};

int main(void) {
    enum Month today = APR;
    printf("The current month number is: %d\n", today);
    return 0;
}
```

### **Example Output:**

```
The current month number is: 4
```

---

## **Exercises**

### **Exercise 1: Define and Print a Student Structure**

1. Define a Student structure with name (char array) and score (int).
2. Create a student, input data, and print it.

### **Example Output:**

```
Enter student name and score:
Alice 95
Alice scored 95 points.
```

### **Exercise 2: Add One Second to User-Input Time**

1. Define a Time structure with hour, minute, and second.
2. Prompt the user to input hour, minute, and second.
3. Write a function that adds one second to the input time, correctly handling overflow (i.e., 60 seconds → 1 minute, 60 minutes → 1 hour, 24 hours → 0).
4. Print the new time.

### **Example Output:**

```
Enter hour (0-23): 23
Enter minute (0-59): 59
Enter second (0-59): 59
New time: 00:00:00
```

### **Exercise 3: Map Months Using Enum**

1. Use enum Month to map a month number to its name.
2. Print the corresponding month.

### **Example Output:**

```
Enter month number (1-12): 5
Month number is: 5
```

### **Exercise 4: Use Typedef for Cleaner Struct**

1. Create a typedef for struct Book.
2. Input and print book information.

### **Example Output:**

```
Enter book title and number of pages:
CProgramming 500
Book: CProgramming, Pages: 500
```

---

## **Bonus Challenge**

🏆 Complex Structure: Event Log Management

1. You are asked to design a structure to manage event logs.
2. Define a Date structure with day, month, and year.
3. Define a Time structure with hour, minute, and second.
4. Define a Log structure that contains both a Date and a Time, along with a short message (char[]).
5. Ask the user to enter two event logs.
6. After collecting input, print the logs in the following format:

```
[YYYY-MM-DD HH:MM:SS] Message
```

### **Example Output:**

```
Enter date (day month year) for log 1: 26 4 2025
Enter time (hour minute second) for log 1: 14 30 15
Enter message for log 1: System rebooted

Enter date (day month year) for log 2: 26 4 2025
Enter time (hour minute second) for log 2: 16 45 00
Enter message for log 2: User login successful

Event Logs:
[2025-04-26 14:30:15] System rebooted
[2025-04-26 16:45:00] User login successful
```

---

## **Summary & Wrap-Up**

- Structures group different types of variables.
- Structures can be passed to functions.
- Arrays of structures are useful for managing collections.
- Enums and typedef improve code readability.
