Title: TestCentric Beta4 Release
Published: 12/2/2023
Tags: [TestCentric]
Author: Charlie Poole
---
In  an [earlier post](./testcentric-beta2-and-beyond.html), I talked about plans for moving ahead with TestCentric, separating it more completely from its remaining dependencies on NUnit. I predicted that the beta3 release would probably not have any new features, being concerned primarily with internal changes in how the TestCentric runner and engine were structured. That turned out to be true.

The beta4 release built on beta3 and incorporated one new and fairly important feature. To coincide with Microsoft's release of .NET 8.0 last week, the Gui now bundles an updated agent for .NET 8.0 tests along with the .NET 4.6.2, 6.0 and 7.0 agents, which were already included.

In addition to providing an important new feature for users, the beta4 release serves to illustrate the value of our earlier decision to make all agents separate components. With this release, development work on an agent only requires installation of whatever runtime that agent is intended to support. Work on the engine or the GUI can proceed independently. The engine itself is delivered without any agents and the bundling of particular agents with the GUI is a packaging decision, which can be made on a just-in-time basis.
