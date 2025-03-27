# W3 Answers

### 🔍 Exercise 1: Wallet Tracker (5 min)

Write a program that asks the user to enter how much money they want to add and how much they want to spend. Then calculate and print the remaining amount in the wallet.

**Requirements:**

- Use `+=` and `=` operators
- Start wallet balance from 0

```c
#include <stdio.h>

int main(void)
{
    int wallet = 0, add, spend;
    printf("Enter money to add: ");
    scanf("%d", &add);
    printf("Enter money to spend: ");
    scanf("%d", &spend);

    wallet += add;
    wallet -= spend;

    printf("Remaining: %d\n", wallet);
    return 0;
}
```

---

### 🔍 Exercise 2: Last Digit Extractor (10 min)

Write a program that asks the user to enter an integer number, then prints the last digit of that number using the modulus operator.

**Requirements:**

- Use `%` to extract the last digit
- Assume the user enters a valid integer

```c
#include <stdio.h>

int main(void)
{
    int num;
    printf("Enter a number: ");
    scanf("%d", &num);
    int last = num % 10;
    printf("Last digit: %d\n", last);
    return 0;
}
```

---

### 🔍 Exercise 3: Score Calculation (5 min)

Write a program to calculate a score in two ways:

1. Without parentheses: `base + bonus * level`
2. With parentheses: `(base + bonus) * level` Compare the results and explain why they are different.

**Requirements:**

- Use `int` variables
- Use , `+`, and parentheses
- Show both calculations in output

```c
#include <stdio.h>

int main(void)
{
    int base = 100, bonus = 20, level = 3;
    int score1 = base + bonus * level;
    int score2 = (base + bonus) * level;

    printf("Score1: %d\n", score1);
    printf("Score2: %d\n", score2);
    return 0;
}
```

---

### 🔍 Exercise 4: Countdown (5 min)

Write a program that asks the user to input a number, and then prints numbers from that number down to 1 using a while loop.

**Requirements:**

- Use a `while` loop
- Start from the input number and print down to 1
- Use the `--` operator

```c
#include <stdio.h>

int main(void)
{
    int n;
    printf("Enter a number to countdown from: ");
    scanf("%d", &n);
    while (n >= 1)
    {
        printf("%d\n", n);
        n--;
    }
    return 0;
}
```

---

### 🔍 **Exercise 5: Highest and Lowest Score Finder (10 min)**

Write a program that repeatedly asks the user to enter scores.

The loop stops when the user enters a **negative number**.

At the end, the program prints the **highest** and **lowest** scores entered.

### **Requirements**

- Use a `do-while` loop
- Do **not** use `if` statements
- Use logical expressions (e.g. `(score > max) * score + ...`)
- Track the total number of scores entered

```c
#include <stdio.h>

int main(void)
{
    int score;
    int count = 0, max, min;

    printf("Enter a score (negative to stop): ");
    scanf("%d", &score);

    max = min = score;

    do
    {
        max = (score > max) * score + (score <= max) * max;
        min = (score < min) * score + (score >= min) * min;
        count++;

        printf("Enter a score (negative to stop): ");
        scanf("%d", &score);

    } while (score >= 0);

    printf("You entered %d scores.\n", count);
    printf("Highest score: %d\n", max);
    printf("Lowest score: %d\n", min);

    return 0;
}
```
