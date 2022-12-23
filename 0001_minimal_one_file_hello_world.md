# 0001 Rust: One-File Minimal "Hello World"
### Rust Language Learning Module

## Goal Statement
compile and run a rust program, using a minimal one-file method
note: not using "cargo"

## File Tree
```
$ tree
```
#### Output
```
[username@system projects]$ tree
.
└── temp
    ├── hello
    └── hello.rs

```

## File name: hello.rs
```
$ nano hello.rs
```
## File contents
```
fn main(){
    println!("Hello, world!");
}
```

## compile
```
[username@system projects]$ rustc hello.rs

```
#### Output
```
Hello, world!
```


