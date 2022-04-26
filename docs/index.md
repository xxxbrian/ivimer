# Vim cheat sheet

- [English](./)
- [简体中文](./README_CN.md)
- [繁體中文](./README_TC.md)

## The power of repetition

```
.                   # Repeat (Dot) command, repeats the previous command
N{command}          # Repeat a command N times, e.g. 10k, cursor moves up 10 lines
```

**In addition, the power of repetition should also be leveraged with macros and regular expressions to reduce repetitive operations.**

## Cursor movement

**Note: In normal mode, any of the actions can be repeated.**

unit level.

```
h                   # Move the cursor to the left, equivalent to the <Left> arrow key. (Note: the h key is on the left, press it to move the cursor left)
j                   # Move the cursor down, equivalent to the <Down> arrow key. (Note: the j key has a downward protrusion, press this key to move the cursor down)
k                   # Move the cursor up, equivalent to the <Up> arrow key. (Note: the k key is the opposite of the j key, press this key to move the cursor up)
l                   # Move the cursor to the right, equivalent to the <Right> arrow key. (Note: the l key is on the right, press it to move the cursor to the right)
```

word level.

```
w                   # Move to the beginning of the next word separated by punctuation or space (w: word)
W                   # Move to the beginning of the next space-separated word (W: Word)
e                   # Move to the end of the next word separated by punctuation or space (e: end)
E                   # Move to the end of the next space separated word (E: End)
b                   # Move to the beginning of the previous word separated by punctuation or space (b: backward)
B                   # Move to the beginning of the previous space-separated word (B: Backward)
```

block level.

```
0                   # Jump to the beginning of the line, the number 0, the effect is equivalent to the <Home> key
^                   # Jump to the non-blank character at the beginning of the line, you can use 0w instead of ^, which is more convenient to press
$                   # Jump to the end of the line, the effect is equivalent to the <End> key
gg                  # Jump to the first line, the effect is equivalent to Ctrl+<Home>
G                   # Jump to the last line, the effect is equivalent to Ctrl+<End>
NG                  # Jump to the Nth row, for example 10G is to move to the tenth row
:N                  # Jump to the Nth line, for example: 10<Enter> is to move to the tenth line
N%                  # Move to the N% position of the file, for example 10% is moved to the 10% position of the file
N|                  # Move to N columns of the current row
<Enter>             # Move to the first non-blank character in the next line
N<Enter>            # Move the cursor down N lines
ge                  # Move backward to the end of the word
gE                  # Move backward to the end of a word separated by a whitespace
)                   # Move forward one sentence (separated by periods)
(                   # Move backward one sentence (period separated）
}                   # Move forward one paragraph (separated by blank lines)
{                   # Move backward one paragraph (separated by blank lines)
+                   # Move to the first non-blank character in the next line (same as the Enter key)
-                   # Move to the first non-blank character in the previous line
H                   # Move to the upper part of the screen (H: High)
M                   # Move to the middle of the screen (M: Middle)
L                   # Move to the bottom of the screen (L: Low)
gm                  # Move to the middle of the line
gj                  # Move the cursor down one screen line (ignore automatic line wrapping)
gk                  # Move the cursor up one screen line (ignore auto-wrap)
zz                  # Adjust the cursor line to the center of the screen
zt                  # Adjust the cursor line to the upper part of the screen
zb                  # Adjust the cursor line to the bottom of the screen
Ctrl+e              # Scroll up one line
Ctrl+y              # Scroll down one line
Ctrl+u              # Move up 1/2 a screen
Ctrl+d              # Move down 1/2 a screen
Ctrl+f              # Move forward one full screen
Ctrl+b              # Move back one full screen
<S+Up>              # Hold down the <Shift> key and then press the <Up> arrow key to page up
<S+Down>            # Hold down the <Shift> key and then press the <Down> arrow key to page down
<S+Left>            # Hold down the <Shift> key and press the <Left> arrow key to move one word to the left
<S+Right>           # Hold down the <Shift> key and press the <Right> arrow key to move one word to the right
```

## Insert mode

```
i                   # Enter insert mode at the cursor
I                   # Enter insert mode at the beginning of the line
a                   # Enter insert mode after the cursor
A                   # Enter insert mode at the end of the line
o                   # Insert a new row in the next row and enter insert mode
O                   # Insert a new row in the previous row and enter insert mode
s                   # Delete the character under the cursor and insert text
S                   # Delete the current line and insert text
gi                  # Go to the position of the last insert mode
gI                  # Insert text at the start of line (column 1)
<Esc>               # Exit insert mode
Ctrl+[              # Exit insert mode (equivalent to <Esc> key)
Ctrl+C              # Like Ctrl-[ and <Esc>, but does not check for abbreviation
```

## Insert mode commands

**Note: Enter insert mode by i, I, a, A, o, O, s, S command.**

```
<Up>                # Cursor up
<Down>              # Cursor down
<Left>              # Move the cursor to the left
<Right>             # Move the cursor to the right
<S+Up>              # Hold down the <Shift> key and then press the <Up> arrow key to page up
<S+Down>            # Hold down the <Shift> key and then press the <Down> arrow key to page down
<S+Left>            # Hold down the <Shift> key and press the <Left> arrow key to move one word to the left
<S+Right>           # Hold down the <Shift> key and press the <Right> arrow key to move one word to the right
<PageUp>            # Page up
<PageDown>          # Page down
<Delete>            # Delete the character at the cursor
<Backspace>         # Backspace key is to delete characters backward
<Home>              # Cursor jump to the beginning of the line
<End>               # Cursor jump to end of line
Ctrl+d              # Decrease indent
Ctrl+f              # Decrease indent
Ctrl+t              # Increase indent
Ctrl+h              # Delete the previous character, equivalent to Backspace
Ctrl+o              # Temporarily exit insert mode, execute a single command and return to insert mode
Ctrl+u              # Delete all characters from the current line to the beginning of the line
Ctrl+w              # Delete a word before the cursor
Ctrl+\ Ctrl+O       # Temporarily exit insert mode (cursor hold), execute a single command and return to insert mode
Ctrl+R 0            # Insert the contents of the register (internal clipboard No. 0), the register name can be followed by Ctrl+R
Ctrl+R "            # Insert anonymous register content, which is equivalent to p paste in insert mode
Ctrl+R =            # Insert expression calculation result, equal sign followed by expression
Ctrl+R :            # Insert the last command line command
Ctrl+R /            # Insert the last search keyword
Ctrl+v {char}       # Insert non-numeric literals
Ctrl+v {code}       # Insert the ASCII/Unicode character encoding represented by three digits, such as Ctrl+v 065
Ctrl+v 065          # Insert a decimal ASCII character (two digits) 065 is the A character
Ctrl+v x41          # Insert hexadecimal ASCII characters (three numbers) x41 is the A character
Ctrl+v o101         # Insert octal ASCII characters (three numbers) o101 is the A character
Ctrl+v u1234        # Insert hexadecimal Unicode characters (four digits)
Ctrl+v U12345678    # Insert hexadecimal Unicode characters (eight digits)
Ctrl+K {ch1} {ch2}  # Insert digraph (see :h digraph), quickly enter Japanese or symbols, etc.
```

