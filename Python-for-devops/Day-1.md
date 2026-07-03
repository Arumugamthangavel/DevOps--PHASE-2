
---

# 📅 Day 1: Python Environment & Project Setup

**Time Required:** 1.5 to 2 hours

**Goal:**
By the end of today you'll understand how Python projects are isolated, how packages are managed, and how every real-world Python project starts.

---

# Step 1: Verify Python Installation

Open **PowerShell** or **Command Prompt**

```powershell
python --version
```

Example

```text
Python 3.13.2
```

Also check pip

```powershell
pip --version
```

Example

```text
pip 25.x
```

---

## Why?

Python is the language.

pip is Python's package manager.

Think of it like

```
Ubuntu
    ↓
apt install nginx
```

Similarly

```
Python
    ↓
pip install requests
```

---

# Step 2: Create Project Folder

Open PowerShell

```powershell
mkdir server-monitor
```

Go inside

```powershell
cd server-monitor
```

Check

```powershell
pwd
```

or

```powershell
cd
```

depending on shell.

---

# Step 3: Create Virtual Environment

Run

```powershell
python -m venv venv
```

Now your folder becomes

```
server-monitor/

    venv/
```

---

## What happened?

Python copied a small isolated environment.

Instead of using system Python

```
Windows Python
```

you now have

```
server-monitor/

    venv/
        Scripts/
        Lib/
        Include/
```

Everything installed later stays here.

---

## Why DevOps Engineers Love Virtual Environments

Imagine

Project A

Needs

```
requests==2.25
```

Project B

Needs

```
requests==2.32
```

Without virtual environments...

💥 One project breaks the other.

Virtual environments isolate dependencies, preventing conflicts.

---

# Step 4: Activate Virtual Environment

Windows

```powershell
venv\Scripts\activate
```

You should now see

```
(venv)

PS C:\server-monitor>
```

That

```
(venv)
```

means Python is using the isolated environment.

---

# Step 5: Check Python Again

Run

```powershell
python --version
```

Still

```
Python 3.x.x
```

But now it's coming from

```
server-monitor/venv/
```

instead of the global installation.

---

# Step 6: Install Your First Package

```powershell
pip install requests
```

You'll see something like

```
Collecting requests
Installing...
Successfully installed requests
```

---

## What is Requests?

One of the most used Python libraries.

Later you'll use it for

* Calling REST APIs
* AWS APIs
* Jenkins APIs
* GitHub APIs
* Slack Webhooks
* Kubernetes APIs

Almost every DevOps automation uses it.

---

# Step 7: Verify Installation

```powershell
pip list
```

Example

```
Package

requests
urllib3
certifi
charset-normalizer
idna
```

---

# Step 8: Save Dependencies

```powershell
pip freeze > requirements.txt
```

Open

```
requirements.txt
```

You'll see something like

```
certifi==...
charset-normalizer==...
idna==...
requests==...
urllib3==...
```

---

## Why?

Imagine another developer clones your project.

Instead of saying

> Install everything manually...

they simply run

```powershell
pip install -r requirements.txt
```

Everything installs automatically.

This is exactly how real DevOps projects are shared.

---

# Step 9: Create app.py

Inside

```
server-monitor
```

Create

```
app.py
```

Add

```python
print("Server Monitor Started")
```

Run

```powershell
python app.py
```

Output

```
Server Monitor Started
```

---

# Final Folder Structure

```
server-monitor/
│
├── venv/
│
├── requirements.txt
│
└── app.py
```

---

# Real DevOps Example

Imagine you're writing a script to monitor EC2 instances.

Your project might eventually look like this:

```
server-monitor/

│
├── venv/
│
├── app.py
│
├── aws.py
│
├── monitor.py
│
├── config.py
│
├── requirements.txt
│
└── logs/
```

The foundation you're building today scales directly into automation scripts for AWS, Kubernetes, Jenkins, Docker, and more.

---

# Today's Practice Checklist

* ✅ Verify `python --version`
* ✅ Verify `pip --version`
* ✅ Create `server-monitor` folder
* ✅ Create a virtual environment with `python -m venv venv`
* ✅ Activate the virtual environment
* ✅ Install the `requests` package
* ✅ Check installed packages with `pip list`
* ✅ Generate `requirements.txt` using `pip freeze > requirements.txt`
* ✅ Create `app.py`
* ✅ Run `python app.py` successfully

If you complete these comfortably, you'll be ready for **Day 2**, where you'll learn file handling and build your first practical automation that reads server configuration from files.
