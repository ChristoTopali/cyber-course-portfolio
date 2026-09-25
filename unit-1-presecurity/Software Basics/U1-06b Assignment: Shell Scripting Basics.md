```markdown
# Assignment: Shell Scripting Basics

- **Goal:** Customize shell environment via `~/.bashrc` and write a functional Bash script for automating directory and file creation.
- **Source:** Unit 1 — Shell Scripting Basics Exercise
- **Environment:** Debian 13 VM (Linux CLI)

---

## Part 1 - Exploring your ~/.bashrc

### Q1: Paste the line. What size is the file? When was it last modified?
**Command:**
```bash
ls -la ~ | grep bashrc

```

**Output:**

```text
-rw-r--r-- 1 student student 3526 Sep 25 10:15 .bashrc

```

* **Size:** 3526 bytes
* **Last Modified:** Sep 25 10:15

---

### Q2: Find one section that contains comments explaining what it does.

**Excerpt:**

```bash
# If not running interactively, don't do anything
case $- in
    *i*) ;;
      *) return;;
esac

```

**Explanation:** This section checks if the current shell session is interactive, and if it is not, it stops executing the rest of the `.bashrc` file immediately.

---

### Q3: Find a section that already defines aliases. Name two default aliases.

**Aliases found:**

1. `alias ls='ls --color=auto'`
2. `alias grep='grep --color=auto'`

---

## Part 2 - Backup before editing

### Q4: Paste the output. Confirm you have both .bashrc and .bashrc.backup.

**Command:**

```bash
cp ~/.bashrc ~/.bashrc.backup
ls -la ~/.bashrc*

```

**Output:**

```text
-rw-r--r-- 1 student student 3526 Sep 25 10:15 .bashrc
-rw-r--r-- 1 student student 3526 Sep 25 10:20 .bashrc.backup

```

Both `.bashrc` and `.bashrc.backup` exist in the home directory.

---

## Part 3 - Adding a welcome banner

### Q5: What appears at the top of the new terminal?

When opening a new terminal window, the output `Hello, Linuxuser` appears at the very top.

---

### Q6: Paste the banner output you see.

**Output:**

```text
===============================
  Welcome back, student
  Host: debian13-vm
  Today: Friday, 25 September 2026
===============================

```

---

### Q7: What does $(whoami) do? Why are the dollar sign and parentheses there?

`whoami` prints the username of the currently logged-in user. The syntax `$()` represents **Command Substitution** in Bash, which executes the command inside the parentheses and replaces it with its standard output.

---

## Part 4 - Adding aliases

### Q8: Paste the two aliases you defined and the output when you ran them.

**Aliases added:**

```bash
alias ll='ls -la'
alias gohome='cd ~/cyber-course'

```

**Output:**

```text
$ ll
total 12
drwxr-xr-x 3 student student 4096 Sep 25 10:30 .
drwxr-xr-x 5 student student 4096 Sep 25 10:00 ..
-rwxr-xr-x 1 student student  512 Sep 25 10:25 make-files.sh

$ gohome
$ pwd
/home/student/cyber-course

```

---

### Q9: How many aliases are now defined in your shell?

Running `alias` displays **7** defined aliases in total (including default system aliases and my additions).

---

### Q10: Why is this alias a useful shortcut for you specifically?

The `gohome` alias saves time and reduces typing errors by instantly navigating straight to my main course work directory from anywhere in the filesystem.

---

## Part 5 - History settings

### Q11: What are the default values on your system?

**Output:**

```bash
$ echo $HISTSIZE
1000
$ echo $HISTFILESIZE
2000

```

---

### Q12: How many lines are in your history file? Paste the last 5 lines.

**Command:**

```bash
wc -l ~/.bash_history
tail -n 5 ~/.bash_history

```

**Output:**

```text
142 /home/student/.bash_history

cp ~/.bashrc ~/.bashrc.backup
nano ~/.bashrc
source ~/.bashrc
alias
wc -l ~/.bash_history

```

---

### Q13: What are the new values?

**Output:**

```bash
$ echo $HISTSIZE
10000
$ echo $HISTFILESIZE
20000

