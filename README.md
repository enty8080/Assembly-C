# Assembly-C
Tutorial how to combine assembly and C++

**foo.S:**

```nasm
section .text
global _foo
_foo:
    mov eax, 1
    ret
```

**main.cc:**

```cpp
#include <iostream>

extern "C" int foo(void);

int main(void)
{
    std::cout << foo() << std::endl;
    return 0;
}
```

> nasm -f elf64 foo.S

> g++ main.cc foo.o

> ./a.out

```
1
```
