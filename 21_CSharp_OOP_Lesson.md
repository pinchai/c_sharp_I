# Object-Oriented Programming (OOP)

## Learning Objectives

By the end of this lesson, students should be able to:

- Explain what OOP is
- Create classes and objects
- Use fields, properties, and methods
- Create constructors
- Understand the four main OOP principles:
  - Encapsulation
  - Inheritance
  - Polymorphism
  - Abstraction

---

# 1. What is OOP?

**Object-Oriented Programming (OOP)** is a programming approach that organizes code around **objects**.

An object represents something from the real world.

```text
Student
 ├── Name
 ├── Age
 ├── Email
 └── Study()
```

In C#, we use a **class** to define what an object looks like and what it can do.

```csharp
class Student
{
    public string Name;
    public int Age;

    public void Study()
    {
        Console.WriteLine($"{Name} is studying.");
    }
}
```

---

# 2. Class vs Object

## Class

A **class** is a blueprint.

```csharp
class Student
{
    public string Name;
    public int Age;
}
```

## Object

An **object** is an instance of a class.

```csharp
Student student1 = new Student();

student1.Name = "Dara";
student1.Age = 20;
```

We can create multiple objects from the same class:

```csharp
Student student1 = new Student();
student1.Name = "Dara";

Student student2 = new Student();
student2.Name = "Sokha";
```

Both objects use the same `Student` class but contain different data.

---

# 3. Fields

A field stores data inside an object.

```csharp
class Student
{
    public string Name;
    public int Age;
}
```

Using fields:

```csharp
Student student = new Student();

student.Name = "Dara";
student.Age = 20;

Console.WriteLine(student.Name);
Console.WriteLine(student.Age);
```

---

# 4. Methods

A method defines behavior.

```csharp
class Student
{
    public string Name;

    public void Study()
    {
        Console.WriteLine($"{Name} is studying.");
    }
}
```

Usage:

```csharp
Student student = new Student();

student.Name = "Dara";
student.Study();
```

Output:

```text
Dara is studying.
```

---

# 5. Properties

In modern C#, **properties** are generally preferred over public fields for controlling access to data.

```csharp
class Student
{
    public string Name { get; set; }
    public int Age { get; set; }
}
```

Usage:

```csharp
Student student = new Student();

student.Name = "Dara";
student.Age = 20;

Console.WriteLine(student.Name);
```

---

# 6. Constructor

A **constructor** runs when an object is created.

```csharp
class Student
{
    public string Name { get; set; }
    public int Age { get; set; }

    public Student(string name, int age)
    {
        Name = name;
        Age = age;
    }
}
```

Now we can create an object with initial values:

```csharp
Student student = new Student("Dara", 20);

Console.WriteLine(student.Name);
Console.WriteLine(student.Age);
```

Output:

```text
Dara
20
```

---

# 7. Encapsulation

**Encapsulation** means protecting an object's internal data and controlling how it can be accessed or modified.

Instead of:

```csharp
class BankAccount
{
    public double Balance;
}
```

we can use:

```csharp
class BankAccount
{
    private double balance;

    public double GetBalance()
    {
        return balance;
    }

    public void Deposit(double amount)
    {
        if (amount > 0)
        {
            balance += amount;
        }
    }
}
```

Usage:

```csharp
BankAccount account = new BankAccount();

account.Deposit(100);

Console.WriteLine(account.GetBalance());
```

The `balance` field cannot be directly modified from outside the class.

---

# 8. Inheritance

**Inheritance** allows one class to reuse members of another class.

```csharp
class Animal
{
    public void Eat()
    {
        Console.WriteLine("Animal is eating.");
    }
}
```

Create a child class:

```csharp
class Dog : Animal
{
    public void Bark()
    {
        Console.WriteLine("Dog is barking.");
    }
}
```

Usage:

```csharp
Dog dog = new Dog();

dog.Eat();
dog.Bark();
```

Output:

```text
Animal is eating.
Dog is barking.
```

The `Dog` class inherits `Eat()` from `Animal`.

---

# 9. Polymorphism

**Polymorphism** means that the same method/interface can behave differently depending on the object.

Use `virtual` and `override`:

```csharp
class Animal
{
    public virtual void MakeSound()
    {
        Console.WriteLine("Animal makes a sound.");
    }
}
```

Child classes:

```csharp
class Dog : Animal
{
    public override void MakeSound()
    {
        Console.WriteLine("Dog says Woof!");
    }
}

class Cat : Animal
{
    public override void MakeSound()
    {
        Console.WriteLine("Cat says Meow!");
    }
}
```

Now:

```csharp
Animal animal1 = new Dog();
Animal animal2 = new Cat();

animal1.MakeSound();
animal2.MakeSound();
```

Output:

```text
Dog says Woof!
Cat says Meow!
```

