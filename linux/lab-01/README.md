# LAB-01: Essential Linux Commands (Hands-on)

## 1. Setup & Navigation

**1. Display the path of current directory**
```bash
pwd
```

**2. Go to the log files folder**
```bash
cd /var/log
```

**3. Go to the home directory**
```bash
cd
```

## 2. File & Directory Creation

**4. Create three folders (a, b, c) under home directory in one command**
```bash
mkdir a b c
```

**5. Display the date & time**
```bash
date
```

**6. Display the date of 2 years ago**
```bash
date -d "2 years ago"
```

## 3. Content Manipulation & Verification

**7. Under ~ folder create a file myfile.txt with content "I am a great devops" with one command**
```bash
echo "I am a great devops" > ~/a/myfile.txt
```

**8. Add second line to myfile.txt with content "and I would like to be an expert on Linux" with one command**
```bash
echo "and I would like to be an expert on Linux" >> ~/a/myfile.txt
```

**9. Check the existence of two lines in file**
```bash
cat ~/a/myfile.txt
```

## 4. Advanced Operations & Cleanup

**10. Copy the 'a' folder with all files into the 'b' folder**
```bash
cp -r a b/
```

**11. Display the list, date and hidden files in b folder**
```bash
ls -la ~/b/a
```

**12. Move 'c' folder to 'd' folder and then create empty file in 'd' folder**
```bash
mv c d && touch d/placeholder.txt
```

**13. Back to the home dir and delete all folders and files (a, b, d) with one command**
```bash
cd ~ && rm -rf a b d
```
