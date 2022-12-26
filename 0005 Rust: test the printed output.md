# 0005 Rust: test the printed output
### Rust Language Learning Module

## Goals
1. Add a test that checks printed output, compare actual printed output to expected printed output.


## Create Project with cargo
```
[username@system projects]$ cargo new test_the_print_output
```

## Change working directory
```
$ cd test_the_print_output
```

## Add a dependency to the .toml file
```
[dependencies]
assert_cmd = "1"
```
#### example .toml file
```
[package]
name = "test_the_print_output"
version = "0.1.0"
edition = "2021"

# See more keys and their definitions at https://doc.rust-lang.org/cargo/reference/manifest.html

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
    let mut stored_output = Command::cargo_bin("test_the_print_output").unwrap();
    stored_output.assert().success();
    stored_output.assert().success().stdout("Hello, world!"\n);
}
```


## test
```
$ cargo test
```



## Notes
- ...
