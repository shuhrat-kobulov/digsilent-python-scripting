# Python Scripting in DIgSILENT

Welcome to the Python scripting for DIgSILENT. This documentation will teach you how to leverage Python for automating tasks in DIgSILENT PowerFactory.

## Table of Contents

1. [Connect to PowerFactory Application](#connect-to-powerfactory-application)

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
