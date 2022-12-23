# 0002 Rust: Simple "Hello World" project with cargo
### Rust Language Learning Module

## Goal Statement
1. Create a project using cargo
2. compile and run a rust program, using "cargo"

## File Tree
```
$ tree
```
#### Output
```
[username@system projects]$ tree
.
└── hello
    ├── Cargo.toml
    └── src
        └── main.rs
```

## File name: main.rs
```
$ nano src/main.rs 
```
## File contents
```
fn main(){
    println!("Hello, world!");
}
```

## compile
```
[username@system projects]$ cargo run

```
#### Output
```
[username@system projects]$ cargo run
   Compiling hello v0.1.0 (/home/projects/hello)
    Finished dev [unoptimized + debuginfo] target(s) in 1.07s
     Running `target/debug/hello`
Hello, world!
```


## Notes:
- executable file is in directory named -> debug
- name of executable file is set in -> Cargo.toml
- source code file is in directory named -> src

