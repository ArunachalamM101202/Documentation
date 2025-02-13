# Setting Up a Python Virtual Environment on macOS

A Python **virtual environment (venv)** is an isolated environment where you can install packages and dependencies without affecting the system-wide Python installation.

This guide covers the steps to set up and use a virtual environment on macOS.

---

## Quick Virtual Environment Commands (macOS)

| Command                        | Description                                |
|--------------------------------|--------------------------------------------|
| `python3 --version`            | Check installed Python version            |
| `python3 -m venv .venv`        | Create a virtual environment              |
| `source .venv/bin/activate`    | Activate the virtual environment          |
| `which python`                 | Check the active Python interpreter       |
| `pip install package-name`     | Install a package inside the environment  |
| `deactivate`                   | Exit the virtual environment              |
| `rm -rf .venv`                 | Remove the virtual environment            |


## 1. Check Python Installation

Ensure Python is installed on your system:

```bash
python3 --version
```

If Python is not installed, install it via Homebrew:
```
brew install python3
```

## 2. Create a Project Folder and Virtual Environment

Create a new folder in your preferred location.

Drag the folder to VS Code icon to open the folder in VS Code

Use the Command **Control+Shift+`** or Click **Terminal->New Terminal** in the Menu Bar to access the terminal

Run the following command to create your virtual environment. Replace __your_environment_name__ to your preferred environment name

```
python3 -m venv your_environment_name
```
This will create a your_environment_name folder in your project directory containing an isolated Python environment.

## 3. Activate the Virtual Environment

To activate the virtual environment, run:

```
source your_environment_name/bin/activate
```

Once activated, your terminal prompt will change to indicate that you are inside the virtual environment.

## 4. Install Packages Inside the Virtual Environment

To install a package, use pip:
```
pip install matplotlib
```

All installed packages will now reside inside .venv and will not affect your system-wide Python installation. To check if **matplotlib** got installed, run the following command to find all the installed packages:
```
pip list
```

## 5. Deactivate the Virtual Environment

To exit the virtual environment after completion and return to the system-wide Python installation, run:
```
deactivate
```