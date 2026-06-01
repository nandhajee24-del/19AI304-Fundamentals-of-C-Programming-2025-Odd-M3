# 19AI304 - Fundamentals of C Programming - 2025 Odd - M3

## IAPR-3 - Module 3

### 5. Implementation of One-Dimensional Array and Multidimensional Array

### 6. Implementation of String Manipulation

---

# Ex.No:11

## Decimal to Binary Conversion

**Date : 12/05/2026**

## Aim

To formulate a C program to convert a decimal number into its binary equivalent and display it.

---

## Algorithm

### Step 1:

Start

### Step 2:

Include the standard input-output library:
`#include<stdio.h>`

### Step 3:

Declare variables:

* `num` → input number
* `rem` → remainder
* `binary[]` → array to store binary digits
* `i`, `k` → loop counters

### Step 4:

Read the decimal number from the user.

### Step 5:

Initialize `i = 0`.

### Step 6:

Repeat while `num > 0`:

* Divide `num` by `2`
* Store the remainder in `binary[i]`
* Increment `i`
* Update `num = num / 2`

### Step 7:

Display the binary digits in reverse order from `i-1` down to `0`.

### Step 8:

Stop

---

## Program

```c
#include<stdio.h>

int main()
{
    int num, rem, binary[32], i = 0, k;

    printf("Enter a decimal number: ");
    scanf("%d", &num);

    while(num > 0)
    {
        rem = num % 2;
        binary[i] = rem;
        i++;
        num = num / 2;
    }

    printf("Binary equivalent: ");

    for(k = i - 1; k >= 0; k--)
    {
        printf("%d", binary[k]);
    }

    return 0;
}
```

## Output

```text
Enter a decimal number: 25
Binary equivalent: 11001
```

## Result

Thus, the program was implemented and executed successfully, and the required output was obtained.

---

# Ex.No:12

## Saddle Point in a Matrix

**Date : 12/05/2026**

## Aim

To develop a C program that inputs a matrix, checks each row for its minimum element, verifies whether that element is also the maximum in its corresponding column, and displays the saddle point and its position if it exists.

---

## Algorithm

### Step 1:

Start

### Step 2:

Include the standard input-output library:
`#include<stdio.h>`

### Step 3:

Declare variables:
`i, j, k, m, min, max`
and position array `pos[2][2]`.

### Step 4:

Read the order of the square matrix `m`.

### Step 5:

Declare an `m × m` matrix and read its elements.

### Step 6:

Display the matrix.

### Step 7:

For each row `i` from `0` to `m−1`:

#### Step 7.1:

Set `min` as the first element of the row.

#### Step 7.2:

Scan the row to find its minimum element and store its position in `pos[0]`.

#### Step 7.3:

Let `j` be the column of this minimum element.

#### Step 7.4:

Set `max` as the first element of column `j`.

#### Step 7.5:

Scan column `j` to find its maximum element and store its position in `pos[1]`.

### Step 8:

Check if the row minimum equals the column maximum.

If:

* `min == max`
* positions match

then print the saddle point value and its position.

### Step 9:

Stop

---

## Program

```c
#include<stdio.h>

int main()
{
    int i, j, k, m, min, max;
    int pos[2][2];

    printf("Enter the order of matrix: ");
    scanf("%d", &m);

    int a[m][m];

    printf("Enter matrix elements:\n");

    for(i = 0; i < m; i++)
    {
        for(j = 0; j < m; j++)
        {
            scanf("%d", &a[i][j]);
        }
    }

    printf("Matrix:\n");

    for(i = 0; i < m; i++)
    {
        for(j = 0; j < m; j++)
        {
            printf("%d ", a[i][j]);
        }
        printf("\n");
    }

    for(i = 0; i < m; i++)
    {
        min = a[i][0];
        pos[0][0] = i;
        pos[0][1] = 0;

        for(j = 1; j < m; j++)
        {
            if(a[i][j] < min)
            {
                min = a[i][j];
                pos[0][0] = i;
                pos[0][1] = j;
            }
        }

        j = pos[0][1];

        max = a[0][j];
        pos[1][0] = 0;
        pos[1][1] = j;

        for(k = 1; k < m; k++)
        {
            if(a[k][j] > max)
            {
                max = a[k][j];
                pos[1][0] = k;
                pos[1][1] = j;
            }
        }

        if(min == max &&
           pos[0][0] == pos[1][0] &&
           pos[0][1] == pos[1][1])
        {
            printf("Saddle point(%d, %d) : %d",
                   pos[0][0],
                   pos[0][1],
                   min);
            return 0;
        }
    }

    printf("No saddle point found");

    return 0;
}
```

## Output

```text
Enter the order of matrix: 3
Enter matrix elements:
1 2 3
4 5 6
7 8 9

Matrix:
1 2 3
4 5 6
7 8 9

Saddle point(2, 0) : 7
```

## Result

Thus, the program was implemented and executed successfully, and the required output was obtained.

