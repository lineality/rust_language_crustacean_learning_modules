# 0004 Rust: Integration Test - check a result
### Rust Language Learning Module

## Goals
1. Make an 'integration test' that checks a result, specifically: seeing if the output of your main function is an error or an 'ok' output.


## Create Project with cargo
```
[username@system projects]$ cargo new check_result
```

## Change working directory
```
$ cd check_result
```

## Add a dependency to the .toml file
```
[dependencies]
assert_cmd = "1"
```

## Create a 'tests' directory
```
$ mkdir tests
```

## Make 'cli.rs' file in 'tests' directory
This is a test-file, a file that contains tests that you write to test your program.
```
$ nano tests/cli.rs
```

#### text of cli.rs file
```
use assert_cmd::Command;

#[test]
fn command_runs_test() {
    let mut output_variable = Command::cargo_bin("check_result").unwrap();
    output_variable.assert().success();
}
```



## Source code file
File name: main.rs
```
$ nano src/main.rs 
```
#### File contents
```
fn main(){
    println!("Hello, world!");
}
```

## test
```
$ cargo test
```

#### Output
```

```



## Notes
- some tests may use this form...but perhaps not:
```
use std::process::Command;

#[test]
fn command_runs_test() {
    let mut variable_storing_command_output = Command::new("ls");
    let res = variable_storing_command_output.output();
    assert!(res.is_ok());
}
```
- use of 'assert_cmd' requires a cargo package manager download.
