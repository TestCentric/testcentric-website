Description: Lists engine extension points and installed extensions.
Order: 10
---
The Extensions Dialog is displayed using the Tools | Extensions menu item on the main menu. It lists all the available extension points together with the loaded extensions for each one.

<img class="float-right" alt="Extensions Dialog" src="../img/extensionsDialog.png" />

### Extension Points

This section lists all the extension points present in the engine, which may or may not have extenions installed. The list shows the unique `path`, which identifies each extension.

#### Description

The description of the currently selected extension point in the list, indicating
its general purpose.

### Installed Extensions

This section lists all extensions currently installed at the selected extension point in the first list. The name of the extension is usually the full name of the class that implements it, but may be different in certain cases. The status of an extension may be **Enabled** or **Disabled**.

#### Description

If the author of an extension has provided a description, it is shown here when the extension is selected.

#### Properties

If the selected extension defines any properties, their names and values are listed here.

#### Extension Assembly

Shows the path to the loaded extension assembly and its version.
