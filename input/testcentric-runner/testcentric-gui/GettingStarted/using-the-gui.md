Title: Using the GUI
Description: How to start the GUI, load a set of tests amd execute them,
Order: 2
---
# Starting the GUI

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

# Loading Tests

Normally, when you start the GUI, the most recently used test file will be loaded.

If this is the first time you have used the GUI or if you want to load a different file, use the `File | Open` menu item, select a test assembly and open it. If you want to re-open a file that has been used before, you may use the `File | Recent Files` menu item.

You may also select the file to open from the command-line, by putting it's path after the name of the program when you execute it.

When a test assembly has been loaded, the tests it contains are shown in the tree display.

## Changing How Tests are Displayed

The `Display Format` button lets you choose how tests are displayed. There are three primary choices:

1. The `NUnit Tree` display uses the same layout as the NUnit V2 GUI. Tests are displayed within each test assembly as a tree, which matches the namespace organization of the assembly.

2. The `Fixture List` display shows a list of fixtures. You may choose to group them by Assembly, Category, Outcome or Duration.

3. The `Test List` display shows a list of individual test cases. You may group them by Assembly, Fixture, Category, Outcome or duration.

# Running Tests

## Using the Run All Button

The simplest way to run tests is to click on the `Run All` button in the toolbar. All your tests will be run.

## Using the Run Selected Button

First, select the test or tests you want to run in the tree display and then click the `Run Selected` button in the toolbar.

Tests may be selected in two main ways, depending on whether you have enabled `Show Checkboxes` in the tree.

1. If you right click in the tree display, the context menu allows you to enable the display of checkboxes. When checkboxes are enabled, you may use them to select a single test or even
multiple tests. All the tests under each checked item will be executed.

2. When checkboxes are not displayed, `Run Selected` will execute the highlighted test. All the tests under the highlighted tree node are run. Note that you may also use this technique when checkboxes are turned on, but only if no boxes are currently checked.

## Using the Context Menu

You may run a test - and any tests under it - by right-clicking on the node in the tree display
and selecting `Run` in the menu that appears.

## Repeating the Last Run

Click on the `Rerun` toolbar button to repeat the last test run.

## Running Only Failed Tests

Click on the `Run Failed` button in the toolbar to rerun all tests currently shown as having failed.

# Stopping a Test Run

## Normal Stop

Once a test run begins, the Stop button is enabled. Clicking it initiates a normal stop. We often call this a "cooperative stop" because it requires cooperation from the test framework.

When a Stop is initiated, a command is sent to the framework. The intent is that it should allow all executing tests and all teardowns to complete. No further tests should be started. This usually terminates the run quickly, unless there is a problem like an infinite loop in the test code.

## Forced Stop

As soon as the Stop is initiated, the Stop button text changes to "Kill." The user is able to observe the completion of each test in the GUI and may decide that one of the tests is hung and needs to be stopped forcibly. Clicking "Kill" initiates that process. The framework is expected to terminate all threads, which are running tests and return.

## Last Resort

Some frameworks may not support Forced Stop or it may not work due to a bug. After waiting a period of time (currently 5 seconds) for the run to terminate, the GUI takes the extreme action of unloading all test AppDomains and Processes.
