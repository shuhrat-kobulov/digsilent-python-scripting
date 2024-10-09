# Python Scripting in DIgSILENT

Welcome to the Python scripting guide for DIgSILENT. This documentation will teach you how to leverage Python for automating tasks in DIgSILENT PowerFactory.

## Table of Contents

1. [Introduction](#introduction)
2. [Getting Started](#getting-started)
3. [Basic Scripting](#basic-scripting)
4. [Advanced Scripting](#advanced-scripting)
5. [Troubleshooting](#troubleshooting)

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

1. **Check Python Version**: DIgSILENT PowerFactory supports Python 2.7 and 3.x. Ensure that Python is installed and properly set up with PowerFactory.
2. **Set Up Your Environment**:
   - In PowerFactory, go to _Options > Settings > Python_ and configure your Python environment.

---

## Basic Scripting

### Example: Running a Simple Load Flow

Here is a basic script to run a load flow study in DIgSILENT:

```python
import powerfactory as pf

app = pf.GetApplication()
app.ClearOutputWindow()

# Load the network model
network = app.GetCalcRelevantObjects('*.ElmNet')[0]

# Perform load flow analysis
lf = app.GetFromStudyCase('ComLdf')
ierr = lf.Execute()

if ierr == 0:
    app.PrintPlain("Load flow executed successfully!")
else:
    app.PrintError("Error executing load flow.")
```
