# DCIT318-assignment2-11046896


This project contains **three simple applications** demonstrating different aspects of **Object-Oriented Programming (OOP)** in C#:
1. **Inheritance and Method Overriding**
2. **Abstract Classes and Methods**
3. **Interfaces**

---

## 1. Inheritance and Method Overriding

### Description
This example demonstrates **inheritance** and **method overriding** in C#.

- **Base Class:** `Animal` with a virtual method `MakeSound()` printing `"Some generic sound"`.
- **Derived Classes:**  
  - `Dog` overrides `MakeSound()` to print `"Bark"`.  
  - `Cat` overrides `MakeSound()` to print `"Meow"`.

### Code
```csharp
class Animal
{
    public virtual void MakeSound()
    {
        Console.WriteLine("Some generic sound");
    }
}

class Dog : Animal
{
    public override void MakeSound()
    {
        Console.WriteLine("Bark");
    }
}

class Cat : Animal
{
    public override void MakeSound()
    {
        Console.WriteLine("Meow");
    }
}

class Program
{
    static void Main(string[] args)
    {
        Animal genericAnimal = new Animal();
        Dog dog = new Dog();
        Cat cat = new Cat();

        genericAnimal.MakeSound();
        dog.MakeSound();
        cat.MakeSound();
    }
}

```

**Output**

```
Some generic sound
Bark
Meow
```

---

## 2. Abstract Classes and Methods

**Description**

Demonstrates an abstract class `Shape` with an abstract method `GetArea()` and two concrete shapes: `Circle` and `Rectangle`.

**Code**

```csharp
using System;

abstract class Shape
{
    public abstract double GetArea();
}

class Circle : Shape
{
    public double Radius { get; set; }

    public Circle(double radius)
    {
        Radius = radius;
    }

    public override double GetArea()
    {
        return Math.PI * Radius * Radius;
    }
}

class Rectangle : Shape
{
    public double Width { get; set; }
    public double Height { get; set; }

    public Rectangle(double width, double height)
    {
        Width = width;
        Height = height;
    }

    public override double GetArea()
    {
        return Width * Height;
    }
}

class Program
{
    static void Main(string[] args)
    {
        Shape circle = new Circle(5);       // radius = 5
        Shape rectangle = new Rectangle(4, 6); // width = 4, height = 6

        Console.WriteLine($"Circle Area: {circle.GetArea():F2}");
        Console.WriteLine($"Rectangle Area: {rectangle.GetArea():F2}");
    }
}
```

**Output**

```
Circle Area: 78.54
Rectangle Area: 24.00
```

---

## 3. Interfaces

**Description**

Defines an interface `IMovable` and two classes `Car` and `Bicycle` that implement it.

**Code**

```csharp
using System;

interface IMovable
{
    void Move();
}

class Car : IMovable
{
    public void Move()
    {
        Console.WriteLine("Car is moving");
    }
}

class Bicycle : IMovable
{
    public void Move()
    {
        Console.WriteLine("Bicycle is moving");
    }
}

class Program
{
    static void Main(string[] args)
    {
        IMovable car = new Car();
        IMovable bicycle = new Bicycle();

        car.Move();
        bicycle.Move();
    }
}
```

**Output**

```
Car is moving
Bicycle is moving
```

---

