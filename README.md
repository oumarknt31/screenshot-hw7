# LOGANALYZER — CSC 332 Custom Linux Command

## Introduction
loganalyzer is a custom Linux shell command built for CSC 332 to analyze log files using efficient systems programming techniques, including:

- Advanced file I/O
- mmap() memory mapping
- getopt_long() command parsing
- Error handling
- Word statistics
- Optional filters (date, keyword, errors)

This tool demonstrates knowledge of Linux internals and system calls.

---

## Features

### Core Functionalities
- Efficient file reading via mmap()
- Keyword searching
- Line counting
- Error-only extraction (ERROR, Failed)
- Word frequency statistics
- Date filtering
- Robust option parsing with getopt_long()

### Advanced Concepts Used
- `mmap()` for performance
- File descriptor management
- Error handling with perror()
- Clean modular design
- Text parsing and tokenization

---

## Installation

Compile using GCC:
gcc loganalyzer.c -o loganalyzer

Run with:
./loganalyzer -f /path/to/log


---

## Command-Line Options

| Option | Long Form | Description |
|--------|------------|------------------------------------|
| `-h` | `--help` | Show help menu                         |
| `-f` | `--file <path>` | Path to log file (required)     |
| `-s` | `--stats` | Show file Statistics / Count lines    |
| `-k` | `--keyword <word>` | Count occurrences of keyword |
| `-e` | `--errors` | Only show error entries              |
| `-t` | `--threads <N>` | Enable multithreaded search     |
| `-m` | `--memory` | Show memory map statistics           |


---

## Usage Examples

## Show help menu:
./loganalyzer -f /var/log/auth.log -h

## Count lines/:
./loganalyzer -f /var/log/auth.log -s

## Search keyword:
./loganalyzer -f /var/log/auth.log -k "ERROR"

## Extract errors:
./loganalyzer -f /var/log/auth.log -e

## Enable multithreaded search:
./loganalyzer -f /var/log/auth.log -t

## Memory Map statistics
./loganalyzer -f /var/log/auth.log -m

---

## UML Diagram
<img width="1612" height="576" alt="Loganalyzer - Module Diagram" src="https://github.com/user-attachments/assets/0ac96477-a481-4979-af03-1164cddda3e9" />

