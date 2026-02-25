# Bash Practice Tasks for Beginners

---

## Task 1 - If Condition (File Check)
**Write a script that takes a filename as an argument. If the file exists, print "File found". If not, print "File not found".**

💡 Hint: Use `[ -f "$1" ]` to check if a file exists

---

## Task 2 - For Loop (Countdown)
**Write a script that counts down from 5 to 1 and then prints "Go!".**

💡 Hint: Use `for i in 5 4 3 2 1`

---

## Task 3 - While Loop (Guessing Game)
**Write a script that picks a secret number (set it to 7). Ask the user to guess. If wrong, print "Wrong, try again". If correct, print "You got it!" and stop.**

💡 Hint: Use `while` with `read`

---

## Task 4 - For Loop (Create Users List)
**Write a script that has a list of 3 names. For each name, print "Creating user: NAME".**

💡 Hint: `for name in Alice Bob Charlie`

---

## Task 5 - If + Else If (Grade Checker)
**Write a script that asks for a test score (0-100). Print:**
- **90-100: "A"**
- **80-89: "B"**
- **70-79: "C"**
- **Below 70: "F"**

💡 Hint: Use `if`, `elif`, `else` with `-ge` (greater or equal)

---

## Task 6 - For Loop (Rename Files)
**Write a script that renames all `.txt` files in the current directory to `.bak`. Print what you renamed.**

💡 Hint: `${file%.txt}` removes the `.txt` part from a variable

---

## Task 7 - While Loop (Menu)
**Write a script that shows this menu and keeps running until the user picks 3:**
```
1) Say Hello
2) Show Date
3) Exit
```

💡 Hint: Use `while` + `read` + `if/elif`

---

## Task 8 - For Loop (Ping 3 Servers)
**Write a script that pings 3 IPs: `8.8.8.8`, `1.1.1.1`, `192.168.1.1`. For each one print if it responded or not. Use 1 ping only.**

💡 Hint: `ping -c 1 -W 1 IP > /dev/null 2>&1` then check `$?`

---

## Task 9 - If (Disk Space Check)
**Write a script that checks disk usage of `/`. If it's above 80%, print "WARNING: disk almost full". Otherwise print "Disk OK".**

💡 Hint: `df / | tail -1 | awk '{print $5}' | tr -d '%'` gives you the number

---

## Task 10 - For Loop (Read From File)
**Create a file called `servers.txt` with 3 server names (one per line). Write a script that reads each line and prints "Checking server: NAME".**

💡 Hint: `while read line; do ... done < servers.txt`

---

## Cheat Sheet

| Concept | Syntax |
|---------|--------|
| Script argument 1 | `$1` |
| Last command exit code | `$?` (0 = success) |
| File exists? | `[ -f filename ]` |
| Directory exists? | `[ -d dirname ]` |
| Read user input | `read varname` |
| Arithmetic | `$(( 5 + 3 ))` |
| Remove suffix | `${var%.txt}` |
| Hide command output | `> /dev/null 2>&1` |

| Operator | Meaning | Type |
|----------|---------|------|
| `=`      | Equal | String |
| `!=`     | Not equal | String |
| `-eq`    | Equal | Number |
| `-ne`    | Not equal | Number |
| `-gt`    | Greater than | Number |
| `-lt`    | Less than | Number |
| `-ge`    | Greater or equal | Number |
| `-le`    | Less or equal | Number |
