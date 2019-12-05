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
- [ ] Variable templates http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3651.pdf
- [x] [[deprecated]] attribute: https://josephmansfield.uk/articles/marking-deprecated-c++14.html
- [ ] Aggregate member initialisation https://stackoverflow.com/questions/4178175/what-are-aggregates-and-pods-and-how-why-are-they-special/27511360#27511360 https://en.cppreference.com/w/cpp/language/aggregate_initialization
- [ ] Tweaked wording for contextual conversions
- [ ] Clarifying memory allocation: This one is just about making some wording in the standard documents non-ambiguous: http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3664.html
- [ ] Sized deallocation: See 3.7.4 Dynamic storage duration in: http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3778.html 

## Library Features:
- [ ] User-defined literals for standard library types, \<chrono\> and \<string\>
- [ ] Compile-time integer sequences: std::integer_sequence
- [ ] Std::make_unique
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
