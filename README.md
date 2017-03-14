# Test-Driven Development with C&#35;


### Getting Started
- Install [Resharper](https://www.jetbrains.com/resharper/download/)
  * optional, but highly recommended
- Find a buddy!

### How
- Pair-programming
  - Frequently switch the driver/navigator roles with ping-ponging: one person writes a test, the other passes it and writes the next test
  - [Benefits of pair-programming](https://pdfs.semanticscholar.org/1d4c/7da6969ad0df86aa1d81274305fddc1e20e0.pdf)
- Structure a unit test
   * Arrange / Given
   * Act / When
   * Assert / Then
- [Inversion of control](https://martinfowler.com/articles/injection.html)
   * Use constructor-based dependency injection with your IoC framework of choice
     - Naturally limits the number of hard dependencies as you see the number of constructor arguments grow
     - Ensures that the class is fully initialized before it's used (unlike setter-based injection)
- Write easily testable code
   * Clean code and testable code go hand in hand
   * [What does untestable code look like?](https://testing.googleblog.com/2008/07/how-to-write-3v1l-untestable-code.html)
   
### Tools

#### Inversion of Control Frameworks

- Autofac
- Unity
- Spring.NET
- Lots more: http://stackoverflow.com/a/227012

#### Test Frameworks
 - `NUnit`
 - `MSTest`
 
#### Stubbing & Mocking
- Use [`Moq`](https://github.com/moq/moq4) for interfaces and abstract classes
    * [Moq vs other C# mocking frameworks](http://blogs.clariusconsulting.net/kzu/why-do-we-need-yet-another-net-mocking-framework/)

- Use [Microsoft Fakes](https://msdn.microsoft.com/en-us/library/hh549175.aspx) for anything else
    * It generates a fake assembly that the system under test will use instead of the real binary
    * Note that shims are very slow and tedious to setup, so you may want to wrap the dependency if you'll using it frequently
 
#### Coverage
 - Visual Studio: `Tests > Analyze Code Coverage > All Tests`
 - [`OpenCoverage`](https://github.com/OpenCover/opencover)
  * generated HTML reports with [ReportGenerator](https://github.com/danielpalme/ReportGenerator)
 
#### Fake Test Data
 
 - [`Bogus`](https://github.com/bchavez/Bogus) is a port of `faker.js` and has powerful syntax for filling properties with test data
 
#### Code Analysis & Linting
 - Automatic formatting w/ Resharper (ctrl + alt + l)
 - SonarLint
 - StyleCop
 - [`Gendarme`](http://www.mono-project.com/docs/tools+libraries/tools/gendarme/)
