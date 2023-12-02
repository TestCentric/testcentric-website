Title: "TestCentric .NET 8.0 Pluggable Agent"
Published: 2/24/2023
Tags: [TestCentric, Pluggable Agent, .NET 8.0]
---
Now that the .NET 8.0 preview is out, many folks will want to experiment with
it and possibly run tests under the TestCentric GUI. A newly released extension,
the .NET 8.0 Pluggable Agent, makes this possible.

Briefly, it's a special type of extension to the TestCentric Engine, which
provides a new type of agent to run tests. In this case, an agent capable
of running tests under .NET 8.0.

Like the NUnit engine on which it is based, the TestCentric Engine is
extensible. It supports the standard NUnit extensions defined by the NUnit API
but it also provides additional extension points. A pluggable agent extension
makes use of one of these, extending the engine to provide a new kind of agent.
In this case, an agent which runs tests under .NET 8.0 is provided.

The benefit of having pluggable agents is that new agents can be added
to an existing installation of the GUI, without waiting for a new release.
In this case, assuming you are running the latest alpha release of the gui,
version 2.0.0-alpha7, you can simply install the extension and TestCentric
will be able to run .NET 8.0 tests.

The initial preview of the .NET 8.0 pluggable agent is available on the
TestCentric myget feed. Use the latest `dev` build you can find there.
The package `nunit-extension-net80-pluggable-agent` is for use with Chocolatey.
For other types of installations, use `NUnit.Extension.Net80PluggableAgent`;

Make sure that you install the extension using the same package type you
used to install the GUI. If you installed the GUI using chocolatey,
install the extension in the same way. If you used a NuGet package for
the GUI, use NuGet for the extension as well.
