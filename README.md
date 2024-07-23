# 🖋️ **ft_printf**

## 📖 **About**

Welcome to my implementation of the `ft_printf` function, a pivotal part of the 42 School curriculum. `ft_printf` is a formatted output conversion function, similar to the standard `printf` function in C, but customized to enhance flexibility and functionality. It allows you to print various types of data to the standard output with specified formats.

---

## 🎯 **Functionality**

`ft_printf` supports a wide range of format specifiers and flags to format the output. Below is a detailed breakdown:

### 🔠 **Format Specifiers**

- **%c**: Prints a single character.
  - **Prototype**: `int ft_printf(const char *format, ...);`
  - **Example**:
    ```c
    ft_printf("Character: %c\n", 'A');
    // Output: Character: A
    ```

- **%s**: Prints a string.
  - **Example**:
    ```c
    ft_printf("String: %s\n", "Hello, world!");
    // Output: String: Hello, world!
    ```

- **%d** or **%i**: Prints a signed decimal integer.
  - **Example**:
    ```c
    ft_printf("Integer: %d\n", 42);
    // Output: Integer: 42
    ```

- **%u**: Prints an unsigned decimal integer.
  - **Example**:
    ```c
    ft_printf("Unsigned integer: %u\n", 42);
    // Output: Unsigned integer: 42
    ```

- **%x**: Prints an unsigned hexadecimal integer (lowercase).
  - **Example**:
    ```c
    ft_printf("Hexadecimal: %x\n", 255);
    // Output: Hexadecimal: ff
    ```

- **%X**: Prints an unsigned hexadecimal integer (uppercase).
  - **Example**:
    ```c
    ft_printf("Hexadecimal: %X\n", 255);
    // Output: Hexadecimal: FF
    ```

- **%p**: Prints a pointer address.
  - **Example**:
    ```c
    int *ptr = (int*)0x7ffeefbff5c8;
    ft_printf("Pointer: %p\n", ptr);
    // Output: Pointer: 0x7ffeefbff5c8
    ```

- **%%**: Prints a literal percent sign.
  - **Example**:
    ```c
    ft_printf("Percent sign: %%\n");
    // Output: Percent sign: %
    ```

---

## 🚀 **Usage**

To use `ft_printf` in your projects, include the `ft_printf.h` header file and link your project with the `libftprintf.a` static library. Then, you can start using the `ft_printf` function in your code.


## 🛠️ **va_start and va_arg**

The 'ft_printf' function uses the 'stdarg.h' library to handle variable arguments. Two key macros are essential for this process:

**'va_start'**
-   *Description:* Initializes the variable argument list.
-   *Prototype:* void va_start(va_list ap, last_param);
-   *Usage:* This macro must be called before accessing any variable arguments. The 'last_param' is the last named parameter before the ellipsis (...) in the function definition.
-   *Example:*
```c
#include <stdarg.h>

void example_function(int fixed, ...)
{
    va_list args;
    va_start(args, fixed);
    // Access variable arguments
    va_end(args);
}
 ```

**'va_arg'**
-   *Description:*: Retrieves the next argument in the variable argument list.
-   *Prototype:*: type va_arg(va_list ap, type);
-   *Usage:* This macro is used to access each additional argument in the list. The type specifies the type of the next argument to retrieve.
-   *Example:*
```c
#include <stdarg.h>

void example_function(int fixed, ...)
{
    va_list args;
    va_start(args, fixed);
    int num = va_arg(args, int);
    char ch = va_arg(args, int); // Note: char is promoted to int
    va_end(args);
}
 ```

These macros are crucial for iterating through the variable arguments provided to 'ft_printf'.

### 📚 **Example**

```c
#include "ft_printf.h"

int main() 
{
    ft_printf("Character: %c\n", 'A');
    ft_printf("String: %s\n", "Hello, world!");
    ft_printf("Integer: %d\n", 42);
    ft_printf("Unsigned: %u\n", 42);
    ft_printf("Hex (lower): %x\n", 255);
    ft_printf("Hex (upper): %X\n", 255);
    ft_printf("Pointer: %p\n", (void *)0x7ffeefbff5c8);
    ft_printf("Percent: %%\n");
    return 0;
}
 ```

### 🙏 **Credits**
This `README.md` includes all the essential details, explanations, and code examples in a well-structured and visually appealing format. Feel free to modify or expand upon it as needed!
