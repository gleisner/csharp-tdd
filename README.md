# Test-Driven Development & Standards with C&#35;

## Test Frameworks and Runners
 - `NUnit`
 - `MSTest`
 
## Stubbing & Mocking
 - stub w/ constructor dependency injection
 - [`Moq`](https://github.com/moq/moq4)
    * [Moq vs other C# mocking frameworks](http://blogs.clariusconsulting.net/kzu/why-do-we-need-yet-another-net-mocking-framework/)
    * [No record/replay/verify](http://blogs.clariusconsulting.net/kzu/whats-wrong-with-the-recordreplyverify-model-for-mocking-frameworks/)
 - [`NMock`](http://nmock.sourceforge.net/)
 
## Coverage
 - Visual Studio: `Tests > Analyze Code Coverage > All Tests`
 - [`OpenCoverage`](https://github.com/OpenCover/opencover)
  * generated HTML reports with [ReportGenerator](https://github.com/danielpalme/ReportGenerator)
 
## Fake Test Data
 
 - [`Nbuilder`](https://github.com/nbuilder/nbuilder)
 - [`Bogus`](https://github.com/bchavez/Bogus)
 
## Code Analysis & Linting
 - SonarLint
 - StyleCop
 - [`Gendarme`](http://www.mono-project.com/docs/tools+libraries/tools/gendarme/)
 - Automatic formatting w/ Resharper