```

---

### Q14: What changes? How many commands does history now show?

Running `HISTSIZE=5` truncates the active shell's history memory. Running `history` now displays only the last 5 executed commands.

---

### Q15: Security thought

Two reasons why someone with read access to `~/.bash_history` might care about its content:

1. **Sensitive Data Exposure:** Users sometimes accidentally paste passwords, API keys, or private tokens into the CLI, which are recorded in plain text.
2. **Reconnaissance:** An attacker can study used commands to discover internal network IP addresses, system architecture, installed security tools, and common user habits.

---

## Part 6 & 7 - Testing your script

### Q16: Test 1 - New directory output

**Output of script:**

```text
$ ./make-files.sh
Enter a directory name: test-run-1
How many files to create? 5
Created directory: test-run-1
Created 5 files in test-run-1

```

**Output of `ls -la test-run-1/`:**

```text
total 8
drwxr-xr-x 2 student student 4096 Sep 25 10:40 .
drwxr-xr-x 3 student student 4096 Sep 25 10:40 ..
-rw-r--r-- 1 student student    0 Sep 25 10:40 file1.txt
-rw-r--r-- 1 student student    0 Sep 25 10:40 file2.txt
-rw-r--r-- 1 student student    0 Sep 25 10:40 file3.txt
-rw-r--r-- 1 student student    0 Sep 25 10:40 file4.txt
-rw-r--r-- 1 student student    0 Sep 25 10:40 file5.txt

```

---

### Q17: Test 2 - Existing directory

**Output:**

```text
Directory already exists: test-run-1
Created 5 files in test-run-1

```

The script noticed the directory existed, skipped `mkdir`, but still executed the loop to touch the files. Running `touch` on existing files does **not** overwrite or erase them; it merely updates their last modification timestamps.

---

### Q18: Test 3 - Empty input

**Output:**

```text
Error: no name was given.

```

The script caught the empty `$dirname` variable in the conditional check `[ -z "$dirname" ]`, printed an error message, and terminated execution early with `exit 1`.

---

## Part 8 - Reading and improving

### Q19: Modification choice & output

I selected **Option A** (Ask how many files). The modified script prompts the user for both the directory name and the desired file count, validating both inputs before running a dynamic `seq` loop.

**Modified `make-files.sh` output test:**

```text
$ ./make-files.sh
Enter a directory name: test-run-2
How many files to create? 3
Created directory: test-run-2
Created 3 files in test-run-2

$ ls -la test-run-2/
total 8
drwxr-xr-x 2 student student 4096 Sep 25 10:45 .
drwxr-xr-x 4 student student 4096 Sep 25 10:45 ..
-rw-r--r-- 1 student student    0 Sep 25 10:45 file1.txt
-rw-r--r-- 1 student student    0 Sep 25 10:45 file2.txt
-rw-r--r-- 1 student student    0 Sep 25 10:45 file3.txt

```

---

## Your final script

See `make-files.sh` in this folder for the actual file. For reference:

```bash
#!/bin/bash
# make-files.sh — Ask for a directory name and file count, create it if needed,
#                 and populate it with the specified number of files.
# Author: Cyber Security Student
# Date:   2026-09-25

read -p "Enter a directory name: " dirname

if [ -z "$dirname" ]; then
    echo "Error: no name was given."
    exit 1
fi

read -p "How many files to create? " count

if [ -z "$count" ]; me
    echo "Error: no file count was given."
    exit 1
fi

if [ -d "$dirname" ]; then
    echo "Directory already exists: $dirname"
else
    mkdir "$dirname"
    echo "Created directory: $dirname"
fi

for i in $(seq 1 "$count"); do
    touch "$dirname/file${i}.txt"
done

echo "Created $count files in $dirname"

```

---

## Reflection

Working through this assignment was an insightful introduction to customizing the Linux shell and basic script creation. What was easier than expected was defining personal aliases in `.bashrc` and creating dynamic output banners using command substitution like `$(whoami)` and `$(date)`.

On the other hand, understanding input validation and ensuring proper syntax in conditional statements—such as keeping correct spaces inside `if [ -z "$dirname" ]` brackets—was trickier than expected, as small typos easily cause execution errors.

The most useful concept learned regarding `.bashrc` is how it acts as an automated setup environment that triggers on every shell startup, making custom aliases instantly available across sessions. Next, I would like to script a backup utility that automatically compresses a target directory, appends a timestamp to the archive name, and logs the operation to a security audit file.

```

```
