# Bash Loops - For & While Examples

## For Loop Examples

### Create 5 folders
```bash
for i in {1..5}; do
    mkdir "folder_$i"
done
# Result: folder_1 folder_2 folder_3 folder_4 folder_5
```

### Rename all .txt files to .bak
```bash
for file in *.txt; do
    mv "$file" "${file%.txt}.bak"
done
```

### Ping multiple servers
```bash
for server in google.com github.com amazon.com; do
    ping -c 1 $server
done
```

### Create 10 users
```bash
for user in {1..10}; do
    useradd "student_$user"
    echo "Created student_$user"
done
```

### Loop through lines in a file
```bash
for line in $(cat servers.txt); do
    echo "Connecting to $line"
    ssh $line uptime
done
```

---

## While Loop Examples

### Count from 1 to 5
```bash
count=1
while [ $count -le 5 ]; do
    echo "Number: $count"
    ((count++))
done
```

### Wait for a file to exist
```bash
while [ ! -f /tmp/ready.txt ]; do
    echo "Waiting for file..."
    sleep 2
done
echo "File found!"
```

### Read a file line by line
```bash
while read line; do
    echo "Line: $line"
done < myfile.txt
```

### Simple menu (keep asking until user quits)
```bash
while true; do
    echo "1) List files  2) Show date  3) Exit"
    read choice
    if [ "$choice" = "1" ]; then
        ls
    elif [ "$choice" = "2" ]; then
        date
    elif [ "$choice" = "3" ]; then
        echo "Bye!"
        break
    fi
done
```

### Retry a command until it succeeds
```bash
while ! curl -s http://localhost:8080 > /dev/null; do
    echo "Service not ready, retrying..."
    sleep 3
done
echo "Service is up!"
```

---

## Quick Summary

| | For | While |
|---|---|---|
| **Use when** | You have a list or range | You have a condition to check |
| **Stops** | After the list ends | When condition becomes false |
| **Think** | "for each X, do Y" | "keep doing Y until Z" |
