Title: Engine API
Order: 3
Description: Describes the API used by runners to access the engine.
---
<div class="notice">
<b>NOTE:</b> As of the 2.0.0-beta3 release, the TestCentric Engine is entirely separate from the NUnit engine. Earlier releases made use of the NUnit engine API.
</div>

The engine exposes an API designed to be used by test runners, which is only updated in a backwards-compatible way wherever possible. In order to ensure future compatibility, runners should interact with the engine strictly through the API. The engine also hosts various extension points, to allow further customization.

The API is published on __nuget.org__ in package __TestCentric.Engine.Api__.