## Autocomplete

In insert mode, the most commonly used completion.

```
Ctrl+n              # Automatic text completion in insert mode
Ctrl+P              # Automatic text completion in insert mode
Ctrl+e              # When there is a completion list, terminate this completion and continue typing
```

**Smart completion commands all start with the key combination Ctrl+X.**

```
Ctrl+X              # Enter completion mode
Ctrl+X Ctrl+L       # Whole line completion
Ctrl+X Ctrl+N       # In insert mode, complete according to keywords in the current file
Ctrl+X Ctrl+K       # Completion according to dictionary
Ctrl+X Ctrl+T       # Completion according to the synonym dictionary
Ctrl+X Ctrl+F       # Complete file name in insert mode
Ctrl+X Ctrl+I       # Completion based on keywords in the header file
Ctrl+X Ctrl+]       # Complete according to tags
Ctrl+X Ctrl+D       # Complete macro definition
Ctrl+X Ctrl+V       # Completing Vim commands
Ctrl+X Ctrl+U       # User-defined completion method
Ctrl+X Ctrl+S       # Spelling suggestions, for example: an English word
Ctrl+X Ctrl+O       # Insert Omnifunc completion
```

## Text Editor

```
r                   # Replace the current character
R                   # Enter replacement mode until you press <Esc> to leave
J                   # Delete a newline character and merge multiple lines into one line
s                   # Replace character (delete the character at the cursor and enter the insert mode, the number can be connected in front)
S                   # Replace line (delete the current line and enter the insert mode, the number can be accessed before)
cc                  # Rewrite the current line (delete the current line and enter insert mode), same as S
cw                  # Overwrite the current word at the beginning of the cursor
ciw                 # Rewrite the word under the cursor
caw                 # Rewrite the word under the cursor, and include leading and trailing spaces
c0                  # Rewrite to the beginning of the line
c^                  # Rewrite to the beginning of the line (the first non-zero character)
c$                  # Rewrite to the end of the lin
C                   # Rewrite to the end of the line (same as c$)
ci"                 # Rewrite the content in double quotes
ci'                 # Rewrite the content in single quotes
cib                 # Rewrite the content in parentheses
cab                 # Rewrite the content in the parentheses (including the parentheses themselves)
ci)                 # Rewrite the content in parentheses
ci]                 # Rewrite the content in the brackets
ciB                 # Rewrite the content in the braces
caB                 # Rewrite the content in the braces (including the braces themselves)
ci}                 # Rewrite the content in the braces
cit                 # Rewrite the content in the XML tag
cis                 # Rewrite the current sentence
c2w                 # Write two words instead
ct(                 # Rewrite before the parentheses
x                   # Delete the current character, you can receive a number in front, 3x means delete three characters
X                   # Delete characters forward
dd                  # Delete (cut) a line
d0                  # Delete (cut) to the beginning of the line
d^                  # Delete (cut) to the beginning of the line (the first non-zero character)
d$                  # Delete (cut) to the end of the line
D                   # Delete (cut) to the end of the line (same as d$)
dw                  # Delete (cut) the current word
diw                 # Delete (cut) the word under the cursor
daw                 # Delete (cut) the word under the cursor, and include leading and trailing spaces (if any)
di"                 # Delete the content in double quotes
di'                 # Delete the content in single quotes
dib                 # Delete the content in parentheses
di)                 # Delete the content in parentheses
dab                 # Delete the content in the parentheses (including the parentheses themselves)
di]                 # Delete the content in the square brackets
diB                 # Delete the content in the braces
di}                 # Delete the content in the braces
daB                 # Delete the content inside the braces (including the braces themselves)
dit                 # Delete the content in the tag in XML
dis                 # Delete the current sentence
d2w                 # Delete the next two words
dt(                 # Delete to the front of the parenthesis
dgg                 # Delete to the head of the file
dG                  # Delete to the end of the file
d}                  # Delete the next paragraph
d{                  # Delete the previous paragraph
Nd                  # Delete N lines from the beginning of the current line
:Nd                 # Delete line N
:1,10d              # Delete 1~10 lines
~                   # Replace case
g~iw                # Replace the case of the current word
gUiw                # Convert words to uppercase
guiw                # Convert the current word to lowercase
guu                 # Convert the entire line to lowercase
gUU                 # Convert the entire line to uppercase
<<                  # Reduce indent
>>                  # Increase indent
==                  # Auto indent
Ctrl+A              # Increase the number
Ctrl+X              # Reduce the number
```

## Text object

Note: Only applicable to visual mode or after operator, for example: operation includes **select v, delete d, copy y, modify c**, etc.

