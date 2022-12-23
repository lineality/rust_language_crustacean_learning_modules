# 0003 Rust: Simple Integration Test
### Rust Language Learning Module

## Goals
1. Add an 'integration test' to a cargo project (a test that runs your program as a user might).
2. See files and folders created by cargo after running/testing your program.
3. Note types of tests: unit tests vs. integrations tests.

## Create Project with cargo
```
[username@system projects]$ cargo new simple_integration_test
```

## Change working directory
```
$ cd simple_integration_test
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
#[test]
fn program_runs() {
    assert!(true);
}
```

## File Tree
Look at the files and file-structure
```
$ tree
```
#### Output (before compiling, running, or testing the program)
```
[username@system simple_integration_test]$ tree
.
├── Cargo.toml
├── src
│   └── main.rs
└── tests
    └── cli.rs
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
You may not need to run "$ cargo run" before running "$ cargo test"
Compile source code into an executable file.
```
$ cargo test
```

#### Output
```
[username@system simple_integration_test]$ $ cargo test
   Compiling simple_integration_test v0.1.0 (/home/crust/code/rust/simple_integration_test)
    Finished test [unoptimized + debuginfo] target(s) in 1.79s
     Running unittests src/main.rs (target/debug/deps/simple_integration_test-43edcc9ade888332)

running 0 tests

test result: ok. 0 passed; 0 failed; 0 ignored; 0 measured; 0 filtered out; finished in 0.00s

     Running tests/cli.rs (target/debug/deps/cli-7593bc5d9c6220af)

running 1 test
test program_runs ... ok

test result: ok. 1 passed; 0 failed; 0 ignored; 0 measured; 0 filtered out; finished in 0.00s




```

## Bonus: Run $ tree again, after testing
example output:
- the 'target' directory will contain build files
```
[username@system simple_integration_test]$ tree
.
├── Cargo.lock
├── Cargo.toml
├── src
│   └── main.rs
├── target
│   ├── CACHEDIR.TAG
│   ├── debug
│   │   ├── build
│   │   ├── deps
│   │   │   ├── cli-7593bc5d9c6220af
│   │   │   ├── cli-7593bc5d9c6220af.d
│   │   │   ├── simple_integration_test-0281908b6d4ac726
│   │   │   ├── simple_integration_test-0281908b6d4ac726.d
│   │   │   ├── simple_integration_test-43edcc9ade888332
│   │   │   └── simple_integration_test-43edcc9ade888332.d
│   │   ├── examples
│   │   ├── incremental
│   │   │   ├── cli-2f6eu7evr2gms
│   │   │   │   ├── s-ggm08tbf09-64oqc3.lock
│   │   │   │   └── s-ggm08tbf09-64oqc3-nt80et1m5gjy
│   │   │   │       ├── 1lh385dt23fuihq1.o
│   │   │   │       ├── 21ifka26acr4lp3w.o
│   │   │   │       ├── 3187dkfqegsm1b2r.o
│   │   │   │       ├── 31l78wauo8n1idt2.o
│   │   │   │       ├── 372y8d0c20xqu246.o
│   │   │   │       ├── 3oej3co281nlm37p.o
│   │   │   │       ├── 4ymzbd26w0fx6t6g.o
│   │   │   │       ├── 5g6uaibfvwri591l.o
│   │   │   │       ├── dep-graph.bin
│   │   │   │       ├── efnoamm91pej85h.o
│   │   │   │       ├── o5oljlvc8new44e.o
│   │   │   │       ├── qpuruplwi5srpgd.o
│   │   │   │       ├── query-cache.bin
│   │   │   │       └── work-products.bin
│   │   │   ├── simple_integration_test-2jql23mdxh8ne
│   │   │   │   ├── s-ggm08txmiv-76ozlt-149wxyofkmbu7
│   │   │   │   │   ├── 26xxbbwol4hwwd3h.o
│   │   │   │   │   ├── 28p0lbz76asc9vae.o
│   │   │   │   │   ├── 2fmckp39n4db4mrx.o
│   │   │   │   │   ├── 495g5kei6m555ds8.o
│   │   │   │   │   ├── dep-graph.bin
│   │   │   │   │   ├── query-cache.bin
│   │   │   │   │   ├── work-products.bin
│   │   │   │   │   └── zzng8r6nn8peoac.o
│   │   │   │   └── s-ggm08txmiv-76ozlt.lock
│   │   │   └── simple_integration_test-4jz4ng1rtnfr
│   │   │       ├── s-ggm08tbf15-13wmjfp-3283sup9f0b10
│   │   │       │   ├── 11beo7ee8yyl1imk.o
│   │   │       │   ├── 19ltf9vmaky7yjpg.o
│   │   │       │   ├── 1gfkj0hjmc43s4il.o
│   │   │       │   ├── 3bwmppvn0ko8q73l.o
│   │   │       │   ├── dep-graph.bin
│   │   │       │   ├── hjzvgnde3ga6krm.o
│   │   │       │   ├── q3q330pwwc5r0rm.o
│   │   │       │   ├── query-cache.bin
│   │   │       │   └── work-products.bin
│   │   │       └── s-ggm08tbf15-13wmjfp.lock
│   │   └── simple_integration_test
│   └── tmp
└── tests
    └── cli.rs

15 directories, 46 files
```

## Notes
- "Integration Testing" / "Outside-in testing" -> tests that run your program
- "Unit Testing" / "Inside-out Testing" -> test functions inside of your program
- Convention says: create a "tests" directory parallel to the "src" directory
- "#[test]" is an 'attribute' that tells rust to run this function during testing
- If you run "$ tree" after running "$ cargo run" or "$ cargo test" then additional files and folders will be seen to have been added.
- .toml -> you can add comment lines in with a "#" sharp/hash at the start of the line
- .toml -> you can add a "[dependencies]" section
- a command with a bang/exclamation-point after it ("!") is called a "macro" in rust
- Tests: you can use "assert!" to test if a result is what it is expected to be. 
- Tests: you can use "assert_eq!" to test if a value is what it is expected to be. 
