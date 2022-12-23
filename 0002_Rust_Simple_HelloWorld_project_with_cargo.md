# 0002 Rust: Simple "Hello World" project with cargo
### Rust Language Learning Module

## Goals
1. Create a project using cargo
2. Compile and run a rust program, using "cargo"

## Use Cargo: Create Project
```
$ cargo new hello
```

## Change working directory: Go into new 'hello' [project] folder
```
$ cd hello
```

## File Tree
Look at the files and file-structure of files and folders created by cargo.
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

## Examine source code file
File name: main.rs
```
$ nano src/main.rs 
```
## File contents
```
fn main(){
    println!("Hello, world!");
}
```

## Compile
Compile source code into an executable file.
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


## Notes
- executable file is in directory named -> debug
- name of executable file is set in -> Cargo.toml
- source code file is in directory named -> src
- for abbreviated output:
```
$ cargo run -q
```
or
```

$ cargo run --quiet
```

