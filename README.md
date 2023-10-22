# JavaSE-FinalVariablesAndMethods

In Java, **"final"** is a keyword that can be applied to variables, methods, and classes. 

When applied to variables, it means that the variable's value cannot be changed after it has been assigned a value. 

When applied to methods, it means that the method cannot be overridden by subclasses.

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