---

# Ex.No:13

## Reverse a String

**Date : 12/05/2026**

## Aim

To formulate a C program that reads a string from the user, reverses it, and prints the reversed string.

---

## Algorithm

### Step 1:

Start

### Step 2:

Include the standard input-output library:
`#include<stdio.h>`

### Step 3:

Declare two character arrays:

* `s` → input string
* `d` → reversed string

### Step 4:

Read the string using:
`scanf("%[^\n]s", s);`

### Step 5:

Find the length of the string until `'\0'`.

### Step 6:

Initialize counter `j`.

### Step 7:

Copy characters from the end of `s` to the beginning of `d`.

### Step 8:

Terminate `d` using `'\0'`.

### Step 9:

Print the reversed string.

### Step 10:

Stop

---

## Program

```c
#include<stdio.h>

int main()
{
    char s[100], d[100];
    int i = 0, j = 0, len = 0;

    printf("Enter a string: ");
    scanf("%[^\n]s", s);

    while(s[len] != '\0')
    {
        len++;
    }

    for(i = len - 1; i >= 0; i--)
    {
        d[j] = s[i];
        j++;
    }

    d[j] = '\0';

    printf("Reversed string: %s", d);

    return 0;
}
```

## Output

```text
Enter a string: Hello World
Reversed string: dlroW olleH
```

## Result

Thus, the program was implemented and executed successfully, and the required output was obtained.

---

# Ex.No:14

## Character Frequency in a String

**Date : 12/05/2026**

## Aim

To formulate a C program that accepts a string from the user and calculates the frequency of each character in the string.

---

## Algorithm

### Step 1:

Start

### Step 2:

Include the standard input-output library:
`#include<stdio.h>`

### Step 3:

Declare:

* `s[100]` → input string
* `visited[256]` → array initialized to 0
* variables `i, j, n, count`

### Step 4:

Read the string using:
`scanf("%[^\n]", s);`

### Step 5:

Find the length using `strlen(s)`.

### Step 6:

For each character:

* Check whether already counted
* Count occurrences
* Print character and frequency
* Mark as visited

### Step 7:

Repeat for all characters.

### Step 8:

Stop

---

## Program

```c
#include<stdio.h>
#include<string.h>

int main()
{
    char s[100];
    int visited[256] = {0};
    int i, j, n, count;

    printf("Enter a string: ");
    scanf("%[^\n]", s);

    n = strlen(s);

    printf("Character Frequencies:\n");

    for(i = 0; i < n; i++)
    {
        if(visited[(unsigned char)s[i]] == 0)
        {
            count = 0;

            for(j = 0; j < n; j++)
            {
                if(s[i] == s[j])
                {
                    count++;
                }
            }

            printf("%c = %d\n", s[i], count);

            visited[(unsigned char)s[i]] = 1;
        }
    }

    return 0;
}
```

## Output

```text
Enter a string: hello

Character Frequencies:
h = 1
e = 1
l = 2
o = 1
```

## Result

Thus, the program was implemented and executed successfully, and the required output was obtained.

---

# Ex.No:15

## Remove Duplicate Words from a String

**Date : 12/05/2026**

## Aim

To formulate a C program to remove duplicate words from a given string and display the string with only unique words.

---

## Algorithm

### Step 1:

Start

### Step 2:

Include the standard input-output library:
`#include<stdio.h>`

### Step 3:

Declare:

* `str` → input string
* `words` → 2D array for words

### Step 4:

Read the string using:
`scanf("%[^\n]s", str);`

### Step 5:

Split the string into words.

### Step 6:

Compare each word with all other words.

### Step 7:

Mark duplicate words.

### Step 8:

Print unique words.

### Step 9:

Stop

---

## Program

```c
#include<stdio.h>
#include<string.h>

int main()
{
    char str[100], words[50][50];
    int i, j = 0, k = 0, count = 0;

    printf("Enter a string: ");
    scanf("%[^\n]s", str);

    for(i = 0; str[i] != '\0'; i++)
    {
        if(str[i] == ' ')
        {
            words[j][k] = '\0';
            j++;
            k = 0;
        }
        else
        {
            words[j][k] = str[i];
            k++;
        }
    }

    words[j][k] = '\0';
    count = j + 1;

    for(i = 0; i < count; i++)
    {
        for(j = i + 1; j < count; j++)
        {
            if(strcmp(words[i], words[j]) == 0)
            {
                words[j][0] = '\0';
            }
        }
    }

    printf("String with unique words:\n");

    for(i = 0; i < count; i++)
    {
        if(words[i][0] != '\0')
        {
            printf("%s ", words[i]);
        }
    }

    return 0;
}
```

## Output

```text
Enter a string: this is is a test test

String with unique words:
this is a test
```

## Result

Thus, the C program to remove duplicate words from a given string and display only unique words was successfully executed. Thus, the program was implemented and executed successfully, and the required output was obtained.
