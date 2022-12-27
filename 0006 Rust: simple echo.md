# 0006 Rust: simple echo
### Rust Language Learning Module

## Goals
1. write a command line program that re-prints (echos) the input to the command line program


## Create Project with cargo
```
[username@system projects]$ cargo new simple_echo
```

## Change working directory
```
$ cd simple_echo
```

## Main source file
```
$ nano src/main.rs
```

#### text of main.rs file
```
fn main(){
    println!("{:?}", std::env::args());
}
```

## Run
```
$ cargo run
$ cargo run Hello
```



## Notes
- By convention, command line programs often have a built-in feature whereby they can accept "-h" or "--help" as inputs and will (if those are input) output a standard help page.


