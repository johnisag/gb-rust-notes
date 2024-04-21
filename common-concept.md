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

```rust
use std::io;

fn main() {
    // we need type annotation here to avoid ambiguity
    let guess: u32 = "42".parse().expect("Not a number!");
    println!("{:?}", guess);

    // scalar types
    let x = 2.0; // f64
    let y: f32 = 3.0; // f32

    println!("{:?}", x);
    println!("{:?}", y);

    // numeric operations
    let sum = 5 + 10;
    let difference = 95.5 - 4.3;
    let product = 4 * 30;
    let quotient = 56.7 / 32.2;
    let truncated_quotient = 5 / 3; // 1
    let remainder = 43 % 5;

    println!("{:?}", sum);
    println!("{:?}", difference);
    println!("{:?}", product);
    println!("{:?}", quotient);
    println!("{:?}", truncated_quotient);
    println!("{:?}", remainder);

    // boolean type
    let t = true;
    let f: bool = false;

    println!("{:?}", t);
    println!("{:?}", f);

    // character type
    let c = 'z';
    let z: char = 'ℤ';

    println!("{:?}", c);    
    println!("{:?}", z);

    // compound types

    // tuple type (fixed length): can have different types
    // tuple is allocated on stack
    let tup: (i32, f64, u8) = (500, 6.4, 1);
    let (x, _y, _z) = tup;

    println!("{:?}", x);

    let five_hundred = tup.0;
    let _six_point_four = tup.1; // underscore to avoid warning of unused variable

    println!("{:?}", five_hundred);

    // array type (fixed length): must have same type
    // array is allocated on stack
    // when you know the length of an array at compile time, you can use an array
    let a = [1, 2, 3, 4, 5];
    let _first = a[0];
    let _second = a[1];

    println!("{:?}", a);

    let b = [3; 5]; // [3, 3, 3, 3, 3]

    println!("{:?}", _first);
    println!("{:?}", _second);
    println!("{:?}", b);

    let aa = [1, 2, 3, 4, 5];

    println!("{:?}", aa[0]);

    let mut index = String::new();

    io::stdin()
        .read_line(&mut index)
        .expect("Failed to read line");

    let index: usize = index.trim().parse().expect("Not a number!");

    println!("{:?}", aa[index]);
}

// compile with `rustc common-prog/dtype.rs`
// run with `./dtype`
```

