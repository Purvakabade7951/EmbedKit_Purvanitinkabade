# EmbedKit - Embedded Developer Fresher Assignment

## Author
Purva nitin kabade.

## Project Description
This project implements an 8-byte circular buffer (ring buffer) in standard C.
A ring buffer stores data in FIFO (First In, First Out) order and reuses freed
slots when the read and write positions wrap around.

## Module
- `ring_buf.c` — Implements and demonstrates the ring buffer operations.

## Features
- Initialize the buffer to an empty state.
- Write one byte unless the buffer is full.
- Read one byte unless the buffer is empty.
- Query the number of bytes stored.
- Check whether the buffer is full or empty.
- Demonstrate wrap-around and reuse of freed slots.
- Use bitwise AND for wrap-around if this optimization is implemented in the source.

## Requirements
- GCC compiler
- C99 support
- Standard C library only

## Build
Run this command from the project directory:

```bash
gcc -Wall -std=c99 ring_buf.c -o ringbuf.exe
```

## Run
In MSYS2 UCRT64, run:

```bash
./ringbuf.exe
```

## Test Sequence
The program demonstrates:
1. Writing eight bytes (`0x41` through `0x48`).
2. Attempting a write while the buffer is full.
3. Reading the first three bytes.
4. Writing three new bytes (`0x49`, `0x4A`, `0x4B`) into reused slots.
5. Reading the remaining bytes in FIFO order.
6. Attempting a read when the buffer is empty.

## Expected Behavior
- A full-buffer write fails without overwriting unread data.
- An empty-buffer read fails without returning invalid data.
- The byte count updates after each successful read or write.
- Data is returned in FIFO order.

## Compilation Check
The code should compile with `-Wall -std=c99` without warnings or errors.
