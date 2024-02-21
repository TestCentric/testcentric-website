Title: Contributing
Description: Contributing to TestCentric
Order: 3
---
# How to contribute

So you're thinking about contributing to TestCentric? Great! Maintaining and enhancing the TestCentric GUI is a big job, so **the community's help is really appreciated.**

Helping out isn't just writing code, it also includes submitting issues, helping confirm issues, writing documentation, running tests and answering questions from other users. 

## Submitting Issues

Requests for new features and bug reports keep the project moving forward.

### Where to submit an issue

#### TestCentric Runner:

There are multiple packages, each with it's own issue tracker. When in doubt, use the [GUI tracker](https://github.com/TestCentric/testcentric-gui/issues) for issues of appearance and the [TestEngine tracker](https://github.com/TestCentric/testcentric-engine/issues) for Issues related to loading and running of tests. An engine-like issue, which only occurs when a specific runtime is targeted, may actually relate to the agent used: [.NET 4.6.2](https://github.com/TestCentric/net462-pluggable-agent/issues) / [.NET 8.0](https://github.com/TestCentric/net80-pluggable-agent/issues) / [.NET 7.0](https://github.com/TestCentric/net70-pluggable-agent/issues) / [.NET 6.0](https://github.com/TestCentric/net60-pluggable-agent/issues), for example.

Once again, when in doubt use the issue tracker for the software where you encountered the issue but **submit your issue**! After investigating the problem, we will move your issue to a different tracker if necessary.

#### TC-Lite Framework:
All issues should be submitted [here](https://github.com/TestCentric/tc-lite/issues).

### Before you submit an issue

- Ensure you are running the latest version of the software, which may be a pre-release. Note that we are no longer fixing problems arising in version 1 of the TestCentric GUI.
- Search the issue list to make sure your issue hasn't already been reported. Be sure to look at closed issues as well as open ones, in case there is an unreleased fix available in our repository.

### Submitting a good issue

- Give the issue a short, clear title that describes the bug or feature request.
- Include the versions of the software you are using.
- Include steps to reproduce the issue
- If possible, include a short code example that reproduces the issue.
- Use [markdown formatting](https://guides.github.com/features/mastering-markdown/) as appropriate to make the issue and code more readable.

## Confirming Bugs

Before we work on a bug report, we must confirm and be able to reproduce it. Confirming bugs takes up a great deal of the team's time, so making that job easier is very helpful.

Issues that need confirmation will have the **Needs Confirmation** label. As a user, you can help us by;

- Adding steps to reproduce the bug, if not provided in the original report.
- Describing conditions in which the bug occurs or does not occur.
- Creating failing unit tests to demonstrate the bug.
- Testing issues created by others and adding a comment as feedback.

## Documentation

Great documentation is essential for any open source project and TestCentric is no exception. [Our documentation](https://test-centric.org) may sometimes lag behind the features that have been implemented or may benefit from better examples.

A great place to start is by going through the Release Notes on GitHub and ensuring that the documentation for new features is up to date.

## Fixing Bugs and Adding Features

We love pull requests! We prefer that new contributors start with small issues and let us know before contributing code so as to prevent duplication of work. To help new contributors get their feet wet, we have marked a number of issues with the `Easy Fix` label. These are great places to start.

It is also a good idea to add a comment to an issue that you are working on to let everyone know. We'll assign the issue to you so that it shows up under your name on GitHub. If you stop working on it, also please let us know.

Please read through the developer section of the documentation before contributing to understand our coding standards and contribution guidelines.

Once you are ready to have your work reviewed, create a Pull Request (PR) on GitHub. A team member will review it and may make suggestions for changes. Only team members (committers) are able to merge your work into TestCentric.

## License

Our software is under the [MIT license](https://opensource.org/license/MIT). By contributing to TestCentric, you assert that:

- The contribution is your own original work.
- You have the right to assign the copyright for the work.