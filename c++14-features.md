C++14 Features

## Language Features
- [x] Binary literals: https://github.com/AnthonyCalandra/modern-cpp-features#binary-literals
- [x] Digit separators: https://en.wikipedia.org/wiki/C%2B%2B14#Digit_separators
- [x] Generic lambda expressions: https://github.com/AnthonyCalandra/modern-cpp-features#generic-lambda-expressions
- [x] Lambda capture initialisers (init-capture): https://github.com/AnthonyCalandra/modern-cpp-features#lambda-capture-initializers
- [x] Return type deduction for normal functions: https://en.wikipedia.org/wiki/C%2B%2B14#Function_return_type_deduction
- [ ] decltype(auto) - Alternate type deduction on declaration:
https://github.com/AnthonyCalandra/modern-cpp-features#decltypeauto
- [x] Relaxing constraints on constexpr functions: https://github.com/AnthonyCalandra/modern-cpp-features#relaxing-constraints-on-constexpr-functions https://www.modernescpp.com/index.php/constexpr-functions
- [x] Variable templates http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3651.pdf
- [x] [[deprecated]] attribute: https://josephmansfield.uk/articles/marking-deprecated-c++14.html
- [x] Aggregate member initialisation https://stackoverflow.com/questions/4178175/what-are-aggregates-and-pods-and-how-why-are-they-special/27511360#27511360 https://en.cppreference.com/w/cpp/language/aggregate_initialization
Super concise example from the proposal: http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3653.html
- [ ] Tweaked wording for contextual conversions
- [x] Clarifying memory allocation: This one is just about making some wording in the standard documents non-ambiguous: http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3664.html
- [x] Sized deallocation: See 3.7.4 Dynamic storage duration in http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3778.html; 
An extra method for declaring a delete operator was added. You can declare a global delete operator that takes a `void*` to the memory you want to delete as well as the size of that memory. Useful in low-level use cases, e.g. when working with HW sensors or in embedded contexts (we think).

## Library Features:
- [ ] User-defined literals for standard library types, \<chrono\> and \<string\>
```
C++11 added user-defined literals, but didn’t use them in the standard library. Now some very useful and popular ones work:

auto a_string = "hello there"s;   // type std::string
auto a_minute = 60s;              // type std::chrono::duration = 60 seconds
auto a_day    = 24h;              // type std::chrono::duration = 24 hours
Note s means “string” when used on a string literal, and “seconds” when used on an integer literal, without ambiguity.
```
- [ ] Compile-time integer sequences: std::integer_sequence
- [ ] Std::make_unique
```
std::unique_ptr<SomeObject> a = new SomeObject(...)

Accomplishes the same thing as: 
std::unique_ptr<SomeObject> a = std::make_unique(SomeObject(...))

However, make_unique() is preferable because... {need to finish understanding...}

- [ ] Shared mutexes and locking: std::shared_timed_mutex
- [ ] Heterogeneous lookup in associative containers
- [ ] Tuple addressing via type: std::get\<T\>()
- [ ] Constexpr for: \<chrono\>, \<complex\>, \<array\>, \<init_list\>, \<utility\>, \<tuple\>
- [ ] Improved std::integral_constant
- [ ] Null forward iterators
- [ ] Std::quoted
- [ ] std::exchange
- [ ] “Fixing constexpr member functions without const”
- [ ] Dual-Range std::equal, std::is_permutation, std::mismatch
