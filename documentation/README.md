# Python Scripting in DIgSILENT

Welcome to the Python scripting for DIgSILENT. This documentation will teach you how to leverage Python for automating tasks in DIgSILENT PowerFactory.

## Table of Contents

1. [Connect to PowerFactory Application](#connect-to-powerfactory-application)
2. [Activate Project](#activate-project)

---

## Connect to PowerFactory Application

Before you can perform any operations within DIgSILENT PowerFactory using Python, you need to establish a connection to the PowerFactory application. This connection allows your Python script to interact with PowerFactory's objects and functionalities.

### Steps to Connect:

1. **Import the PowerFactory Module**: PowerFactory provides a Python module that facilitates interaction with its environment. Begin by importing this module in your script.
   ```python
    import sys
    sys.path.append(r"C:\\Program Files\\DIgSILENT\\PowerFactory 2022 SP2\\Python\\3.8")
    import powerfactory
   ```
2. **Initialize the PowerFactory Application**: Use the GetApplication() method to initialize and obtain a reference to the PowerFactory application instance.

   ```python
    app = powerfactory.GetApplication()

    if not app:
        raise Exception("Could not connect to PowerFactory application.")
    else:
        print("Connected to PowerFactory successfully.")
   ```

### Example:

Here's a complete example that connects to the PowerFactory application and verifies the connection:

```python
import sys
sys.path.append(r"C:\\Program Files\\DIgSILENT\\PowerFactory 2022 SP2\\Python\\3.8")
import powerfactory

app = powerfactory.GetApplication()

if not app:
    raise Exception("Could not connect to PowerFactory application.")
else:
    print("Connected to PowerFactory successfully.")
```

## Activate Project

The ActivateProject() method in the Python API is used to activate a specific project within PowerFactory. Once activated, the project becomes the context for all subsequent actions like running simulations, managing scenarios, or executing scripts.

```python
app.ActivateProject(project_name)
```

### Parameters:

- `project_name`: Name of the project to be activated.

### Returns:

- The method returns the activated project object. If the project is not found or cannot be activated, it returns `None`.

### Example:

```python
import sys
sys.path.append(r"C:\\Program Files\\DIgSILENT\\PowerFactory 2022 SP2\\Python\\3.8")
import powerfactory

app = powerfactory.GetApplication()

if not app:
    raise Exception("Could not connect to PowerFactory application.")

project_name = "Your_Project_Name"  # Replace with the actual name of your project

# Activate the project
project = app.ActivateProject(project_name)

# Check if the project was activated successfully
if project is None:
    raise Exception(f"Project '{project_name}' could not be activated.")
else:
    print(f"Project '{project_name}' activated successfully.")

# Further operations on the activated project go here
...
```
