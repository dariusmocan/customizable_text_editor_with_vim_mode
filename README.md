# Text Editor (Tkinter)

A lightweight, tabbed text editor built with Python's Tkinter. It supports multiple tabs, windows, saving and opening existing .txt files,  standard editing operations, a handy Find dialog, and a customization window for fonts, styles, sizes, and colors. Font and color preferences are saved and automatically reused.

**NEW**: Vim mode support with essential Vim commands for efficient text editing!

## Features

- Multiple tabs
- Standard file operations: Open, Save, Save As
- Window management: New Tab, Close Tab, New Window, Close Window, Exit All
- Edit operations: Undo, Redo, Copy, Paste, Cut, Select All
- Find dialog with Find Next / Find Previous and match highlighting
- Customization window:
  - Font family selection
  - Style toggles (Normal, Bold, Italic)
  - Font size
  - Text color and background color pickers
- Auto-persistent preferences (font family, size, weight, slant, fg/bg colors) saved in `font.json`
- Unsaved changes indicator: an asterisk `*` on the tab title
- Helpful text navigation:
  - Ctrl+Left moves to beginning of the pervious word
  - Ctrl+Right moves to end of the current/next word
  - Ctrl+Backspace deletes the whole previous word
- **Vim Mode**: Toggle between Standard and Vim editing modes with full support for:
  - Normal, Insert, and Command modes
  - Navigation (h/j/k/l, 0/$)
  - Editing commands (x, dd, yy, p, o)
  - Find commands (f/F)
  - Ex commands (:w, :q, :wq, :q!)
  - Repeat last change (.)
  - Visual mode indicator in status bar

## Keyboard Shortcuts

| Action | Shortcut |
|---|---|
| Open File | Ctrl + O |
| Save | Ctrl + S |
| Save As | Ctrl + Shift + S |
| New Tab | Ctrl + N |
| Close Tab | Ctrl + W |
| New Window | Ctrl + Shift + N |
| Close Window | Ctrl + Shift + W |
| Exit All | (via File menu) |
| Undo | Ctrl + Z |
| Redo | Ctrl + Y |
| Copy | Ctrl + C |
| Paste | Ctrl + V |
| Cut | Ctrl + X |
| Select All | Ctrl + A |
| Find | Ctrl + F |
| Move to end of word | Ctrl + Right |
| Delete whole previous word | Ctrl + Backspace |
| Indent line | Ctrl + T |
| Unindent line | Ctrl + D |
| Enable Vim Mode | Ctrl + M |
| Enable Standard Mode | Ctrl + Shift + M |

Note: If a shortcut doesn't trigger in your environment, use the corresponding menu item.

### Vim Mode Commands

#### Normal Mode

| Command | Description |
|---|---|
| `h` | Move cursor left |
| `j` | Move cursor down |
| `k` | Move cursor up |
| `l` | Move cursor right |
| `0` | Jump to start of line |
| `$` | Jump to end of line |
| `x` | Delete character under cursor |
| `dd` | Delete entire line |
| `dk` | Delete current line and line above |
| `dh` | Delete character before cursor |
| `yy` | Copy (yank) entire line |
| `y$` | Copy from cursor to end of line |
| `p` | Paste after cursor |
| `o` | Open new line below and enter Insert mode |
| `u` | Undo |
| `Ctrl + R` | Redo |
| `f<char>` | Find next occurrence of character on current line |
| `F<char>` | Find previous occurrence of character on current line |
| `.` | Repeat last change |
| `i` | Enter Insert mode |
| `:` | Enter Command mode |
| `Esc` | Return to Normal mode (from any mode) |

#### Insert Mode

| Command | Description |
|---|---|
| `Esc` | Return to Normal mode |
| `Ctrl + T` | Indent current line |
| `Ctrl + D` | Unindent current line |

(All regular typing works as expected in Insert mode)

#### Command Mode

| Command | Description |
|---|---|
| `:w` | Save file |
| `:q` | Close tab |
| `:wq` | Save and close tab |
| `:q!` | Exit all windows without saving |
| `Esc` | Return to Normal mode |

**Mode Indicator**: The status bar at the bottom shows the current mode:
- `Standard` - Standard editing mode
- `-- NORMAL --` - Vim Normal mode
- `-- INSERT --` - Vim Insert mode
- `:` followed by text - Vim Command mode

## Requirements

- Python (preferably 10+)
- Tkinter (bundled with the standard Python installer on Windows/macOS; on some Linux distros you may need to install it separately, e.g., `python3-tk`).

No third-party packages are required.

## Getting Started

### Run (Windows PowerShell)

```powershell
# From the project directory
python .\text_editor.py
```

Optional (use a virtual environment):

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
python .\text_editor.py
```

### Run (macOS/Linux)

```bash
python3 text_editor.py
```

## Usage

### Standard Mode

- **File menu**:
  - Open an existing text file, Save current file, or Save As a new file.
  - Create a New Tab or a New Window.
  - Close the current Tab or Window, or Exit All windows.
- **Edit menu**:
  - Undo/Redo, Copy/Paste/Cut, Select All, and open the Find dialog.
- **Custom menu**:
  - Open the customization window to adjust font family, style (Normal/Bold/Italic), size, and colors (text/background).
- **Mode menu**:
  - Switch between Standard and Vim editing modes.
- **Find dialog**:
  - Enter the search term and use Find Next or Find Prev to jump between matches; matches are highlighted.
- **Unsaved changes**:
  - Tabs with unsaved changes show an asterisk `*` in the title. Closing a tab or window with unsaved changes prompts you to save.

### Vim Mode

To enable Vim mode:
1. Use the **Mode Menu** → **Vim**, or
2. Press `Ctrl + M`

Once in Vim mode:
- You start in **Normal mode** (status bar shows `-- NORMAL --`)
- Press `i` to enter **Insert mode** for typing
- Press `Esc` to return to **Normal mode** from any other mode
- Press `:` to enter **Command mode** for saving/quitting
- All Vim commands listed in the Keyboard Shortcuts section are available
- Press `Ctrl + Shift + M` or use Mode Menu → Standard to return to Standard mode

**Tips**:
- The status bar always shows your current mode
- File operations (`:w`, `:q`, `:wq`) work seamlessly with the tabbed interface
- Clipboard operations (`yy`, `y$`, `p`) use the system clipboard
- The `.` command repeats your last editing action (like `dd`, `x`, or `o`)

## Preferences and Persistence

- Preferences are stored in `font.json` in the project directory.
- When you open the customization window and close it, settings (font family, size, weight, slant, text color, background color) are saved automatically.
- New tabs load these preferences on creation.


