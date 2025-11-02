# Python-Debugging-With-PDB
Deep dive into Python’s command-line debugging with pdb — covering setup, commands, workflows, and performance comparisons with IDEs.


# 🐍 Python Debugging with `pdb` (Command Line)

## 📘 Overview
`pdb` (Python Debugger) is a built-in Python module that allows you to debug scripts directly through the command line — without requiring any GUI-based IDE such as PyCharm, VS Code, or Spyder.  

It helps inspect code execution line-by-line, evaluate variables, and trace program flow in real time.  

This guide covers:
- Running scripts with `pdb`
- Common commands
- Debugging workflow in Windows and Linux
- Pros & Cons
- Comparison with GUI-based debugging

---

## ⚙️ 1. Setting Up
No installation is required — `pdb` is included with Python by default.

### ✅ Check Python Installation
```bash
python --version
# or
python3 --version
```

## 🖥️ 2. Running pdb in Windows or Linux
Option 1: Run with the -m pdb flag
python -m pdb your_script.py


This starts the script in interactive debug mode from the very first line.


## 💡 3. Common pdb Commands

| Command           | Description                                                 |
| ----------------- | ----------------------------------------------------------- |
| `l`               | List 11 lines around the current line (shows where you are) |
| `l 1,50`          | List specific lines (from line 1 to 50)                     |
| `n`               | Execute the next line (step over)                           |
| `s`               | Step into a function call                                   |
| `c`               | Continue until next breakpoint                              |
| `b`               | Show all breakpoints                                        |
| `b 25`            | Set breakpoint at line 25                                   |
| `b function_name` | Set breakpoint at the start of a function                   |
| `cl`              | Clear all breakpoints                                       |
| `cl 25`           | Clear breakpoint at line 25                                 |
| `p variable`      | Print value of a variable                                   |
| `pp variable`     | Pretty-print variable (useful for dicts, lists, JSONs)      |
| `h`               | Show help for commands                                      |
| `q`               | Quit debugger                                               |
| `!command`        | Execute any Python command                                  |
| `where` / `w`     | Show current stack trace                                    |
| `whatis`          | Show the type of a variable                                 |


## 4. Using pdb on Windows CMD
- Open Command Prompt
- Navigate to the script directory using:   cd path\to\your\project
- Run the script with:  python -m pdb script.py

## 🐧 5. Using pdb on Linux Terminal
Steps are the same:
cd /path/to/project
python3 -m pdb script.py


## 🧩 6. Debugging Tips

Use pp variable for nested structures (e.g., dicts, lists)

Use l 1,100 to view more lines of code

Use !print(variable) to execute inline Python commands

Type where to check your current position in the call stack


## ⚖️ 7. Comparison: pdb vs GUI Debuggers (e.g., PyCharm, VSCode)

| Feature          | `pdb` (Command Line)                      | GUI Debugger (PyCharm, VSCode)         |
| ---------------- | ----------------------------------------- | -------------------------------------- |
| Setup            | No setup required                         | Requires IDE installation              |
| Environment      | Works on headless servers, remote systems | Requires graphical interface           |
| Performance      | Lightweight                               | Slightly slower due to overhead        |
| Ease of Use      | Text-based, steeper learning curve        | Visual, intuitive breakpoints          |
| Visualization    | No variable visualization                 | Graphical variable watch, stack viewer |
| Automation       | Easily scriptable                         | Limited scripting support              |
| Remote Debugging | Excellent (SSH supported)                 | Needs remote interpreter setup         |
| Cross-Platform   | Windows/Linux/macOS                       | Yes, but requires GUI                  |
| Learning Curve   | Moderate to High                          | Low                                    |



## ✅ 8. Pros and Cons
👍 Pros

No installation or GUI needed

Works on headless (no-GUI) systems

Fast and lightweight

Fully scriptable for automation

Built-in to Python (no dependencies)

Perfect for production or SSH debugging

👎 Cons

No visual variable inspection

Harder for beginners

Tedious for large, complex projects

Limited breakpoint management (compared to IDEs)



## 🧩 9. Summary

| Topic          | Description                                      |
| -------------- | ------------------------------------------------ |
| Tool           | `pdb` (Python Debugger)                          |
| Usage          | Command-line debugging (Windows/Linux)           |
| Start Debugger | `python -m pdb script.py` or `pdb.set_trace()`   |
| Key Commands   | `n`, `s`, `c`, `b`, `p`, `pp`, `q`               |
| Ideal For      | Remote systems, quick debugging, servers         |
| Not Ideal For  | Visual inspection, complex UIs                   |
| Alternatives   | PyCharm, VS Code, ipdb, pudb, remote-debug tools |
