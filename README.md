# ped

**ped** is a lightweight, terminal-based text editor written in Perl.  
It is designed for fast editing in a Unix-like shell without extra dependencies or a graphical interface.

## Highlights

- Minimal, keyboard-driven editing experience
- Works directly in the terminal using raw keyboard input
- Line-numbered editor view with a live status/footer bar
- Supports both **UNIX (LF)** and **DOS (CRLF)** line endings
- Insert/overwrite toggle support
- Inline search with cursor jump to next match
- Optional open-at-line behavior via command-line argument

## Features

### File handling
- Open a file by passing its path as an argument
- Start with an empty buffer if the file does not exist
- Save to the current filename
- Save unnamed buffers by prompting for a filename

### Navigation
- Arrow keys: move cursor
- Page Up / Page Down: jump by one screen
- Home / End: jump to start/end of file
- Keeps cursor and viewport synchronized while scrolling

### Editing
- Insert text, tabs, and new lines
- Backspace and Delete support
- Delete to end of line (`Ctrl+K`)
- Merge/split lines when editing at boundaries

### Search
- `Ctrl+F` prompts for a search string
- Case-insensitive forward search through the buffer
- Reaching end of file is reported in the status line

### UI
- Header with editor title
- Footer with:
  - Current filename
  - Status messages (e.g., save results)
  - Line-ending mode (DOS/UNIX)
  - Insert mode indicator
  - Cursor position and line count
- Built-in help popup (`F1`)

## Key bindings

- `Ctrl+S` — Save
- `Ctrl+D` — Save and exit
- `Ctrl+C` — Exit without saving
- `Ctrl+F` — Search
- `Ctrl+K` — Delete to end of line
- `F1` — Help
- `Insert` — Toggle insert mode

## Usage

```bash
ped <filename>
```

Open near a specific line:

```bash
ped <filename> +<line_number>
```

Example:

```bash
ped notes.txt +120
```

## Requirements

- Perl runtime
- Terminal with ANSI escape support
- `stty` available (used for raw input mode and terminal sizing)

## Project notes

`ped` focuses on being small, readable, and easy to modify.  
It is a practical editor for quick terminal sessions and a useful reference for building text UIs in Perl.
