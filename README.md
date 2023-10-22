# JavaSE-FinalVariablesAndMethods

In Java, **"final"** is a keyword that can be applied to variables, methods, and classes. 

When applied to variables, it means that the **variable's value cannot be changed** after it has been assigned a value. 

# Final Variables

```java
public class Example {
    // Final variable (constant)
    final int constantValue = 10;

    public static void main(String[] args) {
        Example example = new Example();
        // Trying to change the value of a final variable will result in a compilation error
        // example.constantValue = 20; // This line will cause a compilation error
        System.out.println(example.constantValue);
    }
}
```

In this example, constantValue is a final variable, and any attempt to change its value will result in a compilation error.

# Final Methods

When applied to methods, it means that the **method cannot be overridden** by subclasses.

```java
public class Parent {
    // Final method that cannot be overridden
    public final void displayMessage() {
        System.out.println("This is a final method in the Parent class.");
    }
}

public class Child extends Parent {
    // Attempting to override a final method will result in a compilation error
    // @Override
    // public void displayMessage() {
    //     System.out.println("This is an attempt to override the final method.");
    // }

    public static void main(String[] args) {
        Child child = new Child();
        child.displayMessage();
    }
}
```

In this example, displayMessage is a final method in the Parent class. 

If you uncomment the overridden method in the Child class, it will result in a compilation error because final methods cannot be overridden.

Final variables are often used to create constants, and final methods are used to prevent further modification of a method's behavior in subclasses.

# Final Classes

In Java, a **final** class is a class that **cannot be subclassed or extended**. 

Once a class is marked as final, it means that no other class can inherit from it. 

This is achieved by using the final keyword in the class declaration.

```java
final class FinalClass {
    // Class members and methods
}
```

In this example, FinalClass is marked as final, so you cannot create a new class that extends FinalClass. 

For instance, the following code would result in a compilation error:

```java
// This will result in a compilation error
class SubClass extends FinalClass {
    // Some code
}
```

Additionally, you can have final methods and final variables within a class. 

A final method in a class cannot be overridden by any subclass, and a final variable cannot be reassigned after its initial assignment.

```java
class MyClass {
    final int myConstant = 10; // A final variable

    final void myFinalMethod() {
        // Some code
    }
}

class SubClass extends MyClass {
    // You cannot override myFinalMethod here

    // You cannot reassign myConstant here
}
```

The primary use of final classes, methods, and variables is to ensure that certain aspects of your code remain unchanged. 

This can contribute to code safety, optimization, or design considerations.

# Difference between Final Classes and Sealed Classes

 In Java, both final classes and sealed classes provide mechanisms to control class inheritance, but they differ in their flexibility and purpose.

## Final Classes:

Immutability: A final class cannot be subclassed or extended. Once a class is marked as final, it means that no other class can inherit from it.

```java
final class FinalClass {
    // Class members and methods
}
```

Use Cases:

- When you want to prevent further extension of a class.

- When you want to ensure that the class cannot be overridden or modified.

## Sealed Classes

Limited Subclassing: A sealed class allows you to specify which classes can be subclasses. 

You can explicitly declare which subclasses are allowed, and any other attempt to subclass it will result in a compilation error.

```java
sealed class SealedClass permits SubClass1, SubClass2 {
    // Class members and methods
}

final class SubClass1 extends SealedClass {
    // Subclass 1 implementation
}

final class SubClass2 extends SealedClass {
    // Subclass 2 implementation
}
```

Use Cases:

- When you want to control and limit the hierarchy of subclasses.

- When you want to provide a set of known subclasses and prevent external classes from extending the sealed class.

In summary, while **final classes** prevent any subclassing, **sealed classes** allow you to specify a limited set of subclasses. 

Sealed classes provide more flexibility in terms of inheritance while still maintaining control over the hierarchy. 

The choice between them depends on the design requirements and the level of control you want over the class hierarchy.
