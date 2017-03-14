## Sinon for Microsoft Fakes Assembly

Given a shimmed class, `Some.Namespace.Fakes.MyShim` with `Some.Namespace.Fakes.MyShim.AllInstances`:

```C#
var shimType = typeof(Some.Namespace.Fakes.MyShim);
var allInstances = typeof(Some.Namespace.Fakes.MyShim.AllInstances);
```

- Take the set difference of `shimType.GetMethods()` and `allInstances.GetMethods()`
    * The result should be a method called `Constructor` and several `set_ConstructorWithArgumentTypesListedInOrder`
    * Might need to filter static methods out of `shimType.GetMethods()` (?)
- Using `TypeBuilder` from `System.Reflection.Emit`, create a new class with `shimType` as the base
    * For each method, create a property named `MethodNameInfo`
    * Could allow for assertions like `Assert.IsTrue(MyShimClass.MyMethodNameInfo.Called)`
    * Unfortunately can't just use the method name: http://stackoverflow.com/questions/15522242/can-a-property-name-and-a-method-name-be-same-in-c
- Strip the `set_` from the `set_Constructor` methods and programatically set each constructor to return a subclass of the shim type
    * `myShimSubClass.GetProperty("ConstructorStringString").SetValue(object, value)`
    * Store the constructor parameters somehow (?)