```
aw                  # Operate the entire word, excluding the delimiter (aw: a word)
aW                  # Manipulate entire words, including separators (aW: a Word)
iw                  # Operate the entire word, excluding the separator (iw: inner word)
iW                  # Operate the entire word, including the separator (iW: inner Word)
is                  # Operate the entire sentence, excluding the separator (s: sentence)
ib                  # Operation contains block, from [( to ]) (b: block)
iB                  # Operation contains large blocks, from [{ to ]} (B: Block)
ab                  # Operate a block, from [( to ])(b: block)
aB                  # Operate a large block, from [{ to ]} (B: Block)
ap                  # Operate a paragraph (p: paragraph)
ip                  # Operation contains paragraph
i)                  # Manipulate parentheses string
a)                  # Manipulate the string in the parentheses, including the parentheses themselves
i]                  # Operation bracket string
a]                  # Operate the bracket string, including the bracket itself
i}                  # Manipulate brace strings
a}                  # Manipulate brace strings, including the braces themselves
i'                  # Operation single quoted string
a'                  # Manipulate a single quoted string, including the single quote itself
i"                  # Manipulate double quoted strings
a"                  # Manipulate double quoted strings, including the double quotes themselves
a`                  # Manipulate a backtick string
i`                  # Operation contains backquote string
a>                  # Manipulate a <> block
i>                  # Operation contains <> block
at                  # Manipulate a tag block, for example from <aaa> to </aaa> (t: tag)
it                  # The operation contains a tag block, such as from <aaa> to </aaa>
2i)                 # Operate outside the two parentheses
2a)                 # Operate the outer two levels of parentheses, including the parentheses themselves
Nf)                 # Move to the Nth parenthesis
Nt)                 # Move to the Nth parenthesis
```

**The text object can be simply summarized as:**

```
ci'、ci"、ci(、ci[、ci{、ci<                 # Change the text content in these paired punctuation marks separately
di'、di"、di(、dib、di[、di{、diB、di<        # Delete the text content in these paired punctuation marks respectively
yi'、yi"、yi(、yi[、yi{、yi<                 # Copy the text content of these paired punctuation marks separately
vi'、vi"、vi(、vi[、vi{、vi<                 # Select the text content in these paired punctuation marks respectively
```

cit、dit、yit、vit，Operate the content between a pair of tags separately, and edit HTML and XML are easy to use! In addition, if you change the above i to a, you can operate the matching punctuation and the content in the matching punctuation at the same time.

## Move text

```
:[range]m[ove]{address}
```

**Parameter Description**

- [range]: Indicates the range of rows to be moved
- {address}: Indicates the target position of the movement, both of these parameters can be defaulted

For example

```
:m+1                # Move down 1 line
:m-2                # Move up 1 line
:8,10m2             # Move the contents of lines 8~10 of the currently opened file to the bottom of line 2
```

## Copy and paste

**Format of the copy command**：

```
:[range]co[py]{address}
```

Parameter Description：

- [range]：Indicates the range of lines to be copied, where copy can be abbreviated as :co or :t
- {address}：Indicates the destination of the copy. Both of these parameters can be defaulted to indicate the current line where the Vim cursor is located.

> For example: [:5copy.] means to copy line 5 of the file currently opened by Vim to the current line (indicated by .), that is, to create a copy of line 5 and place it below the current line.

The subscript lists some examples and uses of file copy using the abbreviation t of the copy command, which is used to understand the purpose of the copy command copy.

```
:3,5t.              # Copy the content from lines 3 to 5 below the current line
:t5                 # Copy the current line below line 5
:t.                 # Copy the current line below the current line (equivalent to yyp in normal mode)
:t$                 # Copy the current line to the end of the text
:'<,'>t0            # Copy the highlighted line to the beginning of the file
```

**Copy and paste commands**

```
p                   # After pasting to the cursor
P                   # Paste before the cursor
v                   # Enter visual mode
V                   # Visual mode is marked by line
Ctrl+V              # Visual mode is marked by column
y                   # Copy marked content
y$                  # Copy the current position to the end of the line
yy                  # Yank (copy) a line
Y                   # Copy the current line, same as yy
yiw                 # Copy the current word
Nyy                 # Copy the contents of N lines under the cursor
ddp                 # Cut the current line and paste (first delete the current line, copy it to the register, and paste)
v0                  # Select the current position to the beginning of the line
v$                  # Select the current position to the end of the line
viw                 # Select the current word
vib                 # Select things in parentheses
vi)                 # Select the content in parentheses
vi]                 # Select the content in the square brackets
viB                 # Select the content in the braces
vi}                 # Select the content in the braces
vis                 # Select the content in the sentence
vab                 # Select the content in the parentheses (including the parentheses themselves)
va)                 # Select the content in the parentheses (including the parentheses themselves)
va]                 # Select the content in the brackets (including the brackets themselves)
vaB                 # Select the content inside the braces (including the braces themselves)
va}                 # Select the content inside the braces (including the braces themselves)
:set paste          # Allow paste mode (to avoid automatic indentation affecting formatting when pasting)
:set nopaste        # Prohibit paste mode
"?yy                # Copy the current line to the register?, The question mark represents the register name from 0-9
"?d3j               # Delete the contents of the three lines under the cursor and put them in the register?, The question mark represents the register name of 0-9
"?p                 # Paste the contents of the register? After the cursor
"?P                 # Paste the contents of the register? In front of the cursor
:registers          # Display the contents of all registers
:[range]y           # Copy range, for example: 20,30y is to copy 20 to 30 lines, and :10y is to copy the tenth line
:[range]d           # Delete range, for example: 20,30d is to delete 20 to 30 lines, and :10d is to delete the tenth line
"_[command]         # Use [command] to delete content without copying (not polluting registers)
"*[command]         # Use [command] to copy the content to the system clipboard (requires the Vim version to have clipboard support)
```

## Revocation and restoration

```
[N]u                # The undo command can be combined. For example, Nu, N is any integer, which means to undo N operations, the same below. (u: undo)
[N]U                # Undo the entire operation
Ctrl+r              # Cancel the last u command (r: redo)
Ctrl+R              # Rewind the previous command
```

## Find and replace

**Find command in normal mode**

