C++14 Features: https://en.cppreference.com/w/cpp/compiler_support

## Language Features
- [x] Binary literals: https://github.com/AnthonyCalandra/modern-cpp-features#binary-literals
- [x] Digit separators: https://en.wikipedia.org/wiki/C%2B%2B14#Digit_separators
- [x] Generic lambda expressions: https://github.com/AnthonyCalandra/modern-cpp-features#generic-lambda-expressions
- [x] Lambda capture initialisers (init-capture): https://github.com/AnthonyCalandra/modern-cpp-features#lambda-capture-initializers
- [x] Return type deduction for normal functions: https://en.wikipedia.org/wiki/C%2B%2B14#Function_return_type_deduction
- [x] decltype(auto) - Alternate type deduction on declaration:
https://github.com/AnthonyCalandra/modern-cpp-features#decltypeauto
trailing types: https://www.ibm.com/developerworks/community/blogs/5894415f-be62-4bc0-81c5-3956e82276f3/entry/introduction_to_the_c_11_feature_trailing_return_types?lang=en
proposal: http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3638.html
- [x] Relaxing constraints on constexpr functions: https://github.com/AnthonyCalandra/modern-cpp-features#relaxing-constraints-on-constexpr-functions https://www.modernescpp.com/index.php/constexpr-functions
- [x] Variable templates http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3651.pdf
- [x] [[deprecated]] attribute: https://josephmansfield.uk/articles/marking-deprecated-c++14.html
- [x] Aggregate member initialisation https://stackoverflow.com/questions/4178175/what-are-aggregates-and-pods-and-how-why-are-they-special/27511360#27511360 https://en.cppreference.com/w/cpp/language/aggregate_initialization
Super concise example from the proposal: http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3653.html
- [x] Tweaked wording for contextual conversions
- [x] Clarifying memory allocation: This one is just about making some wording in the standard documents non-ambiguous: http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3664.html
- [x] Sized deallocation: See 3.7.4 Dynamic storage duration in http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3778.html; 
An extra method for declaring a delete operator was added. You can declare a global delete operator that takes a `void*` to the memory you want to delete as well as the size of that memory. Useful in low-level use cases, e.g. when working with HW sensors or in embedded contexts (we think).

## Library Features:
- [x] User-defined literals for standard library types, \<chrono\> and \<string\>: https://en.cppreference.com/w/cpp/chrono/operator%22%22s
```
C++11 added user-defined literals, but didn’t use them in the standard library. Now some very useful and popular ones work:

auto a_string = "hello there"s;   // type std::string
auto a_minute = 60s;              // type std::chrono::duration = 60 seconds
auto a_day    = 24h;              // type std::chrono::duration = 24 hours
Note s means “string” when used on a string literal, and “seconds” when used on an integer literal, without ambiguity.
```
- [x] Compile-time integer sequences: std::integer_sequence: https://github.com/AnthonyCalandra/modern-cpp-features#user-defined-literals-for-standard-library-types

  * Example1: https://en.cppreference.com/w/cpp/utility/integer_sequence
  * Example2: https://stackoverflow.com/questions/41660062/how-to-construct-an-stdarray-with-index-sequence

- [x] Std::make_unique
```
std::unique_ptr<SomeObject> a = new SomeObject(...)

Accomplishes the same thing as: 
std::unique_ptr<SomeObject> a = std::make_unique(SomeObject(...))

However, make_unique() is preferable because it forces the creation and deletion of the unique_ptr to be atomic and prevents a few cases which might result in a memory leak. 
```
  * Example of memory leak: https://www.learncpp.com/cpp-tutorial/15-5-stdunique_ptr/

- [x] Shared timed mutexes and locking: std::shared_timed_mutex

    * Documentation for `std::shared_timed_mutex`: https://en.cppreference.com/w/cpp/thread/shared_timed_mutex
    * interesting trivia on why `std:shared_timed_mutex` was added in c++14 but `std::shared_mutex` only in c++17 https://stackoverflow.com/questions/40207171/why-shared-timed-mutex-is-defined-in-c14-but-shared-mutex-in-c17

- [x] Heterogeneous lookup in associative containers

Wikipedia has a good explanation: https://en.wikipedia.org/wiki/C%2B%2B14#Heterogeneous_lookup_in_associative_containers

A comprehensive example is given in this blog post: https://www.bfilipek.com/2019/05/heterogeneous-lookup-cpp14.html

- [x] Tuple addressing via type: std::get\<T\>()

Gets an element by type. Raises a compilation error if you there is more than one of the same type in the tuple.
https://en.wikipedia.org/wiki/C%2B%2B14#Tuple_addressing_via_type

- [ ] Constexpr for: \<chrono\>, \<complex\>, \<array\>, \<init_list\>, \<utility\>, \<tuple\>
- [x] Improved std::integral_constant

The `std::integral_constant`'s value can now be retrieved also using an `operator()`.
```
using two_t = std::integral_constant<int, 2>;
using four_t = std::integral_constant<int, 4>;

// Old option
static_assert(two_t::value*2 == four_t::value, "2*2 != 4");

// New option
static_assert(two_t()*2 == four_t(), "2*2 != 4");
```
`std::integral_constant` is used for metaprogramming: https://en.cppreference.com/w/cpp/types/integral_constant

- [ ] Null forward iterators
- [ ] Std::quoted
http://www.open-std.org/JTC1/sc22/WG21/docs/papers/2013/n3654.html
- [ ] std::exchange
- [ ] “Fixing constexpr member functions without const”
- [ ] Dual-Range std::equal, std::is_permutation, std::mismatch
