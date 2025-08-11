# shell-command-line

---

# lsh - A Simple Shell in C

`lsh` is a simple command-line shell written in C, inspired by Stephen Brennan's "Build Your Own Shell" tutorial. It supports executing commands, built-in functions like `cd`, `help`, and `exit`, and basic command parsing.

---

## Features

* Read and parse user input lines.
* Split input into tokens (commands and arguments).
* Execute built-in commands:

  * `cd` — change directory
  * `help` — display help information
  * `exit` — exit the shell
* Launch external programs using `fork()` and `execv()`.
* Wait for child processes to finish before accepting new commands.

---

## Getting Started

### Prerequisites

* A Unix-like operating system (Linux, macOS).
* GCC or any C compiler.
* Basic knowledge of terminal/command line.

### Compilation

To compile the shell program, run:

```bash
gcc -o lsh lsh.c
```

This will create an executable named `lsh`.

### Usage

Run the shell by executing:

```bash
./lsh
```

You will see a prompt like this:

```bash
>
```

Type commands and press Enter.

Example:

```bash
> ls -l
> cd /home/user
> help
> exit
```

---

## Code Overview

* `main()` starts the shell loop (`lsh_loop`).
* `lsh_loop()` repeatedly:

  * Displays prompt
  * Reads a line of input (`lsh_read_line`)
  * Splits the line into tokens (`lsh_spilt_line`)
  * Executes commands (`lsh_execute`)
* Built-in commands are handled internally.
* Other commands are run using `fork()` and `execv()`.

---

## Known Issues

* Currently, external commands must be specified with full path (e.g., `/bin/ls`). PATH environment variable lookup is not implemented.
* Limited error handling.
* Input editing (like backspace) is minimal.




## Author

Your sourav


