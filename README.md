# ft\_printf

> Because `ft_putstr()` and `ft_putnbr()` aren’t enough.

## 📌 Project Description

This project is part of the 42 Common Core and challenges students to reimplement the standard `printf()` function from C’s standard library.

The goal is to create a custom function `ft_printf()` that replicates the behavior of `printf()`, handling formatted output with a variable number of arguments. It must support a subset of format specifiers and work with C’s variadic functions using `stdarg.h`.

Once complete, the project helps solidify skills in:

* Memory and string manipulation
* Variadic functions
* Formatted output
* Code structure and modularization

## 🔧 Features Implemented

The `ft_printf()` function supports the following format specifiers:

| Format | Description              |
| ------ | ------------------------ |
| `%c`   | Character                |
| `%s`   | String                   |
| `%p`   | Pointer address (hex)    |
| `%d`   | Signed decimal integer   |
| `%i`   | Signed decimal integer   |
| `%u`   | Unsigned decimal integer |
| `%x`   | Lowercase hexadecimal    |
| `%X`   | Uppercase hexadecimal    |
| `%%`   | Literal percent sign     |

## 📘 What I Learned

### Variadic Functions

I discovered how C handles functions with an unknown number of arguments using `va_list`, `va_start`, `va_arg`, and `va_end`. This was key to implementing `ft_printf()` and understanding how format strings are parsed and arguments consumed in order.

### String and Buffer Handling

Managing strings, especially when converting numbers to different bases and handling pointer formatting (`%p`), helped strengthen my grasp of pointer arithmetic, memory formatting, and safety.

### Precision in Output Formatting

Correctly handling edge cases and matching the output of the real `printf()` taught me to pay attention to the smallest formatting details—like null pointers, empty strings, and number alignment.

## 😓 Challenges Faced

### `%p` (Pointer Formatting)

* **Challenge:** Properly formatting the memory address of a pointer, handling `NULL`, and making sure the `0x` prefix is correctly added.
* **Lesson Learned:** I had to write a helper function to convert the pointer to hexadecimal and learned to cast properly from `void *` to `uintptr_t` or `unsigned long`.

### `%x` / `%X` (Hexadecimal)

* **Challenge:** Implementing case-sensitive hexadecimal output and managing base conversion for unsigned integers.
* **Lesson Learned:** I reused a base conversion function and modified it to output upper/lowercase letters depending on the specifier.

### Modularizing Code

* **Challenge:** Keeping the `ft_printf` code clean and modular while managing multiple specifiers.
* **Lesson Learned:** I separated logic into small, specific functions (e.g., `print_char`, `print_string`, `print_pointer`, `print_number`) to maintain readability and make debugging easier.

### Memory Safety

* **Challenge:** Avoiding segmentation faults and ensuring all dynamically allocated memory (if any) is freed.
* **Lesson Learned:** I rigorously tested edge cases and integrated `valgrind` into my workflow to check for leaks.

## 🛠️ Compilation

To compile the library and a test program:

```bash
make
```

This will generate `libftprintf.a`, which can be linked into your C programs.
