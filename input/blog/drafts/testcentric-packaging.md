Title: TestCentric Packaging
Published: 12/27/2023
Tags: [TestCentric]
Author: Charlie Poole
---
I just released version 1.1.0 of **TestCentric.InternalTrace**, which may raise questions in some folks' minds. Questions like "What is this package for?" or "Do I need to install it in order to use the GUI?" or "Why do you have so many packages anyway?"

In this post, I'll talk about why **TestCentric** is split into multiple packages. I'll try to explain the purpose of each package, what we use it for and how it _might_ be used outside of **TestCentric**.

But first, I'd like to clarify one thing. I started work on **TestCentric** to try out some ideas about software development and to see where they take me. One of the things I want to try out is breaking a large application into multiple packages. I'd like to examine the pros, cons and limits of this technique and I won't know the limits until I've gone too far and have to pull back!

So I'm not _advocating_ an approach of extreme modulization, I'm _experimenting_ with it. As a side effect, I hope to create something useful.

Because this is an experiment, the number of packages involved varies over time. Currently, there are a total of nineteen packages related to the **TestCentric GUI**. I'll list them with some brief information about each one.

### TestCentric.GuiRunner

**Purpose:** Contains the the GUI runner itself but also pulls in all the packages needed to run it as well as agents for .NET 4.6.2, 6.0, 7.0 and 8.0.

**Used by:** Anyone wanting to use the **TestCentric** GUI to execute tests.

**History:** Version 1 of the GUI was a re-implementation of the old NUnit V2 GUI. Version 2 is currently in beta.

### TestCentric.Engine

**Purpose:** The engine actually does the work of loading and executing tests. It is intended for use by client runners, including third-party. For example, we have plans for a console runner, which will make use of the engine.

**Used By:** Test runners like the GUI, our coming console runner and any third-party runners.

**History:** The notion of a TestEngine separate from the runner itself comes from NUnit3. TestCentric is trying to take this a step further.

### TestCentric.Engine.Api

**Purpose:** The API for the engine is provided as a separate package because many clients only need the API. In fact, even runners, which necessarily load the engine, should limit themselves to working through the API.

**Used By:** Client runners, which normally only call the engine through the API, as well as extensions, which implement one or more of its interfaces.

**History:**

### TestCentric.Engine.Core

**Purpose:** Common code used by both the runner and agents.

**Used By:** 

**History:** Engine Core was developed as a part of the NUnit Test Engine. As of beta4, its size has been reduced and it will be eliminated for beta5.

### TestCentric.Agent.Core

**Purpose:** Common code used by all our agents.

**Used By:** Anyone who wants to create an agent similar to those we provide. Its use is optional but will probably simplify implementation.

**History:** Agent Core is a new module developed to keep code for agents separate from the engine itself.

### TestCentric.Extensibility

**Purpose:** This package incorporates the extensibility mechanism used by **TestCentric**. It is used by the **ExtensionService** in the engine itself but is also available for use by other runners, agents and frameworks. That's why it no longer has "Engine" in it's NuGet id. We believe it is suitable for general use but it has not yet been tested in another application as far as we know.

**Used By:**

**History:**

### TestCentric.Extensibility.Api

**Purpose:** The extensibility API is a separate package since it is needed by extensions to **TestCentric**. Extensions don't require the full extensibility package unless they are themselves extensible. 

**Used By:**

**History:**

### TestCentric.Metadata

**Purpose:** 

**Used By:**

**History:** When the TestCentric GUI project was created in 2018, it used `Mono.Cecil` to examine assemblies, just as NUnit did. Use of `Mono.Cecil`, however, came to present a number of problems for both projects. One was that the library was larger than we needed, containing a great deal of unused functionality. Another was that there seemed to be a risk in using it to examine assemblies, which themselves depended on `Mono.Cecil`.

Those two problems were relatively small. More important was the fact that `Mono.Cecil` was moving forward, dropping support for older platforms. This presented a problem for a test framework committed to continued support for tests using those platforms. While alternative solutions were possible, we eventually settled on building a subset of `Mono.Cecil` and modifying the code as needed so that a single build could be used by all our agents, including those which ran tests on legacy platforms.

Initially, this subset was incorporated in the TestCentric engine itself, which was separated from the GUI as a project in 2020. In the same year, we made `TestCentric.Metadata` a separate project and package and it began to be used by NUnit as well as TestCentric.

### TestCentric.InternalTrace

**Purpose:** 

**Used By:**

**History:**

### TestCentric.Cake.Recipe

**Purpose:** 

**Used By:**

**History:**

### Agents
