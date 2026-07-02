
---

# Phase 1 (Week 1)

## Python Foundations for DevOps

### 📅 Day 1 - Python Environment & Project Setup

**Objectives**

* Install Python (verify version)
* Understand Python versions
* Create virtual environments
* Install packages using pip

Topics

* python --version
* pip
* venv
* requirements.txt

Commands

```bash
python -m venv venv
```

```bash
source venv/bin/activate
```

Windows

```powershell
venv\Scripts\activate
```

Install

```bash
pip install requests
```

Save packages

```bash
pip freeze > requirements.txt
```

Install again

```bash
pip install -r requirements.txt
```

Mini Project

> Create a project folder called

```
server-monitor
```

Inside

```
server-monitor/
    venv/
    requirements.txt
    app.py
```

---

## 📅 Day 2 - File Handling

Why?

DevOps engineers read

* configuration
* logs
* deployment files

Topics

Reading files

Writing files

Appending

Working with folders

Functions

```
open()

with open()

Pathlib
```

Mini Project

Read

```
servers.txt
```

```
server1
server2
server3
```

Print

```
Checking server1...
Checking server2...
Checking server3...
```

---

## 📅 Day 3 - JSON

Every cloud service loves JSON.

AWS

Docker

Terraform output

Kubernetes APIs

all use JSON.

Topics

```
json.loads()

json.dumps()

json.load()

json.dump()
```

Mini Project

Create

```
servers.json
```

```
[
 {
  "name":"web1",
  "ip":"10.0.0.1"
 },
 {
  "name":"db1",
  "ip":"10.0.0.2"
 }
]
```

Python should print

```
web1
10.0.0.1

db1
10.0.0.2
```

---

## 📅 Day 4 - YAML

Probably the most important file format in DevOps.

You'll use YAML almost every day.

Examples

* Kubernetes
* GitHub Actions
* Docker Compose
* Ansible
* Azure Pipelines

Topics

```
PyYAML
```

Install

```
pip install pyyaml
```

Mini Project

Read

```
config.yaml
```

```
servers:
 - web
 - db
 - cache
```

Print

```
web
db
cache
```

---

## 📅 Day 5 - os & pathlib

Imagine managing 500 files.

You don't manually click folders.

Python does it.

Topics

```
os

pathlib

mkdir

exists()

rename()

remove()
```

Mini Project

Automatically create

```
logs/

backup/

config/

reports/
```

---

## 📅 Day 6 - Logging

Instead of

```
print()
```

Professional scripts use

```
logging
```

Topics

```
logging.basicConfig()

INFO

WARNING

ERROR
```

Mini Project

Create

```
automation.log
```

Output

```
INFO Started backup

INFO Backup complete

ERROR Unable to connect
```

---

## 📅 Day 7 - Week 1 Challenge

Build

```
Server Inventory Manager
```

Structure

```
inventory/

servers.json

logs/

main.py
```

Features

* Read JSON
* Create log
* Display servers
* Save results

---

# Phase 2 (Week 2)

Now we start writing scripts that feel like real DevOps tools.

---

## 📅 Day 8 - argparse

Instead of editing code

```
python app.py
```

You'll use

```
python app.py --server web1
```

Topics

```
argparse

arguments

options

help
```

Mini Project

```
python app.py --name web1
```

Output

```
Checking web1
```

---

## 📅 Day 9 - requests

DevOps scripts constantly call APIs.

Examples

AWS

GitHub

Jenkins

Docker Hub

Prometheus

Topics

```
GET

POST

status_code

json()
```

Mini Project

Call

```
https://jsonplaceholder.typicode.com/users
```

Print every user's name.

---

## 📅 Day 10 - subprocess

This is where Python becomes a DevOps assistant.

Python can execute

```
docker ps

kubectl get pods

git status

terraform plan
```

Topics

```
subprocess.run()
```

Mini Project

Run

```
ipconfig
```

Windows

or

```
ls
```

Linux

Print the output.

---

## 📅 Day 11 - Regex

Need to find an IP inside a log?

Regex.

Need to extract an error?

Regex.

Topics

```
re.findall()

re.search()
```

Mini Project

Given

```
Server started at 10.0.0.5
```

Extract

```
10.0.0.5
```

---

## 📅 Day 12 - Combining Everything

Build

```
Health Checker
```

Python

↓

Read YAML

↓

Read JSON

↓

Call API

↓

Run command

↓

Save logs

---

## 📅 Day 13 - Final Mini Project

```
Infrastructure Health Reporter
```

Folder

```
health-reporter/

config.yaml

servers.json

logs/

report.txt

main.py
```

Flow

```
Read config

↓

Read server list

↓

Ping server (simulate if needed)

↓

Save logs

↓

Generate report
```

Example report

```
Server Report

web1

Status : Healthy

db1

Status : Healthy

cache1

Status : Offline
```

---

## 📅 Day 14 - Polish & Push to GitHub

Goals

* Clean project structure
* Add README
* Add `.gitignore`
* Create `requirements.txt`
* Use meaningful commit messages
* Push to GitHub

By the end of Day 14, you'll have a portfolio-ready repository that demonstrates practical Python for DevOps.

---

# 🎯 End Goal After 2 Weeks

You should be comfortable writing scripts that can:

* ✅ Read and write configuration files (JSON and YAML)
* ✅ Manage files and directories with `pathlib`
* ✅ Parse command-line arguments with `argparse`
* ✅ Call REST APIs using `requests`
* ✅ Execute system commands with `subprocess`
* ✅ Extract information from text using regular expressions
* ✅ Record execution details with `logging`
* ✅ Organize projects using virtual environments and `requirements.txt`
* ✅ Combine these skills into small automation tools similar to what DevOps engineers build daily

This phase creates a strong bridge between your existing AWS/DevOps knowledge and practical automation. Once you finish it, the next logical step is learning **GitHub API automation, Jenkins API scripting, Docker SDK for Python, and AWS automation with `boto3`**, where Python starts controlling real infrastructure instead of just local files.
