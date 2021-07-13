# Activity 4
## Introduction to Polymorphism

## Exercise 4.1 - Introductory Reading - Polymorphism & Abstract Classes

### Pillar 4 - What is 'Polymorphism'?

Polymorphism means many shapes or forms. Building on top of what we know about classes, abstraction, encapsulation and inheritance so far, we can now apply Polymorphism to provide flexibility for subclasses to implement something in many different forms. One tool that can be used to enable Polymorphism is called **Abstract** classes.

### What is an Abstract class?

An Abstract class is an intentionally incomplete class. 

This means that it's the job of subclasses that extend on an abstract class to provide meaning (implementation) for the attributes and methods defined in the abstract class.

Abstract classes enable Software Engineers to collate functionality that subclasses can override i.e. provide their own implementation for.

---

## Exercise 4.2 - Make the base class `Bird` an abstract class

In your existing .NET 5+ Console application project:

- Make your existing `Bird` class an abstract class

- Add the `virtual` keyword to the `Speak()` and `Fly()` methods. This means that subclasses can override the method with their own implementation.

```csharp

public abstract class Bird
{
    public string Name { get; private set; }
    public string Color { get; private set; }

    public Bird(string name, string color)
    {
        Name = name;
        Color = color;
    }

    public virtual void Speak() 
    {
        //To be implemented in subclasses
    }

    public virtual void Fly() 
    {
        //Default implementation
        Console.WriteLine($"Hi there! I can fly.");
    }
}

```

- Abstract classes cannot be instantiated, so let's remove the following code from your `main` method in `program.cs`.

```csharp

Bird myBird = new Bird("Tweety", "Yellow");
myBird.Speak();
myBird.Fly();

```

---

## Exercise 4.3 - Edit the `Pigeon` class to override methods defined by the `Bird` class

- In your existing `Pigeon` class, add the following implementation for the `Speak()` method by overriding the abstract class' `Speak()` method.

- Notice that for the `Pigeon` class, we'd like to use the default implementation for `Fly()` which is defined in the abstract class.


```csharp

//The Pigeon extends the base class Bird
public class Pigeon : Bird
{
    public Pigeon(string name, string color) : base(name, color)
    {
    }

    public override void Speak() 
    {
        Console.WriteLine($"Yo! I'm {Name} and I'm a {Color} pigeon.");
    }
}

```

---
## Exercise 4.4 - Run your console application

- Run your console application. You should see the following output to your console.

```

Yo! I'm Pippa and I'm a Grey pigeon.
Hi there! I can fly.

```

---

## Exercise 4.5 - Create the additional subclass `Penguin` to extend the base class `Bird`

- Add an empty class called `Penguin`
- Add the following code to make the `Penguin` class extend base class `Bird`

```csharp

public class Penguin : Bird
{
    public Penguin(string name, string color) : base(name, color)
    {
    }

    public override void Speak() 
    {
        Console.WriteLine($"Hi! I'm {Name} and I'm a {Color} penguin.");
    }

    public override void Fly() 
    {
        Console.WriteLine($"Whoops, I can't fly. Waddle waddle.");
    }
}

```

---

## Exercise 4.6 - Run your console application

- Add the following code to the `main` method in the `program.cs` file beneath your existing code

```csharp

Penguin pingu = new Pigeon("Pingu", "Black & White");
pingu.Speak();
pingu.Fly();

```

- Run your console application. You should see the following output to your console.

```

Yo! I'm Pippa and I'm a Grey pigeon.
Hi there! I can fly.
Hi! I'm Pingu and I'm a Black & White penguin.
Whoops, I can't fly. Waddle waddle.


```
---

### What's next?

Head over to [Introduction to Interfaces in Activity 5](./activity_5) to learn more.

---

### Key Study Notes

- *Polymorphism* - means many shapes or forms.

- *Abstract class* - an intentionally incomplete class. Abstract classes enable Software Engineers to collate functionality that subclasses can override i.e. provide their own implementation for. This is Polymorphism in action.