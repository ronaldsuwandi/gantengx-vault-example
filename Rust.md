Typesafe and non-GC based language. So there is no garbage collection performance penalty and it is memory safe

Unlike C where it uses manual memory management, Rust ensures memory safety through combination of ownership, borrowing and lifetime system

==Rust does not have null concept==

Another important point of Rust is that it does not perform type-erasure on generics. Rather it performs "monomorphization" which basically generate the code of the types that accessing the generics. So if you have `Option<T>` and use both `i32` and `f32` in your code, then it will generate both `Option_i32` and `Option_f32` so there is no runtime penalty and the code will be performant. Downside is that it will have bigger binary if you use plenty of type for the generics

Head over to [[Rust Design Patterns]] for more idioms and best practices summarised from the book

## Basic
- [[Shadowing variable in rust]]
- [[Const in Rust]]
- [[isize and usize in Rust]]
- [[Arrays in Rust]]
- [[Integer overflow in Rust]]
- [[Expression and statement in Rust]]
- [[Loop in Rust]]

## Ownership and memory allocation
- [[Ownership concept]]
- [[Rust memory allocation]]
- [[References and Borrowing in Rust]]
- [[Borrower cannot move value]]
- [[Slice in Rust]]
- [[Ownership of function argument]]
- [[Fixing common ownership error in Rust]]

## Struct
- [[Mutable struct in Rust applies to entire instance]]
- [[Struct shortcuts in Rust]]
- [[Ownership of struct data]]
- [[How to derive traits in a struct]]
- [[Associated functions in Rust]]

## Enums & Pattern matching
- [[Enums in Rust can have different types]]
- [[Option enum]]
- [[Use if let expression for concise control flow]]

## Modules
- [[Module convention in Rust]]
- [[Use nested paths to clean up large use lists]]

## String
- [[String format! vs add]]
- [[String internal representation in Rust]]
- [[Difference between String and &str]]

## Error handling
- [[Best practice to use error in Rust]]
- [[Propagate error using question mark operator]]
- [[When to use panic! or Result]]

## Traits and Lifetimes
- [[Trait]]
- [[Common Traits]]
- [[Trait usage]]
- [[Lifetimes]]
- [[Supertraits]]

## Closures
- [[Closure syntax]]
- [[Closure reference and ownership]]
- [[Closure and Fn traits]]
- [[Double pointer in Rust closure]]
- [[Closure iterators are lazily evaluated]]
- [[Rust iterators are zero-cost abstractions]]
- [[iter vs into_iter]]
- [[Use drain to empty collection without consuming the collection]]
- [[Async closure is not stable and better to simplify code to avoid Pin and Box]]

## Testing
- [[Unit test in Rust]]
- [[Integration test in Rust]]
- [[Benchmarking in Rust]]

## Smart Pointers
- [[Smart pointers]]
- [[Box to point data on the heap]]
- [[Dropping value early with std-mem-drop]]
- [[Use Rc for reference counted smart pointer]]
- [[RefCell and interior mutability pattern]]
- [[How to choose between Box, Rc or RefCell]]
- [[Having multiple owners of mutable data by combining Rc and RefCell]]
- [[References cycles can leak memory]]
- [[Rust needs to know size of types at compile time]]

## Concurrency
- [[Thread in Rust]]
- [[Using move Closures with thread]]
- [[Message passing to transfer data between threads]]
- [[Channel and ownership]]
- [[Do not use mpsc for channels]]
- [[Use receiver as iterator]]
- [[How to create multiple producers in Rust]]
- [[Concurrency by sharing state in Rust]]
- [[Atomic reference counting with Arc]]
- [[RefCell, Rc, Mutex, Arc]]
- [[Concurrency with Sync and Send traits]]

## Object Oriented Features
- [[Using Trait objects]]
- [[Why do we need to wrap dyn trait with Box]]

## Advanced Rust
- [[Associated Types]]
- [[Default generic type parameters]]
- [[Operator overloading in Rust]]
- [[Use fully qualified syntax to avoid disambiguation when calling method with same name]]
- [[Supertraits]]
- [[Never type in Rust]]
- [[Dynamically Sized Types and Sized trait]]
- [[Returning closure]]
- [[Summary on how async Rust work]]
- [[What does Pin do in Rust]]
- [[self vs Self]]

## Macros
- [[Two type of macros in Rust]]
- [[Macros must be defined into scope]]
- [[Declarative macros with macro_rules in Rust]]
- [[Procedural macros in Rust]]

## Conversion
- [[Using AsRef and AsMut trait]]
- [[Using Into and From trait]]
- [[When to use Into, From, AsRef and AsMut]]
- [[Type casting using as keyword]]

## See also
- [[Rust Design Patterns]]
- [[Asynchronous Programming in Rust]]
- [[Logging in Rust]]
- [[Tokio]]

## References
- [Rust Book](https://doc.rust-lang.org/book/title-page.html)
- [Rustonomicon - Unsafe Rust](https://doc.rust-lang.org/nomicon/intro.html)
- [Rust Macros](https://veykril.github.io/tlborm/introduction.html)
- [Rust Design Patterns](https://rust-unofficial.github.io/patterns/)
