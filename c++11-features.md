## Language Features
- [x] Attributes : 
```
Compiling a valid program with all instances of a particular attribute ignored must result in a correct implementation of the original program

Often used to give compiler warnings and optimizing performance.
```
```
#include <iostream> 
#include <string> 
  
[[noreturn]] void f() 
{ 
    // Some code that does not return 
    // back the control to the caller 
    // In this case the function returns 
    // back to the caller without a value 
    // This is the reason why the 
    // warning "noreturn' function does return' arises 
} 
  
void g() 
{ 
    std::cout << "Code is intented to reach here"; 
} 
  
int main() 
{ 
    f(); 
    g(); 
} 
Returns:
main.cpp: In function 'void f()':
main.cpp:8:1: warning: 'noreturn' function does return
 }
 ^
```

- [ ] constexpr : 
```
constexpr specifies that the value of an object or a function can be evaluated at compile time and the expression can be used in other constant expressions. 
```
```
// constexpr function for product of two numbers. 
// By specifying constexpr, we suggest compiler to  
// to evaluate value at compiler time 
constexpr int product(int x, int y) 
{ 
    return (x * y); 
} 
  
int main() 
{ 
    const int x = product(10, 20); 
    cout << x; 
    return 0; 
} 
```
