# Rust

Rust is a fast, reliable, and productive language for building software on embedded devices, web services, and more.

## Installation

```bash
> curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
``` 

## Commands

Native Compilation :
```
> rustc file.rs
```

Create a new rust project : 
```
> cargo new name_of_the_project
```

Compilation and build dependencies:
```
> cargo build
(create a target folder and Cargo.lock)
Or :
> cargo run
```

Check Cargo project:
```
> cargo check
```

## Variables


## Arithmetic and type-casting


## Data types


## Conditions, control flow


## Functions, expressions and statements



## Memory Management

The **borrow checker** analyze the code and check for memory safety.
-> So optimal performance and memory safety

### Ownership

- Each value in Rust as an owner
- There can only be one owner at a time

```Rust
    fn main() {
        let s1 = String::from("Let's get Rusty!");
        let s2 = s1;
        println("{s1}"); // error : borrow of moved value s1
    }
```
s2 is now the owner of the allocated string, to compile we can print s2 or clone s1
with *s1.clone* .Moving value also applies to functions. 

So rust ownership ensure that memory is automatically cleaned up.


#### Borrowing

Creating references is called **borrowing**, because it borrows access to the
data from the owner without taking ownership (same as real life).

Example :

```Rust
    fn main() {
        let s1 = String:: from("Let's Get Rusty!");
        print_string(&s1);
        print_string(&s1);
    }

    fn print_string(s: &str) {
        println!("{s}");
    }
```

- At any given time you can have either one mutable reference or any nb of 
immutable reference. (mut notation).


```Rust
    fn main() {
        let mut x = vec![1, 2, 3];
        
        let last = x.last().unwrap();
        x.push(4); // error : cannot borrow 'x' as mutable already borrowed as immutable
        
        println!("{:?}", last);
    }
```

- References must always be valid 




