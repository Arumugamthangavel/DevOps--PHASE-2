# Day 2: File Handling for DevOps 
---

## Why File Handling?

Imagine you're managing **200 servers**.

Instead of typing every server name manually...

```
server1
server2
server3
...
server200
```

...you store them in a text file.

Your Python script reads the file and performs operations automatically.

This is everywhere in DevOps:

* Server inventory
* IP addresses
* Configuration files
* Log files
* Deployment scripts
* Backup lists

---

### 1. Reading Files

Suppose we have

**servers.txt**

```text
server1
server2
server3
```

Python

```python
file = open("servers.txt", "r")

content = file.read()

print(content)

file.close()
```

Output

```text
server1
server2
server3
```

---

## What happened?

```
open()
```

opens the file.

```
"r"
```

means

```
Read Mode
```

Then

```
read()
```

reads everything.

Finally

```
close()
```

releases the file.

Think of it like borrowing a library book.

```
Open book

Read

Close book
```

---

## Better Way

Python has a safer method.

```python
with open("servers.txt", "r") as file:
    content = file.read()

print(content)
```

No need

```
file.close()
```

Python closes it automatically.

This is the preferred DevOps style.

---

## Reading Line by Line

Instead of reading the whole file

```python
with open("servers.txt") as file:
    for line in file:
        print(line)
```

Output

```
server1

server2

server3
```

Notice the extra blank lines.

That's because every line ends with

```
\n
```

Remove it using

```python
with open("servers.txt") as file:
    for line in file:
        print(line.strip())
```

Output

```
server1
server2
server3
```

---

### 2. Writing Files

Create a new file.

```python
with open("status.txt", "w") as file:
    file.write("Deployment Successful")
```

Output

Creates

```
status.txt
```

Containing

```
Deployment Successful
```

---

## Important

Mode

```
w
```

means

```
Erase old file

Write new content
```

Example

Before

```
Hello
```

After

```python
with open("status.txt","w") as file:
    file.write("Done")
```

Now

```
Done
```

Old content disappeared.

---

### 3. Append

Suppose

```
log.txt
```

contains

```
Server Started
```

Now

```python
with open("log.txt","a") as file:
    file.write("\nDeployment Finished")
```

Output

```
Server Started
Deployment Finished
```

Append means

```
Keep existing content

Add new content
```

Perfect for

* Logs
* Reports
* Monitoring

---

## File Modes

| Mode | Meaning                           |
| ---- | --------------------------------- |
| r    | Read                              |
| w    | Write (overwrite)                 |
| a    | Append                            |
| x    | Create only if file doesn't exist |

---

### 4. Working with Folders

Import

```python
import os
```

Current directory

```python
print(os.getcwd())
```

Create folder

```python
os.mkdir("logs")
```

List files

```python
print(os.listdir())
```

---

## Better Way: Pathlib ⭐

Modern Python uses

```python
from pathlib import Path
```

Current folder

```python
current = Path.cwd()

print(current)
```

Create folder

```python
Path("logs").mkdir(exist_ok=True)
```

Check file exists

```python
file = Path("servers.txt")

print(file.exists())
```

Output

```
True
```

---

## Why Pathlib?

Old way

```python
"C:\\Users\\Arumugam\\Desktop\\DevOps\\servers.txt"
```

Linux

```
/home/arumugam/servers.txt
```

Different operating systems use different path separators.

`pathlib` hides those differences and lets you work with paths in a clean, cross-platform way.

---

## Mini Project (Very Common DevOps Task)

Create

```
servers.txt
```

```text
server1
server2
server3
```

Python

```python
from pathlib import Path

server_file = Path("servers.txt")

with server_file.open("r") as file:
    for server in file:
        print(f"Checking {server.strip()}...")
```

Output

```text
Checking server1...
Checking server2...
Checking server3...
```

---

## Small Upgrade

Save the results into a log file.

```python
from pathlib import Path

server_file = Path("servers.txt")
log_file = Path("check.log")

with server_file.open("r") as servers, log_file.open("w") as log:
    for server in servers:
        message = f"Checking {server.strip()}..."
        print(message)
        log.write(message + "\n")
```

Console Output

```text
Checking server1...
Checking server2...
Checking server3...
```

`check.log`

```text
Checking server1...
Checking server2...
Checking server3...
```

This pattern is very close to real DevOps scripts that process server inventories and generate logs.

---

## Today's Practice Tasks

1. Create `servers.txt` with 5 server names and print them one by one.
2. Create `status.txt` and write `"Deployment Started"`.
3. Append `"Deployment Completed"` to the same file.
4. Use `pathlib` to check whether `servers.txt` exists.
5. Modify the mini project to number each server:

```text
1. Checking server1...
2. Checking server2...
3. Checking server3...
```

---

## Key Takeaways

| Concept                  | Purpose in DevOps                                |
| ------------------------ | ------------------------------------------------ |
| `open()`                 | Open a file                                      |
| `with open()`            | Safely open and automatically close a file       |
| `.read()`                | Read the entire file                             |
| `for line in file`       | Process files line by line (great for logs)      |
| `.write()`               | Create or overwrite a file                       |
| `.append()` (`"a"` mode) | Add new content without deleting existing data   |
| `Path.exists()`          | Check if a file or directory exists              |
| `Path.mkdir()`           | Create directories for logs, backups, or reports |