```
/pattern            # Search pattern from the cursor to the end of the file
?pattern            # Search pattern from the cursor to the head of the file
n                   # Search down for matching content
N                   # Search forward
%                   # Matching bracket movement, including (), {}, []. Combining the following two commands is quite powerful for programmers (premise: you need to move the cursor to the parentheses first)
*                   # Search down the word under the cursor
#                   # Search forward for the word under the cursor
f{char}             # Search backward for the first character of the current line as {char}, 2fv can find the second character of v
F{char}             # Search forward for the first character in the current line that is {char}
t{char}             # Search backward before the first character in the current line that is {char}
T{char}             # Search forward before the first character in the current line that is {char}
;                   # Repeat the last character search command (f/t command)
,                   # Reverse the direction to find the last character search command (f/t command)
tx                  # Search the current line before the specified string
fx                  # Search the current line to the specified string
<Esc>               # Abandon the search. For example, after starting the f command, I found that I wanted to use the F command, and the <Esc> exit key gave up the search
```

Note: The <Esc> key can abort most commands.

**Replace command in normal mode**

```
:[range]s[ubstitute]/{pattern}/{string}/[flags]
```

Parameter Description：

- pattern：It is the string to be replaced, which can be represented by regexp.
- string：Replace pattern by string.
- [range]：There are the following values.

| [range] value | Description                                                                                           |
| ------------- | ----------------------------------------------------------------------------------------------------- |
| null          | Default cursor line                                                                                   |
| .             | The current line where the cursor is                                                                  |
| N             | Line N                                                                                                |
| $             | the last line                                                                                         |
| 'a            | Mark the line where a (has been marked with ma before)                                                |
| $-1           | The penultimate row, you can add or subtract a certain value to a certain row to obtain a certain row |
| 1,10          | Line 1~10                                                                                             |
| 1,$           | First line to last line                                                                               |
| 1,.           | First line to current line                                                                            |
| .,$           | Current line to last line                                                                             |
| 'a,'b         | Mark the line where a is located to the line where the mark b is located (marked with ma, mb before)  |
| %             | All rows (equivalent to 1, $)                                                                         |
| ?str?         | Search upwards from the current position and find the first line of str (str can be regular)          |
| /str/         | Search down from the current position to find the first line of str (str can be regular)              |

Note that all the above representation methods for range can be used to set the relative offset through + and-operations.

- [flags] has the following values:

| [flags]value | Description                                         |
| ------------ | --------------------------------------------------- |
| g            | Replace all matches (global) in the specified range |
| c            | Ask the user to confirm before replacing (confirm)  |
| e            | Ask the user to confirm before replacing (confirm)  |
| i            | not case sensitive                                  |
| null         | Only replace the first match in the specified range |

For example:

```
:s/p1/p2/g          # Replace all p1 with p2 in the current line
:%s/p1/p2/g         # Replace all p1 with p2 in the current file
:%s/p1/p2/gc        # Replace all p1 with p2 in the current file, and ask you whether to replace it everywhere
:10,20s/p1/p2/g     # Replace all p1 in lines 10 to 20 with p2
:%s/1\\2\/3/123/g   # Replace "1\2/3" with "123" (special characters are marked with backslashes)
:%s/\r//g           # Delete DOS line break ^M
:%s///gn            # Count the number of matches in a pattern
:%s/^\s*$\n//g      # Delete all blank lines in the Vim open file
:g/^\s*$/d          # Delete all blank lines in the Vim open file
:%s/^M$//g          # Delete the explicit ^M symbol in the Vim file (operating system line break problem)
```

## Visual mode

**Note: In Vim visual mode, you can select an editing area, and then perform operations such as inserting, deleting, replacing, and changing the case of the selected file content.**

```
v                   # Switch to character-oriented visual mode
V                   # Switch to line-oriented visual mode
Ctrl+V              # Switch to block-oriented visual mode
>                   # Increase indent
<                   # Decrease indent
d                   # Delete the highlighted text
x                   # Delete the highlighted text
c                   # Rewrite the text, that is, delete the highlighted text and enter the insert mode
s                   # Rewrite the text, that is, delete the highlighted text and enter the insert mode
y                   # Copy text
~                   # Convert case
o                   # Jump to the other end of the marked area
O                   # Jump to the other end of the marker block
u                   # Marked area converted to lower case
U                   # Convert marked area to uppercase
gv                  # Reselect the last highlighted selection
g Ctrl+G            # Show statistics of the selected area
ggVG                # Select full text
<Esc>               # Press <Esc> to exit visual mode
```

In addition: The Vim Normal command can execute commands in the normal mode in the command line mode. When the Normal command is combined with the Vim visualization mode, a lot of repetitive tasks can be completed with few operations.

## Comment command

**Multi-line comments**

```
Ctrl+v              # Enter the command line mode, press Ctrl+v to enter the visual mode, then press j or k to select multiple lines and mark the lines that need to be commented
I                   # Press the capital letter I, and then insert the comment character, such as #, //
<Esc>               # Press the <Esc> key to comment all
```

**Uncomment multiple lines**

```
Ctrl+v              # Enter the command line mode, press Ctrl+v to enter the visual mode, press the letter l to select the number of columns horizontally, such as #, // (need to select 2 columns)
j or k              # Press the letter j, or k to select the comment symbol
d                   # Press the d key to uncomment all
```

**Complex annotation**

```
:Start line, end line s/^/ comment character /g       # Add a comment at the beginning of the specified line
:Start line, end line s/^ comment character //g       # Uncomment at the beginning of the specified line

:3,5 s/^/#/g        # Comment lines 3-5
:3,5 s/^#//g        # Uncomment lines 3-5

:1,$ s/^/#/g        # Annotate the entire document
:1,$ s/^#//g        # Uncomment the entire document

:%s/^/#/g           # Annotate the entire document, this method is faster
:%s/^#//g           # Uncomment the entire document
```

## Position movement