The variable type is `Animal`, but the actual object determines which implementation runs.

---

# 10. Abstraction

**Abstraction** means hiding implementation details and exposing only what is necessary.

C# supports abstraction through **abstract classes** and **interfaces**.

## Abstract Class

```csharp
abstract class Animal
{
    public abstract void MakeSound();
}
```

Child class:

```csharp
class Dog : Animal
{
    public override void MakeSound()
    {
        Console.WriteLine("Woof!");
    }
}
```

You cannot directly create an object of an abstract class:

```csharp
// Error
Animal animal = new Animal();
```

But you can do:

```csharp
Animal dog = new Dog();

dog.MakeSound();
```

---

# 11. Interface

An interface defines a contract.

```csharp
interface IPayment
{
    void Pay(double amount);
}
```

A class implements the interface:

```csharp
class CreditCardPayment : IPayment
{
    public void Pay(double amount)
    {
        Console.WriteLine($"Paid ${amount} using credit card.");
    }
}
```

Another implementation:

```csharp
class KHQRPayment : IPayment
{
    public void Pay(double amount)
    {
        Console.WriteLine($"Paid ${amount} using KHQR.");
    }
}
```

Usage:

```csharp
IPayment payment1 = new CreditCardPayment();
IPayment payment2 = new KHQRPayment();

payment1.Pay(100);
payment2.Pay(50);
```

This is a good real-world example of **abstraction + polymorphism**.

---

# 12. The Four Principles of OOP

| Principle | Meaning |
| --- | --- |
| **Encapsulation** | Protect and control data |
| **Inheritance** | Reuse functionality from another class |
| **Polymorphism** | Same interface, different behavior |
| **Abstraction** | Hide implementation details |

A simple way to remember:

```text
Encapsulation → Protect
Inheritance   → Reuse
Polymorphism  → Different behavior
Abstraction   → Hide complexity
```

---

# 13. Complete Example

Let's create a simple banking application.

```csharp
class BankAccount
{
    public string Owner { get; set; }

    private decimal balance;

    public BankAccount(string owner, decimal initialBalance)
    {
        Owner = owner;
        balance = initialBalance;
    }

    public decimal GetBalance()
    {
        return balance;
    }

    public void Deposit(decimal amount)
    {
        if (amount <= 0)
        {
            Console.WriteLine("Invalid amount.");
            return;
        }

        balance += amount;
    }

    public bool Withdraw(decimal amount)
    {
        if (amount <= 0 || amount > balance)
        {
            return false;
        }

        balance -= amount;
        return true;
    }
}
```

Use the class:

```csharp
BankAccount account =
    new BankAccount("Dara", 1000);

account.Deposit(500);

account.Withdraw(200);

Console.WriteLine(account.Owner);
Console.WriteLine(account.GetBalance());
```

Output:

```text
Dara
1300
```

This example demonstrates:

- Class
- Object
- Properties
- Constructor
- Methods
- Encapsulation

---

# 14. Practice Exercises

## Exercise 1 — Student

Create a `Student` class with:

```text
Name
Age
Email
```

Add a method:

```csharp
DisplayInfo()
```

Expected output:

```text
Name: Dara
Age: 20
Email: dara@example.com
```

---

## Exercise 2 — Product

Create a `Product` class:

```text
Id
Name
Price
Quantity
```

Add:

```csharp
GetTotalPrice()
```

Formula:

```text
Total = Price × Quantity
```

---

## Exercise 3 — Inheritance

Create:

```text
Animal
 ├── Dog
 └── Cat
```

`Animal` should have:

```csharp
MakeSound()
```

Override it in `Dog` and `Cat`.

Expected:

```text
Dog: Woof!
Cat: Meow!
```

---

## Exercise 4 — Payment System

Create:

```text
IPayment
 ├── CreditCardPayment
 ├── KHQRPayment
 └── CashPayment
```

Each class should implement:

```csharp
Pay(decimal amount)
```

This exercise demonstrates **interfaces and polymorphism**.

---

# Lesson Summary

```text
C# OOP
│
├── Class
│   └── Blueprint
│
├── Object
│   └── Instance of a class
│
├── Properties
│   └── Store object data
│
├── Methods
│   └── Object behavior
│
├── Constructor
│   └── Initialize objects
│
├── Encapsulation
│   └── Protect data
│
├── Inheritance
│   └── Reuse code
│
├── Polymorphism
│   └── Different behavior
│
└── Abstraction
    └── Hide implementation
```

## Recommended Learning Step

```text
Class/Object
    ↓
Fields/Properties
    ↓
Methods
    ↓
Constructor
    ↓
Encapsulation
    ↓
Inheritance
    ↓
Polymorphism
    ↓
Abstraction
    ↓
Interface
    ↓
Mini Project
```
