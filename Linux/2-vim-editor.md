#  nano editor

### create file with nano editor
````
nano example.txt
````

- to save file press **cntrl + x** then **y** and **enter**


# Vi / Vim Editor

Modes of vi/vim editor:
1. **Command Mode(default)**
2. **Insert Mode**
3. **Execution Mode**
4. **Visual Mode**

### Note:
Press `Esc` to exit from any mode.

---

## 1. Command Mode: (Default Mode)
In **Command Mode**, you can perform operations like deleting, copying, and pasting text, as well as navigating and editing the file. 

### Common Commands:
- dd  Delete current line
- dw  Delete current word
- `n`dd  Delete  number of lines from the current line
---
- yy  Copy current line
- yw  Copy current word
- `n`yy  Copy `n` number of lines from the current line
---

- cc  Cut current line and enter insert mode
- cw  Cut current word and enter insert mode
- `n`cc  Cut `n` number of lines and enter insert mode
---
- P  Paste copied or cut content
- u  Undo last action
- Ctrl+r  Redo last undone action
---

- G or L  Move cursor to the end of the file
- gg or H  Move cursor to the beginning of the file
- `n`gg  Move cursor to the `n`th line
  

---

## 2. Insert Mode

To enter **Insert Mode**, use the following commands:

- i  Insert text at the current cursor position
- o  Insert a new line below the current line
- O  Insert a new line above the current line

---

## 3. Execution Mode

- :q  Quit without saving
- :q!  Quit without saving, forcefully
- :w  Save and stay in the file
- :wq  Save and quit
- :x  Save and quit
- :wq!  Save and quit, forcefully
- :set nu  Enable line numbers
- :set nonu  Disable line numbers
- :/<word>  Highlight a specific word
- :%s/old word /new word      Find and replace old word with new word
- :!<command>  Execute a terminal command without leaving the editor

---

## 4. Visual Mode

- v: Select text character by character
- V: Select text line by line
- Ctrl+v: Select a block of text

---
- y: Copy selected text
- d: Delete selected text
- c: Cut selected text
- P: Paste the selected text

---
