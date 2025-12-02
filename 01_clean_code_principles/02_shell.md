# Shell
## Command Lines
The command line—also called the command-line interface (CLI)—is the place where you type commands to interact with your computer instead of clicking icons like in a GUI. You can use it to:

* Manage files
* Control your development environment (for example, install packages or create virtual environments)
* Automate repetitive tasks

**Terminology**:

* **Linux**: An operating system. Open source & customizable. Commonly used for servers & supercomputers. Commonly operated through the CLI. Linux is a widely used OS for coding.
* **Shell**: A programme that lets you interact with the operating system, e.g., Linux. Interprets the commands you type in the CLI. Shell examples: Bash, zsh, etc. It is important tool for deployment and remote system administration. 
* **CLI**: Command Line Interface. The concept of interacting with the OS through typing commands. Displayed inside an app (e.g., Terminal (MacOS), VS Code, etc. Same app and CLI can run several different shells.

![terminal](imgs/terminal.png)


## 1. Fundamentals
**echo — Print Text or Variables**  
Displays text or the value of a variable.  
Examples:  
- `echo "Hello world"` → prints *Hello world*  
- `echo $COLUMNS x $LINES` → prints your terminal size in columns and lines

Additional useful echo usage:  
- `echo $0` → shows which shell you are currently running (e.g., *bash*, *zsh*)  

**clear — Clear the Terminal Screen**  
Removes visible text from the terminal but does not stop or reset any processes.  
Examples:  
- `clear` → clears the current terminal view  
- Pressing `Ctrl + L` → same effect as `clear`

**Kill a Process (Interrupt) — Ctrl + C**  
Stops the currently running foreground command. Use this when something gets stuck—often due to missing quotes or commands waiting for input.  
Examples:  
- Press `Ctrl + C` while a command is hanging → interrupts it  
- Start `sleep 100` then press `Ctrl + C` → stops the sleep command immediately
## 2. Navigating directories
**pwd — Print Working Directory**  
Shows the full path of the folder you are currently in.  
Examples:  
- `pwd` → prints the current directory  
- After moving folders, `pwd` confirms your location

**ls — List Directory Contents**  
Shows files and folders in the current or specified directory.  
Examples:  
- `ls` → lists items in the current folder  
- `ls /etc` → lists items inside `/etc`

**ls -l — Long Format Listing**  
Shows detailed info: permissions, owner, size, date.  
Examples:  
- `ls -l` → detailed list of current directory  
- `ls -l Documents/*.pdf` → detailed list of PDF files in Documents

**cd — Change Directory**  
Moves you into another folder.  
Examples:  
- `cd Documents` → enter the Documents folder  
- `cd /usr/local/bin` → go to an absolute path

**cd .. — Go Up One Directory**  
Moves to the parent directory.  
Examples:  
- `cd ..` → from `/home/user/Documents` to `/home/user`  
- `cd ../..` → go up two levels

**.. — Parent Directory Symbol**  
Represents the folder above your current one.  
Examples:  
- `ls ..` → list the parent directory  
- `cd ../Projects` → go up one level, then enter Projects

## 3. Organising your files — Create & Delete
**touch — Create Empty Files**  
Creates a new file or updates the timestamp of an existing one.  
Examples:  
- `touch notes.txt` → creates an empty file named *notes.txt*  
- `touch a b c` → creates three empty files

**mkdir — Make a Directory**  
Creates a new folder.  
Examples:  
- `mkdir Photos` → creates a folder named *Photos*  
- `mkdir project/src` → creates nested folders if the path exists

**rm — Delete Files**  
Removes a file permanently.  
Examples:  
- `rm file.txt` → deletes *file.txt*  
- `rm *.log` → deletes all `.log` files in the current folder

**rmdir — Remove Empty Directory**  
Deletes a folder only if it contains no files.  
Examples:  
- `rmdir OldFolder` → removes *OldFolder* (if empty)  
- `rmdir temp` → deletes *temp* only when it has no content

**rm -r — Remove Directory Recursively**  
Deletes a directory *and everything inside it permanently*.  
Examples:  
- `rm -r build` → deletes the *build* folder and its contents  
- `rm -r backups/old` → removes *old* and all files inside it

## 4. Organising your files — Copy, Move & Rename
**mv — Move or Rename Files**  
Moves a file or directory to a new location, or renames it if the destination does not already exist.  
Examples:  
- `mv report.csv archive/` → moves *report.csv* into the *archive* directory  
- `mv draft.txt final.txt` → renames *draft.txt* to *final.txt*

**cp — Copy Files**  
Creates a duplicate of a file without altering the original.  
Examples:  
- `cp config.yaml config_backup.yaml` → makes a backup copy  
- `cp notes.txt ~/Documents/` → copies *notes.txt* to *Documents*

**cp -r — Copy Directories Recursively**  
Copies an entire directory *and all of its contents* (files, subfolders, etc.).  
Examples:  
- `cp -r src/ src_backup/` → duplicates the *src* directory  
- `cp -r projectA/ projects/projectA_copy/` → creates a full copy of *projectA* in another location

## 5. Viewing, Writing, and Reading Files
**echo — Print Text or Write to Files**  
Prints text to the terminal or redirects it into a file.  
Examples:  
- `echo 'Hello world'` → prints *Hello world* to the terminal  
- `echo 'Log entry' >> app.log` → appends *Log entry* to *app.log* without overwriting it

**echo > — Overwrite File with Text**  
Writes text into a file, replacing its previous contents (creates the file if it doesn’t exist).  
Examples:  
- `echo 'Welcome' > welcome.txt` → creates/overwrites *welcome.txt* with *Welcome*  
- `echo 'Reset' > status.txt` → clears previous content and writes *Reset*

**echo >> — Append Text to File**  
Adds text to the end of a file without deleting existing content.  
Examples:  
- `echo 'New record' >> data.txt` → appends a line to *data.txt*  
- `echo 'Error: missing value' >> errors.log` → adds an error message to a log

**cat — View or Combine File Contents**  
Displays file contents or redirects them into another file.  
Examples:  
- `cat notes.txt` → prints the full contents of *notes.txt*  
- `cat input.txt > output.txt` → overwrites *output.txt* with *input.txt* contents

**less — View Files One Screen at a Time**  
Interactive viewer for large files (use space/arrow keys to scroll, **b** to go back, **/** to search, **q** to quit).  
Examples:  
- `less large_report.txt` → view a long report interactively  
- `less /var/log/system.log` → explore logs page by page

## 6. Downloading Files
**curl — Transfer Data from or to a URL**  
`curl` retrieves data from URLs. The name comes from “see URL.” It can download web pages, files, APIs, and more.

Options commonly used:  
- `-o FILE` → save output to a file  
- `-L` → follow redirects (useful when URLs forward to another location)

Examples:  
- `curl -o google.html -L 'http://google.com'` → downloads the Google homepage to *google.html*, following redirects  
- `curl -o data.json 'https://api.example.com/data'` → saves API output into *data.json*

## 7. Searching & Replacing
**find — Search for Files and Directories**  
Searches recursively from a starting path using filters like name, type, and case sensitivity.  
Common paths:  
- `.` → current directory  
- `..` → parent directory  
- `~` → home directory (use with caution for large searches)  
- `/` → root directory (very expensive to search)

Common options:  
- `-name 'pattern'` → search by name  
- `-iname 'pattern'` → case-insensitive name search  
- `-type f` → files only  
- `-type d` → directories only  
- Combine options freely

Examples:  
- `find . -name 'forest*'` → finds items in the current directory that start with *forest*  
- `find ~/projects -type d -iname 'test*'` → finds directories named like *test...* in your *projects* folder
---
**grep — Search Text for Patterns**  
Prints lines that match a pattern, using regular expressions.  
Useful options:  
- `-n` → show line numbers  
- `-i` → case-insensitive search  
- `-r` → recursive search through directories

Examples:  
- `grep 'CEO' team.txt` → prints lines containing “CEO”  
- `grep -rn 'error' logs/` → recursively search for *error* in all files under *logs*
---
**wc — Count Lines, Words, and Bytes**  
Prints text statistics from files or standard input.

Examples (expanded):  
- `wc report.txt`  
  - `wc` → run the *word count* command  
  - `report.txt` → the file wc should read  
  → Output shows: number of **lines**, **words**, and **bytes** in *report.txt*
- `cat data.csv | wc -l`  
  - `cat data.csv` → print the contents of *data.csv*  
  - `|` → pipe the printed contents as input to the next command  
  - `wc -l` → run wc with `-l` to count **only lines**  
  → Result: total number of lines in *data.csv*
---
**sed — Search and Replace Text**  
A stream editor that edits text in a pipeline.  
Pattern: `sed 's/pattern/replacement/' file`

Examples (expanded):  
- `sed 's/,/:/' team.txt`  
  - `sed` → run the stream editor  
  - `s` → substitute command  
  - `,` → the pattern to search for  
  - `:` → the replacement  
  - `/` → delimiter separating parts  
  - `team.txt` → file to read  
  → Replaces **only the first comma** on each line with a colon and prints the result.

- `sed 's/a/z/gI' team.txt`  
  - `s` → substitute  
  - `a` → search for the letter “a”  
  - `z` → replace it with “z”  
  - `g` → replace **all** matches in each line (global)  
  - `I` → ignore case (match "a" or "A")  
  → Every “a” or “A” in each line becomes “z”, printed to the terminal.
---
**Redirecting sed Output**

Examples (expanded):  
- `sed 's/,/:/' team.txt > colon_team.txt`  
  - Everything to the left of `>` behaves as before (replace first comma with colon)  
  - `>` → redirect output  
  - `colon_team.txt` → file to write the output into  
  → Creates/overwrites *colon_team.txt* with the modified text.

- `sed -i 's/CEO/Chief Executive Officer/' team.txt`  
  - `sed -i` → edit in place (modify the file directly)  
  - `s/CEO/Chief Executive Officer/` → replace the text “CEO” with the full phrase  
  - `team.txt` → file to edit  
  → Updates *team.txt* on disk, replacing “CEO” everywhere it appears.

## 8. Counting, Organising & Using Pipes
**wc — Count Lines, Words, Bytes, or Characters**  
Reports statistics about a file.  
- `wc FILENAME` → shows lines, words, and bytes  
- `wc -l` → lines only  
- `wc -w` → words only  
- `wc -c` → bytes only  
- `wc -m` → characters only  

Examples:  
- `wc notes.txt` → prints count of lines/words/bytes in *notes.txt*  
- `wc -l logs/error.log` → shows how many lines are in the error log  

**sort — Sort File Content**  
Sorts lines alphabetically (A–Z) by default.  
- `sort -r` → reverse alphabetical (Z–A)  
- `sort -n` → numeric sort  

Examples:  
- `sort names.txt` → sorts names alphabetically  
- `sort -n scores.txt` → sorts numbers in *scores.txt* from least to greatest  

**uniq — Remove Adjacent Duplicate Lines**  
`uniq` removes duplicates *only when they appear next to each other*, which is why it is commonly paired with `sort`.

Examples:  
- `uniq items.txt` → removes consecutive duplicate lines in *items.txt*  
- `sort items.txt | uniq` → first sorts, then removes all duplicates  

**Pipes ( | ) — Send Output from One Command Into Another**  
A pipe takes the output of one command and feeds it as input into the next.

Examples:  
- `sort team.txt | uniq` → sorts the file, then removes all duplicates  
- `wc -l data.csv | sort -n` → counts lines, then sorts numeric output  

**Redirecting Output ( > ) — Save Results to a File**  
Commands do **not** modify the original file unless you redirect the output.

Examples:  
- `sort team.txt | uniq > sorted_team.txt` → saves unique, sorted names  
- `wc -l logs.txt > line_count.txt` → writes the line count to a new file

## 9. Shell Startup Files, Scripts, and Aliases
**Shell Scripts (`*.sh`)**  
Files containing shell commands. Running a script executes the commands inside it.

Examples:  
- `bash backup.sh` → runs *backup.sh*  
- `./setup.sh` → executes *setup.sh* (requires execute permission)

**Startup Files (`.bashrc` and `.bash_profile`)**  
Variables, aliases, and custom settings reset when you close a terminal unless stored in a startup file.  
- `.bash_profile` runs **once** when a login shell starts.  
- `.bashrc` runs for **every interactive shell**. Many systems load `.bashrc` from `.bash_profile`.

Typical setup steps:  
1. Navigate to your home directory  
2. `touch .bashrc` → create the file if it doesn’t exist  
3. `vim .bashrc` → edit it  
4. Save and exit with `:wq`  
5. Restart your shell  
6. Git Bash will automatically create `.bash_profile` and source your `.bashrc`

**alias — Create Shortcuts for Commands**  
Lets you define shorter or more convenient command names.

Examples:  
- `alias ll='ls -la'` → `ll` now runs `ls -la`  
- `alias gs='git status'` → quick shortcut for checking Git status

## 10. Shell and Environment Variables

**Shell Variables**  
Variables you create in the shell exist only for the current session.

Examples:  
- `numbers='one two three'` then `echo $numbers` → prints `one two three`  
- `count=5` then `echo $count` → prints `5`

You can inspect built-in shell variables too:  
- `echo $LINES x $COLUMNS` → prints terminal size (rows × columns)

**Environment Variables**  
These are inherited by programs launched from the shell. They control things like search paths, language settings, and configuration.

Examples:  
- `echo $PATH` → shows the list of directories the shell searches for commands  
- `export TOKEN=abc123` → creates an environment variable available to child processes

**PATH — Where the Shell Looks for Programs**  
The `PATH` variable contains directories separated by `:`. When you run a command, the shell searches these directories in order.

Examples:  
- `echo $PATH` → prints something like `/usr/local/bin:/usr/bin:/bin:/usr/sbin:/sbin`  
- `PATH="$PATH:$HOME/bin"` → adds your personal `bin` directory to the search path

## 12. Jupyter Notebooks
`jupyter notebook --NotebookNotary.db_file=:memory:`

## 13. Continue Learning
* [Udacity Free Course](https://www.udacity.com/course/shell-workshop--ud206)
* [Bash Academy](https://guide.bash.academy/)
* [Beguineers Guide](https://tldp.org/LDP/Bash-Beginners-Guide/html/)
* [Bash Programming](https://tldp.org/HOWTO/Bash-Prog-Intro-HOWTO.html)





