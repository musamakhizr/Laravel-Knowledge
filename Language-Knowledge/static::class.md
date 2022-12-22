# static::class
In PHP, static::class is a language construct that returns the fully qualified name of the class that it is called from. It is a way to get the name of the current class from within a class method.

For example, consider the following PHP class:

```php
class MyClass {
    public static function getClassName() {
        return static::class;
    }
}
```

If you call MyClass::getClassName(), the function will return "MyClass".

This construct is particularly useful in PHP when working with inheritance, as it allows you to access the name of the actual class that a method is being called on, rather than the name of the parent class.

For example:

```php
class MyClass {
    public static function getClassName() {
        return static::class;
    }
}

class MySubClass extends MyClass {
    // ...
}

echo MyClass::getClassName();  // Outputs "MyClass"
echo MySubClass::getClassName();  // Outputs "MySubClass"
```

In this example, the `getClassName()` method is defined in the `MyClass` class, but it is being called on both `MyClass` and `MySubClass`. 
<br>When called on `MyClass`, the method returns "MyClass", as expected. When called on `MySubClass`, the method returns "MySubClass", because `static::class` returns the name of the actual class that the method is being called on (`MySubClass`), rather than the name of the parent class (`MyClass`).
