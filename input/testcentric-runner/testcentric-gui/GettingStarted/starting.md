Title: Starting the GUI
Description: Starting the TestCentric GUI.
Order: 2
---
How you start the GUI depends on how you installed it.

## Chocolatey Install

Did you install the chocolatey package? Chocolatey will have installed a small stub program to run the GUI. In that case just type

```cmd
testcentric
```

## NuGet Install

If you added the install directory to the path, just type

```cmd
testcentric
```

Otherwise, use the path to which the GUI was installed:

```cmd
<path to the install directory>\testcentric.exe (*)
```

(*) Of course, you would use a forward slash on Linux.
