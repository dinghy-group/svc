# Bash Practice Tasks for Beginners

---

## Task 1 - If Condition (Equal)

**Write a script that asks the user for a password. If the password is "1234", print "Access granted". Otherwise, print "Access denied".**

<details>
<summary>Solution</summary>

```bash
#!/bin/bash
echo "Enter password:"
read pass
if [ "$pass" = "1234" ]; then
    echo "Access granted"
else
    echo "Access denied"
fi
```

</details>

---

## Task 2 - If Condition (Greater Than)

**Write a script that asks the user for their age. If the age is greater than 18, print "You can enter". Otherwise, print "Too young".**

<details>
<summary>Solution</summary>

```bash
#!/bin/bash
echo "Enter your age:"
read age
if [ "$age" -gt 18 ]; then
    echo "You can enter"
else
    echo "Too young"
fi
```

</details>

---

## Task 3 - If Condition (Equal with numbers)

**Write a script that asks for a number. If the number equals 7, print "Lucky number!". Otherwise, print "Try again".**

<details>
<summary>Solution</summary>

```bash
#!/bin/bash
echo "Pick a number:"
read num
if [ "$num" -eq 7 ]; then
    echo "Lucky number!"
else
    echo "Try again"
fi
```

</details>

---

## Task 4 - For Loop

**Write a script that creates 3 files called file_1.txt, file_2.txt, file_3.txt.**

<details>
<summary>Solution</summary>

```bash
#!/bin/bash
for i in {1..3}; do
    touch "file_$i.txt"
    echo "Created file_$i.txt"
done
```

</details>

---

## Task 5 - For Loop

**Write a script that prints "Hello" to 3 friends: David, Sarah, Dan.**

<details>
<summary>Solution</summary>

```bash
#!/bin/bash
for name in David Sarah Dan; do
    echo "Hello $name!"
done
```

</details>

---

## Task 6 - While Loop

**Write a script that counts from 1 to 5 and prints each number.**

<details>
<summary>Solution</summary>

```bash
#!/bin/bash
count=1
while [ $count -le 5 ]; do
    echo "$count"
    ((count++))
done
```

</details>

---

## Task 7 - While Loop

**Write a script that keeps asking "Say the magic word:" until the user types "please".**

<details>
<summary>Solution</summary>

```bash
#!/bin/bash
word=""
while [ "$word" != "please" ]; do
    echo "Say the magic word:"
    read word
done
echo "Thank you! You are polite!"
```

</details>

---

## Cheat Sheet - Comparison Operators

| Operator | Meaning | Type |
|----------|---------|------|
| `=`      | Equal (strings) | String |
| `!=`     | Not equal (strings) | String |
| `-eq`    | Equal (numbers) | Number |
| `-ne`    | Not equal (numbers) | Number |
| `-gt`    | Greater than | Number |
| `-lt`    | Less than | Number |
| `-ge`    | Greater or equal | Number |
| `-le`    | Less or equal | Number |

### Important Rule
- Use `=` and `!=` for **text** (strings)
- Use `-eq`, `-gt`, `-lt` for **numbers**
