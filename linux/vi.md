
# VI chivo

## Entering and Exiting vi

> `vi file.txt `
Opens file.txt for editing or creates it if it doesn’t exist. Basic usage to open a file in vi.

> `i           `
Switches from command mode to insert mode, allowing you to insert text. Press i to begin inserting text.

> ` Esc        `
Exits insert mode and returns to command mode. Use this key to switch back to command mode after editing.

> ` :w         `
Saves (writes) the file without exiting. Saves changes made to the file.

> ` **:wq or :x`
Saves the file and exits vi. Commonly used to save and exit after editing.

> ` :q         `
Exits vi without saving changes. Use this to quit without saving.

> ` :q!        `
Forces vi to exit without saving changes, even if modifications have been made. Use when you want to discard all changes and quit.

## Navigation in Command Mode

> `h, j, k, l`
Moves the cursor left (h), down (j), up (k), or right (l). Basic cursor navigation keys in command mode.

> `w         `
Moves the cursor forward by one word. Useful for quickly navigating through text.

> `b         `
Moves the cursor backward by one word. Useful for reversing through text.

> `0         `
Moves the cursor to the beginning of the current line. Quick way to jump to the start of a line.

> `$         `
Moves the cursor to the end of the current line. Quick way to jump to the end of a line.

> `gg        `
Moves the cursor to the beginning of the file. Fast navigation to the start of a file.

> `G         `
Moves the cursor to the end of the file. Fast navigation to the end of a file.

## Editing in Command Mode


>`dd         `
Deletes the current line. Useful for removing lines.

>`yy         `
Yanks (copies) the current line. Use p to paste the copied line.

>`p          `
Pastes the yanked or deleted content after the cursor. Used after yy or dd to paste content.

>`u          `
Undoes the last change. Reverts the previous command.

>`r          `
Replaces the character under the cursor. Quickly replace single characters.

>`x          `
Deletes the character under the cursor. Useful for quick character deletion.

>`:set number`
Displays line numbers in the file. Useful for editing files with reference to line numbers.
