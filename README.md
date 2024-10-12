# Python Scripting in DIgSILENT

Welcome to the Python scripting for DIgSILENT. This documentation will teach you how to leverage Python for automating tasks in DIgSILENT PowerFactory.

## Table of Contents

1. [Introduction](#introduction)
2. [Getting Started](#getting-started)
3. [Basic Scripting](#basic-scripting)
4. [Troubleshooting](#troubleshooting)
5. [Contributing](contributing.md)
6. [Start Learning](documentation/README.md)

---

## Introduction

Python scripting in DIgSILENT allows users to automate repetitive tasks, perform custom calculations, and enhance power system analysis. Whether you're a beginner or an experienced engineer, learning scripting can improve your workflow and reduce manual effort.

### Why Use Python for DIgSILENT?

- Automate load flow simulations
- Perform batch processing of studies
- Customize reports and results
- Create complex scenarios and simulations

---

## Getting Started

Before diving into scripting, make sure you have the following:

- DIgSILENT PowerFactory installed
- Python environment set up
- Basic understanding of Python programming

### Setting Up Python with DIgSILENT

1. Check the Python version used by DIgSILENT PowerFactory. You can find the Python API path in your PowerFactory installation directory, typically located at: `C:\\Program Files\\DIgSILENT\\PowerFactory 2022 SP2\\Python`
2. Install the same Python version on your system. You can download Python from the official website: [Python Downloads](https://www.python.org/downloads/)

## Basic Scripting

### Example: Running a Simple Load Flow

Here is a basic script to run a load flow study in DIgSILENT:

```python
# Import the system module
import sys

# Add the path to the PowerFactory Python module
sys.path.append(r"C:\\Program Files\\DIgSILENT\\PowerFactory 2022 SP2\\Python\\3.8")

# Import the PowerFactory module
import powerfactory as pf

# Initialize the PowerFactory application instance
app = pf.GetApplication()

# Load the first available network model (ElmNet is the class for networks)
network = app.GetCalcRelevantObjects('*.ElmNet')[0]

# Get the load flow command from the current study case
lf = app.GetFromStudyCase('ComLdf')

# Execute the load flow analysis
ierr = lf.Execute()

# Check if the load flow was successful (ierr = 0 means success)
if ierr == 0:
    app.PrintPlain("Load flow executed successfully!")
else:
    app.PrintError("Error executing load flow.")

```

## Troubleshooting

- Error Connecting to DIgSILENT PowerFactory: Ensure that the path in sys.path.append() is correct for your PowerFactory installation. You can find the Python API path typically located at:

```bash
C:\\Program Files\\DIgSILENT\\PowerFactory 2022 SP2\\Python\\3.x
```

- Python Version Mismatch: The Python version installed on your system must match the version required by PowerFactory. For example, if PowerFactory is using Python 3.8, you should have Python 3.8 installed. To check your Python version, run:

```bash
python --version
```

- Script Failing to Execute: Verify that the correct study case is active and that your network model is properly set up.
