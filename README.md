# Pillars of Object-Oriented Programming (OOP) - Polymorphism

**`Polymorphism`** is a fundamental concept in object-oriented programming (OOP) that allows objects of different types to be treated as objects of a common base type. There are two types of polymorphism in C#: compile-time (or static) polymorphism and runtime (or dynamic) polymorphism.

1. **`Compile-time Polymorphism (Method Overloading)`**:

Method overloading allows a class to have multiple methods with the same name but different parameters.

```csharp
using System;

class Calculator
{
    // Method Overloading
    public int Add(int a, int b)
    {
        return a + b;
    }

    public double Add(double a, double b)
    {
        return a + b;
    }
}

class Program
{
    static void Main()
    {
        Calculator calculator = new Calculator();

        int resultInt = calculator.Add(5, 10);
        Console.WriteLine("Sum (int): " + resultInt);

        double resultDouble = calculator.Add(5.5, 10.5);
        Console.WriteLine("Sum (double): " + resultDouble);
    }
}
```

In this example, the **`Calculator`** class has two **`Add`** methods with different parameter types. Depending on the argument types used, the compiler will select the appropriate method at compile time.

2. **`Runtime Polymorphism (Method Overriding)`**:

Method overriding allows a derived class to provide a specific implementation of a method that is already defined in its base class.

```csharp
using System;

class Shape
{
    public virtual void Draw()
    {
        Console.WriteLine("Drawing a shape");
    }
}

class Circle : Shape
{
    public override void Draw()
    {
        Console.WriteLine("Drawing a circle");
    }
}

class Square : Shape
{
    public override void Draw()
    {
        Console.WriteLine("Drawing a square");
    }
}

class Program
{
    static void Main()
    {
        Shape shape1 = new Circle();
        Shape shape2 = new Square();

        shape1.Draw();  // Output: Drawing a circle
        shape2.Draw();  // Output: Drawing a square
    }
}
```

In this example, the **`Circle`** and **`Square`** classes inherit from the **`Shape`** class. The **`Draw`** method is marked as **`virtual`** in the base class and overridden in the derived classes. At runtime, the appropriate version of the **`Draw`** method is called based on the actual type of the object.

These examples illustrate how polymorphism in C# allows for flexibility and extensibility in your code by enabling you to work with objects of various types in a consistent manner.
