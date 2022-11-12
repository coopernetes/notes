# Thorny parts of Rust
Jotting down some parts of the language that are still a bit too esoteric for
me to remember every time. Namely, odd syntax.

## Range expression

`start..=end`

```rust
// from the rand crate
use rand::Rng;

let secret_number = rand::thread_rng().gen_range(1..=100); // 1 - 100 inclusive
```

## Macros

`macro_name!`

```rust
println!("Hello world!");
```

## Format strings

`"My literal contains {a_var}"`

```rust
println!("It can also include {} and {}", foo, bar);

let x = ...; // some non-primitive
println!("Convert {:?} to str", x);
```

## Propagate errors

https://doc.rust-lang.org/book/ch09-02-recoverable-errors-with-result.html#a-shortcut-for-propagating-errors-the--operator

`x.get_something()?;`

```rust
fn main() -> Result<Anything, io::Error> {
    let x = some_call(...)?;         // if some_call()'s Result is Err, propagate it up to main()'s caller
    let y = match some_call(...) {   // Both are functionally the same
        Ok(ok_value) => ok_value     // ok_value is assigned to y
        Err(e) => return Err(e)
    };
    Ok(())
}
```

## Apostrophe

https://doc.rust-lang.org/stable/book/ch10-03-lifetime-syntax.html#lifetime-annotation-syntax

```rust
&i32        // a reference
&'a i32     // a reference with an explicit lifetime
&'a mut i32 // a mutable reference with an explicit lifetime
```
