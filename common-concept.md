# Common Concept

### [Variables and Mutability](https://doc.rust-lang.org/book/ch03-01-variables-and-mutability.html#variables-and-mutability) <a href="#variables-and-mutability" id="variables-and-mutability"></a>

```rust
fn main() {
    let mut x = 5;
    println!("The value of x is: {x}");
    x = 6;
    println!("The value of x is: {x}");
}
```

```rust
const THREE_HOURS_IN_SECONDS: u32 = 60 * 60 * 3;
```

```rust
fn main() {
    let x = 5;

    let x = x + 1;

    {
        let x = x * 2;
        println!("The value of x in the inner scope is: {x}");
    }

    println!("The value of x is: {x}");
}
```

### [Data Types](https://doc.rust-lang.org/book/ch03-02-data-types.html#data-types) <a href="#data-types" id="data-types"></a>



