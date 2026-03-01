In [[Rust]] you can shadow variable. It's a different semantics from mutating variable

```rust
fn main() {
	let x = 100;
	let x = "abc";
	println!("{x}");
}
```

In the first example it's allowed, you can even change the type with shadowing

```rust
fn main() {
	let x = 100;
	x = 50; // not allowed (not mutable)
	x = "abc"; // not allowed
}
```
