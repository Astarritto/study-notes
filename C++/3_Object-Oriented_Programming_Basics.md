day 3) Object-Oriented Programming Basics<br><br>

1.Key Concepts<br><br>

# Encapsulation<br>
:Bundling data (variables) and methods that operate on the data<br>
into a single unit (class), and restricting access using acciss modifiers(private, protected, public).<br>

# Inheritance<br>
:A class can inherit attributes and methods from another class.<br>
Enables code reuse and hierarchical relationships.<br><br>

# Polymorphism<br>
:Objects can be treated as instances of their parent class.<br>
-Compile-time(overloading): Same function name, different parameters<br>
-Run-time(overriding): Child class provides its own implementation of a parent's virtual function<br><br>

# Abstraction<br>
:Hiding implementation details while exposing only necessary functionality.<br>
Typically achieved through abstract classes or interfaces.<br>
Focuses on what a class does, not how it does it.<br><br><br>


2.Virtual Functions & Abstract Classes<br><br>

# Virtual Function<br>
:A function in a base class that can be overriden in a derived class.<br>
Allows dynamic (run-time) polymorphism.<br><br>

#Abstract Class<br>
:A class that contains at least one pure virtual function.<br>
Cannot be instantiated directly; serves as a base class.<br>
Implements abstraction by defining what actions a class should perform,<br>
while leaving the actual implementation to derived classes.<br><br><br>


Example (conceptual, no full code required):<br><br>

class Animal<br>
{<br>
public:<br>
  virtual void Speak() = 0; // pure virtual function<br>
};  <br><br>

class Dog : public Animal<br>
{<br>
public:<br>
  void Speak() override {/*bark*/}<br>
};<br><br>

class Cat : public Animal<br>
{<br>
public:<br>
  void Speak() override {/*meow*/}<br>
};<br><br>

Explanation:<br>
Animal is abstract because it has a pure virtual function Speak().<br>
Dog and Cat override Speak().<br>
At runtime, you can call Speak() on an Animal* pointer, and the correct derived function executes (polymorphism).<br>
Abstraction is demonstrated because Animal defines what Speak() should do, but the how is implemented in the child classes.<br>
