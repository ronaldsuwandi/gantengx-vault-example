This is the centralized concept in [[Rust]]. It's a set of rules that governs how Rust manages memory. Instead of using garbage collection like in [[Java]] [[Javascript]] [[Golang]] or manual allocation/deallocation in C/C++. Rust implement the third approach using ownership concept

Memory is managed through system of ownership and the compiler will check. If any of the rules are violated, the program will not compile

> [!important] Ownership rules
> 1. Each value in Rust has an **owner**
> 2. There can only be **one owner** at a time
> 3. When owner goes out of scope, the value will be dropped


> [!Tip] Terminology
> Rust reserves the term "copy" for stack only, whereas "clone" is used when there is heap involved (cloning a string - since string is stored in heap)

## Ownership and Functions
The mechanics of passing value to a function are similar to assigning in variable (see: [[Rust memory allocation]] for more details). Passing variable into function will move or copy, the same as assignment

```rust
fn main() {
	let s = String::from("hello");
	takes_ownership(s);
	let x = 5;
	makes_copy(5);
}

fn takes_ownership(some_string: String) {
	println!("{}", some_string);
}

fn makes_copy(some_number: i32) {
	println!("{}", some_number);
}
```

Once `takes_ownership` function is called, the main function will no longer have access to `s`. If you still need to access, you can call `takes_ownership(s.clone())` instead

## Return values and Scope
Returning values can also transfer ownership. See the following snippet

```rust
fn main() {
    let s1 = gives_ownership();
    let s2 = String::from("hello");
    let s3 = takes_and_gives_back(s2);
}

fn gives_ownership() -> String {
    let some_string = String::from("yours");
	some_string
}

fn takes_and_gives_back(a_string: String) -> String {
    a_string
}
```

Ownership of a variable follow the same pattern every time: assigning value to another variables moves it. When variable that includes data on the heap goes out of scope, the value will be cleaned up by `drop` unless ownership of data has been moved to another variable

Function `gives_ownership` basically move its return value into the function that calls it and transfer the ownership

Function `takes_and_gives_back` basically takes the ownership of the variable and returning it. It's quite tedious because every time you pass the variable it will moves the variables. Instead of passing by values, you can use [[References and Borrowing in Rust|references]] so that Rust doesn't have to transfer ownership

## See also
- [[Ownership of struct data]]