```
Ctrl+O              # Jump to the previous position
Ctrl+I              # Jump to the next position
Ctrl+^              # Jump to alternate file (the previous file in the current window)
%                   # Match jump to the corresponding {} () []
gd                  # Jump to the local definition (the definition of the word under the cursor)
gD                  # Jump to the global definition (the definition of the word under the cursor)
gf                  # Open the file whose name is the file name under the cursor
[[                  # Jump to the previous top-level function
]]                  # Jump to the next top-level function
[m                  # Jump to the previous member function
]m                  # Jump to the next member function
[{                  # Jump to the previous unmatched {
]}                  # Jump to the next unmatched }
[(                  # Jump to the previous unmatched (
])                  # Jump to the next unmatched )
[c                  # The last difference (when diffing)
]c                  # The next difference (when diffing)
[/                  # Jump to the beginning of the C comment
]/                  # Jump to the end of the C comment
``                  # Go back to the last jumped position
''                  # Go back to the last jumped position
`.                  # Back to the last edited position
'.                  # Back to the last edited position
```

## Movement commands diagram

![vim movement commands](./image/vim-movement_EN.png)

## Open file

```
vim .               # Open the file manager, display the catalog file, edit by selecting the file
vim filename        # Open or create a new file, and place the cursor at the beginning of the first line
vim + filename      # Open the file and place the cursor at the beginning of the last line
vim +n filename     # Open the file and place the cursor at the beginning of line n
vim -c cmd file     # Before opening the file file, execute the specified Vim command cmd
vim -b file         # Open the file in binary mode, some special characters (such as line break ^M) can be displayed in this mode
vim -d file1 file2  # Use Vim to open file1 and file2 at the same time and diff the difference between the two files
vim -r filename     # The system crashed the last time I was editing with Vim, restore the file
vim -R file         # Open the file as read-only, but you can still use :wq! to write
vim -M file         # The modification function is forcibly closed and cannot be used :wq! Write
vim -o file1 file2  # When you want to open a Vim file in the terminal, split and display multiple files horizontally
vim -O file1 file2  # When you want to open a Vim file in the terminal, split and display multiple files vertically
vim -x file         # Open the file encrypted
vim +/target file   # Open file and move the cursor to the first target string found
```

## Save and exit

**Note: Save and exit in normal mode.**

```
:w                  # Write the file and save it, the time stamp of the file will be modified
:w {filename}       # Save file by name
:w !sudo tee %      # Save the file with super user privileges, you can also do this :w !sudo tee%> /dev/null
:wa                 # Save all files
:wall               # Save all files
:wqall              # Save all files and exit
:q                  # Close the window where the cursor is located and exit (q: quit)
:q!                 # Force quit (q: quit)
:qa！               # Abandon all file operations and force exit
:qall               # Abandon all file operations and exit
:x                  # Save the file and exit, the time stamp of the file will not be modified
ZZ                  # Save the changed file, and close the exit window
ZQ                  # Close the window without saving the file
```

## File operations

```
:e[dit] {filename}  # Open the file and edit, open the file by the absolute or relative path of the file, Tab key to complete the path
:e[dit] .           # Open the file manager, browse the files in the current directory, select and edit
:e[dit]             # Reload current file
:E[xplore]          # Open the file manager, and display the directory where the active buffer is located
:saveas {filename}  # Save as specified file
:o {filename}       # Open another file in the current window (o: open)
:r {filename}       # Read the file and insert the content after the cursor
:r !dir             # Capture and insert the output of the dir command after the cursor
:on[ly]             # Close other windows except the window where the cursor is located, same as Ctrl+W o
:clo[se]            # Close the file in the window where the cursor is, the same as Ctrl+W c
:cd {path}          # Switch Vim current path
:cd -               # Go back to the last current directory
:pwd                # Show Vim current path
:n[ew] {filename}   # Open a new window to edit the new file filename
:new                # Open a new window to edit a new file
:ene[w]             # Create a new file in the current window
:vnew               # Edit the new file in a new window divided into left and right
:tabnew             # Edit the new file in a new tab
:fin[d] {file}      # Find the file {file} in path and edit it
:f[ile]             # Display the current file name and cursor position
:f[ile] {name}      # Set the current file name to name
:files              # Show all alternate file names
```

## Opened file operation

```
:ls                 # Investigation cache list
:bn                 # Switch to the next cache
:bp                 # Switch to the previous cache
:bd                 # Delete cache
:b 1                # Switch to cache 1
:b abc              # Switch to the cache whose file name starts with abc
:badd {filename}    # Add files to the cache list
:set hidden         # Set hidden mode (unsaved cache can be switched away or closed)
:set nohidden       # Turn off the hidden mode (unsaved cache cannot be switched away or closed)
n Ctrl+^            # To switch the cache, enter the numeric cache number first, then press Ctrl+6
```

## Multi-window operation

> The split-screen window is based on the Ctrl+W shortcut key, Ctrl is the control function key, W stands for Windom, and Ctrl+W stands for control window.

```
:sp {filename}      # Split the window horizontally and open the file in a new window filename
:vs {filename}      # Split the window vertically and open the file in a new window filename
:split              # Copy the current window to a horizontal window, the content is synchronized, the cursor can be different
:vsplit             # Copy the current window to another vertical window, the content is synchronized, the cursor can be different
Ctrl+W              # Switch to the next window
Ctrl+W s            # Horizo​​ntal split window
Ctrl+W v            # Split window longitudinally
Ctrl+W w            # Cycle to the next window
Ctrl+W W            # Cycle to the previous window
Ctrl+W p            # Skip to the last visited window
Ctrl+W r            # reverse window
Ctrl+W c            # Close the current window, but cannot close the last window
Ctrl+W q            # Exit the current window, if it is the last window, close vi
Ctrl+W o            # Keep only the active window, close other (o: other) windows, same as :on[ly]
Ctrl+W h            # Jump to the left window
Ctrl+W j            # Jump to the window below
Ctrl+W k            # Jump to the upper window
Ctrl+W l            # Jump to the right window
Ctrl+W +            # Increase the row height of the current window, you can add a number in front
Ctrl+W -            # Decrease the row height of the current window, you can add a number in front
Ctrl+W <            # Reduce the column width of the current window, you can add a number in front
Ctrl+W >            # Increase the column width of the current window, you can add a number in front
Ctrl+W =            # Make all windows the same width and height
Ctrl+W H            # Move the current window to the far left
Ctrl+W J            # Move the current window to the bottom
Ctrl+W K            # Move the current window to the top
Ctrl+W L            # Move the current window to the far right
Ctrl+W x            # Exchange window
Ctrl+W f            # Open the file named under the cursor in a new window
Ctrl+W gf           # Open the file named under the cursor in a new tab
Ctrl+W T            # Move the current window to a new tab
Ctrl+W P            # Jump to the preview window
Ctrl+W z            # Close preview window
Ctrl+W _            # Maximize the current window vertically
Ctrl+W |            # Maximize the current window horizontally
```

## Tags

```
:tabs               # Show all tabs
:tabe {filename}    # Open the file filename in a new tab
:tabn[ext]          # Next tab
:tabp[revious]      # Previous tab
:tabc[lose]         # Close current tab
:tabo[nly]          # Close other tabs
:tabn N             # Switch to the Nth tab page, for example: tabn 3 Switch to the third tab page
:tabm n             # Label move
:tabfir[st]         # Switch to the first tab
:tabl[ast]          # Switch to the last tab
:tab help           # Open help in tab
:tab drop {file}    # If the file has been opened by other tabs and windows, skip over, otherwise open a new tab
:tab split          # Open the file in the current window in a new tab
:tab ball           # Open all files in the cache with tabs
:set showtabline=?  # Set to 0 to not display the tab page label, 1 will be displayed on demand, 2 will be permanently displayed
Ngt                 # Switch to the Nth tab page, for example, 2gt will switch to the second tab page
gt                  # Next tab
gT                  # Previous tab
```

## Vim bookmarks

```
:marks              # Show all bookmarks
ma                  # Save the current position to bookmark a, the lowercase letter of the book signature is in the file, and the uppercase global
'a                  # Jump to the line of bookmark a
`a                  # Jump to the location of bookmark a
`.                  # Jump to the last edited line
'A                  # Jump to full text bookmark A
['                  # Jump to the previous bookmark
]'                  # Jump to the next bookmark
'<                  # Jump to the beginning of the last visual mode selection area
'>                  # Jump to the end of the last visual mode selection area
```

## Spell Check

```
:set spell          # Turn on spell check
:set nospell        # Turn off spell check
]s                  # The next misspelled word
[s                  # The last misspelled word
zg                  # Add words to the spelling vocabulary
zug                 # Undo the last word added
z=                  # Spelling suggestion
```

## Code folding

```
zf{motion}          # Operator, manually define a fold (f:fold)
:{range}fold        # Define the lines included in the range {range} as a fold
zf                  # Create code folding
zF                  # Specify the number of rows to create a fold
za                  # Toggle fold
zA                  # Switch folding recursively
zc                  # Close a fold under the cursor (c: close)
zC                  # Close all folds under the cursor (C: Close)
zd                  # Delete the fold under the cursor
zD                  # Recursively delete all folds
zE                  # Delete all folds
zi                  # Toggle fold
zm                  # All codes are folded one level
zM                  # Fold all code, set foldlevel=0, set foldenable
zr                  # All codes open one layer
zR                  # Open all code and set foldlevel to the maximum
zn                  # Fold none, reset foldenable and open all codes
zN                  # Fold Normal, reset foldenable and restore all folds
zo                  # Open a layer of code
zO                  # Turn on all code folding under the cursor
```

## Document encryption/decryption

> The document is encrypted. When you open the file, you will be prompted to enter the password twice in the lower left corner of the screen before you can operate. After saving the file and exiting, you must enter the normal password to open the file correctly, otherwise garbled characters will be displayed.

```
vim -x {filename}   # Enter the encryption password and confirm the password again. Note: Save the content without modifying it, otherwise the password setting will not take effect
:X                  # Enter the encryption password in command mode and confirm the password again. Note: Save the content without modifying it, otherwise the password setting will not take effect
:set key=password   # Enter the encryption password in command mode and confirm the password again. Note: Save the content without modifying it, otherwise the password setting will not take effect
```

> Document decryption, set decryption by command mode.

```
:X                  # In command mode, directly press Enter to indicate that the password is empty. Note: Save the content without modifying it, otherwise the decryption setting will not take effect
:set key=           # Set the key password to be empty in command mode. Note: Save the content without modifying it, otherwise the password setting will not take effect
```

## Macro recording

**Macro is the function of recording and playback. It is an integration of a series of Vim command operations. Using macros can achieve a lot of repetitive work.**

```
qa                  # Start recording the macro named a
q                   # End recording macro
@a                  # Play the macro named a
@@                  # Play the previous macro
@:                  # Repeat the last ex command (colon command)
```

**Macro example**：You need to type a Tab key at the beginning of the following multi-line text to indent the beginning of the line.

```
set nu
set tabstop=4
set shiftwidth=4
set softtabstop=4
set autoindent
set wrap
syntax on
```

### Record macro

- Move the cursor to the first line first.
- In Normal mode, press the q key and a letter to start recording. For example, press qa to register the macro as a.
- Press I to insert at the beginning of the line, and press Tab in edit mode. Press <Esc> to return to Normal mode.
- Press the j key to move the cursor to the next line.
- Press the q key to finish recording.

### Use macro

- Using the macro a recorded above, press @a to play the macro named a.
- Move the cursor to the second line in Normal mode, press @a, and use macro a again.
- Press N@a for multiple operations, where N is a positive integer, which means that the macro is executed N times. For example, move the cursor to line 3, operate macro a on the remaining 5 lines, and press 5@a.

The above **recording macro, using macro** two common operations, complete the beginning of multiple lines of text, type a Tab key to indent the beginning of the line!

## Other commands

```
ga                  # Display the ASCII code or Unicode code of the character under the cursor
g8                  # Display the UTF-8 encoding byte order of the character under the cursor
gi                  # Go back to the place where you entered the insert last time, and switch to insert mode
K                   # Query the help of the word under the cursor
Ctrl+G              # Display the name of the file being edited, as well as size and location information
g Ctrl+G            # Display file size, number of characters, number of words and number of lines, also available in visual mode
Ctrl+PgUp           # On the last tab page, GVim OK, some terminal software needs to set the corresponding keyboard code
Ctrl+PgDown         # The next tab page, GVim OK, some terminal software needs to set the corresponding keyboard code
Ctrl+R Ctrl+W       # Insert the word under the cursor in command mode
Ctrl+Insert         # Copy to the system clipboard (GVIM)
Shift+Insert        # Paste the contents of the system clipboard (GVIM)
Ctrl+X Ctrl+E       # Scroll up in insert mode
Ctrl+X Ctrl+Y       # Scroll down in insert mode
:map                # To view the map shortcuts of the current Vim configuration
:inoremap           # To view the inoremap shortcuts of the current Vim configuration
:nnoremap           # To view the nnoremap shortcuts of the current Vim configuration
:set ff=unix        # Set change behavior unix
:set ff=dos         # Set change behavior dos
:set ff?            # View line break settings
:set nohl           # Clear search highlight
:set termcap        # See what will be received from the terminal and what commands will be sent to the terminal
:set guicursor=     # Solve the problem of some strange characters in NeoVim in SecureCRT/PenguiNet
:set t_RS= t_SH=    # Solve the strange characters in the Vim8.0 terminal function in SecureCRT/PenguiNet
:set fo+=a          # Enable real-time automatic formatting of text segments
:earlier 15m        # Go back to the contents of the file 15 minutes ago
:.!date             # Insert time in current window
:%!xxd              # Start binary editing
:%!xxd -r           # Save binary edit
:r !curl -sL {URL}  # After reading the URL content and adding it to the cursor
:g/^\s*$/d          # Delete blank lines
:g/green/d          # Delete all lines containing green
:v/green/d          # Delete all lines that do not contain green
:g/gladiolli/#      # Search words and print the results, and add the line number before the results
:g/ab.*cd.*efg/#    # Search for lines containing ab, cd and efg, print the result and line number
:v/./,/./-j         # Compress blank lines
:Man bash           # View man in Vim, first call :runtime! ftplugin/man.vim to activate
/fred\|joe          # Search for fred or joe
/\<\d\d\d\d\>       # Search exactly four numbers
/^\n\{3}            # Search for three consecutive blank lines
```

## History commands

History command format:

```
:his[tory] [{name}] [{first}][, [{last}]]
```

Parameter Description:

- {name}：Specifies the history type.
- {first}：Specifies the starting position of the command history, defaults to the first record.
- {last}：Specifies where the command history ends, defaults to the last record.

In command line mode.

```
:his[tory]                # View the history of all commands entered in the command line mode
:his[tory] all            # Show all types of history
:history c 1,5            # List the first to fifth command line history
:history search or / or ？ # View search history
:call histdel("")         # delete history
:help :history            # See help for the :history command
```

In normal mode.

```
q/                  # View search history used q/ entered
q?                  # View usage q? Entered search history
q:                  # View command line history
```

## Register

**View register value.**

```
:reg                   # View all register values
:reg {register}        # View the specified register value
```

**Recall register value.**

```
"{register}            # Recall register value in normal mode
:Ctrl+r "registerName  # After entering Ctrl+r in command mode, Vim will automatically type "register reference symbol
Ctrl+r registerName    # In insert mode (no need to enter register reference symbol ")
```

**Vim register classification**

| Register name         | Citation method    | Description                                                                                                                                                                                                                                                                                                                                       |
| --------------------- | ------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Unnamed register      | ""                 | The default register, all copy and modify operations (x, s, d, c, y) will copy the data to the unnamed register                                                                                                                                                                                                                                   |
| Named register        | "a - "z or "A - "Z | {register} can only be one of 26 English letters, from a-z, A-Z register contents will be merged into the corresponding lowercase letters                                                                                                                                                                                                         |
| Copy special register | "0(Number 0)       | Only when the copy operation (y) is used, the data will be copied to the unnamed register and the copy special register at the same time                                                                                                                                                                                                          |
| Numbered register     | "1 - "9            | All data without ranges ('(',')','{','}') and operations involving more than 1 line of delete and modify operations (x, s, d, c) will be copied to the stepwise temporary cache register , And when new data is added, it progresses step by step. The data of 1 is copied to 2, 2 to 3, and the contents of the last 9 registers will be deleted |
| Black hole register   | "\_                | Almost all the data involved in the operation will be copied to the register. If you want the data to be operated not to pass through the register, you can specify a black hole register. The data will disappear when the register arrives, and it cannot be displayed and does not exist.                                                      |
| System clipboard      | "+ or "\*          | When interacting with the GUI external to Vim, you need to use a special system clipboard                                                                                                                                                                                                                                                         |
| Expression register   | "=                 | The most special one of all registers is used to calculate expressions. After entering the register application, it will prompt "=" in the command line, enter the expression as needed, and the result will be displayed at the cursor                                                                                                           |
| Other registers       | -                  | -                                                                                                                                                                                                                                                                                                                                                 |

## Vim configuration file

> Note: Vim configuration files are available in global and user versions, and user configuration files take precedence over global system configuration files.

```
:ve[rsion]          # Check the Vim version, and also check the priority order and location of Vim loading configuration files
:echo $MYVIMRC      # Use this command in Vim command mode to output the location of the Vim configuration file
:edit $MYVIMRC      # Use this command to open the Vim configuration file in Vim command mode
:so[urce] $MYVIMRC  # After the Vim configuration file is changed, use this command to load the new configuration options. If the vimrc file happens to be the currently active buffer, this command can be simplified to: so %.
:echo $VIM          # Output the location of the global vimrc configuration file, stored in the Vim installation directory
:echo $HOME         # Output the location of the user vimrc configuration file, stored in the user's home directory
```

**Vim configuration instructions, please refer to [vimrc configuration file](../vimrc) for details. Note: Vim configuration can be set individually in command mode and only takes effect in the current window！**

```
syntax              # List the defined grammar items
syntax clear        # Clear defined grammar rules
syntax on           # Allow syntax highlighting
syntax off          # Prohibit syntax highlighting
set history=200     # Record 200 historical commands
set bs=?            # Set Backspace key mode, modern editor is :set bs=eol,start,indent
set sw=4            # Set the indent width to 4
set ts=4            # Set the tab width to 4
set noet            # Set not to expand Tab to space
set et              # Set expand Tab to space
set winaltkeys=no   # Set the normal capture of the Alt key under GVim
set nowrap          # Turn off word wrap
set ttimeout        # Allow terminal key detection to time out (the function key under the terminal is a series of scan codes starting with Esc)
set ttm=100         # Set the terminal key detection timeout to 100 milliseconds
set term=?          # Set the terminal type, such as the common xterm
set ignorecase      # Set whether the search ignores case
set smartcase       # Smart case, ignore case by default, unless the search content contains uppercase letters
set list            # Set to display tabs and line breaks
set nu              # Set the display line number, you can use :set nonu to prohibit the display line number
set number          # Set the display line number, you can use :set nonumber to prohibit the display line number
set relativenumber  # Set display relative line number (distance between other lines and current line)
set paste           # Enter paste mode (disable indentation when pasting and other things that affect formatting)
set nopaste         # End paste mode
set spell           # Allow spell checking
set hlsearch        # Set highlight search
set ruler           # Always show cursor position
set nocompatible    # The setting is not compatible with the original vi mode (must be set at the very beginning)
set incsearch       # Dynamic incremental display of search results during search input
set insertmode      # Vim is always in insert mode, use Ctrl+o to execute commands temporarily
set all             # List all option settings
```

## Vim plugins

**[vim-commentary](https://github.com/tpope/vim-commentary)**：Vim batch comment tool, you can comment multiple lines and remove multiple lines of comments.

```
gcc                 # Comment the current line
gc{motion}          # Annotate the area marked by {motion}, such as gcap annotate the entire paragraph
gci{                # Comment the content in braces
gc                  # Press gc to annotate the selected area under Visual Mode
:7,17Commentary     # Comment lines 7 to 17
```

**[NERDTree](https://github.com/preservim/nerdtree)**：This plugin is used to list the directory tree of the current path.

```
?                   # Quick help document
o                   # Open a directory or open a file, create a buffer, can also be used to open bookmarks
go                  # Open a file, but the cursor remains in NERDTree, creating a buffer
t                   # Open a file and create a Tab, which is also effective for bookmarks
T                   # Open a file, but the cursor still stays in NERDTree. Tab is created, which is also effective for bookmarks
i                   # Split the window to create the file horizontally, creating a buffer
gi                  # Split the window where the file was created horizontally, but the cursor remains in NERDTree
s                   # Split the window that creates the file vertically, creating a buffer
gs                  # Similar to gi and go
x                   # Collapse the currently open directory
X                   # Collapse all open directories
e                   # Open the selected directory by file management
D                   # Delete bookmark
P                   # Uppercase, jump to the current root path
p                   # Lowercase, jump to the previous path where the cursor is located
K                   # Jump to the first subpath
J                   # Jump to the last subpath
C                   # Set the root path to the directory where the cursor is
u                   # Set the parent directory as the root path
U                   # Set the parent directory to follow the path, but keep the original directory open
r                   # Refresh the directory where the cursor is
R                   # Refresh the current root path
I                   # Show or not show hidden files
f                   # Turn file filters on and off
q                   # Close NERDTree
A                   # Show NERDTree in full screen, or close full screen
Ctrl+j Ctrl+k       # Move between directories and files at the same level, ignoring subdirectories and subfiles
```

**[asyncrun.vim](https://github.com/skywind3000/asyncrun.vim)**：The plug-in uses the asynchronous mechanism of Vim 8 / NeoVim, allowing you to run Shell commands in the background and display the results in Vim's Quickfix window in real time.

```
:AsyncRun ls        # Run the command ls asynchronously and output the result to quickfix. Use :copen to view
:AsyncRun -raw ls   # Run the command asynchronously, the result of ls does not match errorformat
```

## Vim mode

```
Normal mode         # Press <Esc> or Ctrl+[ to enter, the file name is displayed in the lower left corner or empty
Insert mode         # Press i to enter, the lower left corner shows --INSERT--
Visual mode         # Press v to enter, the lower left corner shows --VISUAL--
Replacement mode    # Press r or R to start, the lower left corner shows --REPLACE--
Command line mode   # Press : or / or ? To start
```

## External command

```
:!{command}         # Execute a one-time Shell command, the following command: :!pwd, change the directory in the current Vim mode
:!!                 # Re-execute the most recently run command
:sh[ell]            # Start an interactive Shell to execute multiple commands, the exit command exits and returns to Vim
:!ls                # Run the external command ls and wait for the return
:r !ls              # Capture the output of the external command ls and insert it after the cursor
:w !sudo tee %      # sudo saves the current file in the future, it can also be like this :w !sudo tee % > /dev/null
:call system('ls')  # Call the ls command, but do not display the returned content
:!start notepad     # Start Notepad under Windows, you can add silent at the top
:sil !start cmd     # Open cmd in the current directory under Windows
:%!prog             # Run a text filter program, such as sorting JSON format:%!python -m json.tool
```

## Quickfix window

```
:copen              # Open the quickfix window (view compilation, grep and other information)
:copen 10           # Open the quickfix window and set the height to 10
:cclose             # Close the quickfix window
:cfirst             # Jump to the first error message in quickfix
:clast              # Jump to the last error message in quickfix
:cc [nr]            # View error [nr]
:cnext              # Skip to the next error message in quickfix
:cprev              # Jump to the previous error message in quickfix
```

## Help information

```
:h[elp] {command}   # To display the help of related commands, you can also enter :help instead of the command. To exit the help, you need to enter :q
:h tutor            # Getting started document
:h quickref         # Quick help
:h index            # Query all keyboard command definitions in Vim
:h summary          # Help you better use the built-in help system
:h Ctrl+H           # Query what Ctrl+H does in normal mode
:h i_Ctrl+H         # Query what does Ctrl+H do in insert mode
:h i_<Up>           # Query what is on the arrow keys in insert mode
:h pattern.txt      # Regular expression help
:h eval             # Scripting help
:h function-list    # View the list of functions in VimScript
:h windows.txt      # Window help
:h tabpage.txt      # Help on using tabs
:h +timers          # Show help for the +timers feature
:h :!               # See how to run external commands
:h tips             # View the documentation of common techniques built into Vim
:h set-termcap      # See how to set the key scan code
:viu[sage]          # Displays help for common commands. The purpose is to simulate the corresponding Nvi commands
:exu[sage]          # Displays help for the Ex command. The purpose is to simulate the corresponding Nvi commands
:ve[rsion]          # View the Vim version, and also view the priority and location of the Vim load configuration file
```

## Vim keyboard diagram

![vim keyboard diagram](./image/vim-keys_EN.png)
