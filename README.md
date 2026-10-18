# COAL
coal assignments
# x86 Assembly Assignment: Text Viewport Manager

**Name:** SAIRA IQBAL
**Roll No.:** 25L-0659
**Course:** COAL-EE2003

## Description

This repository contains a 16-bit real-mode x86 (8088) assembly programs, written as .asm file.

### Q2: Text Viewport Manager with Windowed Scrolling & Keyword Highlighter

Draws a bounded text viewer directly in video memory (segment `0xB800`).

part 1: Initial Viewport Window
  - Clears the 80x25 screen with `REP STOSW`.
  - Draws a double-line border window from row 3 to row 21 and column 8 to column 72.
  - Prints a centered title banner with attribute `0x1E`.
    
part 2: Multi-line Text Buffer Streaming
  - Load and display a paragraph stored in memory inside the window boundaries.
  - Use string primitives (LODSB/STOSW) to stream characters into the video segment.
    
part 3: Bounded Sub-Window Scrolling (Window Scroll Up)
  - Implement a subroutine scroll_window_up that receives the window coordinates.
  - Shift text inside the window upward by N lines without altering or corrupting window borders or external screen areas.
  - Move lines using MOVSW with row-stride offset calculations for each individual line, and
    blank out the vacated bottom line(s) of the window using STOSW.
    
## Files

|     File     |          Description          |
| 25L-0659.asm | Q2: complete viewport manager |

## Tools Used

- **NASM** (Netwide Assembler) to assemble the source files
- **DOSBox** (0.74-3) to run and debug the programs

## How to Build and Run

1. Assemble the file into a `.com` program:

   ```
    nasm viewport_manager.asm -f bin -o viewport.com
   ```

2. Mount the folder in DOSBox and run:

   ```
   mount c C:\path\to\repo
   c:
   viewport.com
   ```
