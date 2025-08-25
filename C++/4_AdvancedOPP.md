day 4) Advanced OOP<br><br>

# Multiple Inheritance vs Interface<br>
## Multiple Inheritance<br>
In C++, a class can inherit from more than one base class.<br>
This is called Multiple Inheritance.<br>
However, it  can leat to issues like the *Diamond Problem* if two classes share a common ancestor.
<br><br>
Example: Multiple Inheritance<br>
class A <br>
{<br>
public:<br>
    void hello() { cout << "Hello from A\n"; }<br>
};<br><br>

class B <br>
{<br>
public:<br>
    void hello() { cout << "Hello from B\n"; }<br>
};<br><br>

class C : public A, public B <br>
{<br>
    // C inherits from both A and B<br>
};<br><br>

int main()<br>
{<br>
    C obj;<br>
    // obj.hello(); // ERROR: ambiguous (both A and B have hello)<br>
    obj.A::hello(); // Explicitly call A’s hello<br>
    obj.B::hello(); // Explicitly call B’s hello<br>
} //This shows the ambiguity when two parent classes define the same function.<br><br>

## Interface<br>
C++ does not have a dedicated interface keyword like Java or C#.<br>
Instead, we create interfaces using pure virtual classes(classes with only pure virtual functions).
<br><br>
class IShape <br>
{<br>
public:<br>
    virtual void draw() = 0; // pure virtual function<br>
    virtual ~IShape() = default; // virtual destructor<br>
};<br><br>

class Circle : public IShape <br>
{<br>
public:<br>
    void draw() override { cout << "Drawing Circle\n"; }<br>
};<br><br>

class Square : public IShape <br>
{<br>
public:<br>
    void draw() override { cout << "Drawing Square\n"; }<br>
};<br><br>

int main() <br>
{<br>
    IShape* shape1 = new Circle();<br>
    IShape* shape2 = new Square();<br><br>

    shape1->draw();
    shape2->draw();

    delete shape1;
    delete shape2;
}//Here, Ishape acts like an interface. Every derived class must implement draw().<br><br><br>


# Pure Virtual Functions<br>
-Declared with =0 at the end.<br>
-Make the class abstract (cannot be instantiated).<br>
-Force derived classes to implement the function.<br><br>

class Animal <br>
{<br>
public:<br>
    virtual void speak() = 0; // pure virtual function<br>
};<br><br>

class Dog : public Animal <br>
{<br>
public:<br>
    void speak() override { cout << "Woof!\n"; }<br>
};<br><br>

int main() <br>
{<br>
    // Animal a; // ERROR: abstract class<br>
    Dog d;<br>
    d.speak();<br>
}<br><br><br>


# override and final Keywords<br>
## override<br>
   -Ensures that a derived class is actually overriding a virtual function.<br>
   -If the function signature doesn't match, the compiler throws an error.
<br><br>
class Base <br>
{<br>
public:<br>
    virtual void print(int x) { cout << "Base print\n"; }<br>
};<br>
<br>
class Derived : public Base<br>
{<br>
public:<br>
    void print(int x) override { cout << "Derived print\n"; }<br>
    // void print(double x) override; // ERROR: signature mismatch<br>
};<br><br>

## final<br>
   -Prevents further overriding of a virtual function.<br>
   -Can also applied to a class to stop inheritance.<br><br>

class Base<br>
{<br>
public:<br>
    virtual void show() final { cout << "Base final show\n"; }<br>
};<br><br>

class Derived : public Base <br>
{<br>
public:<br>
    // void show() override; // ERROR: cannot override final function<br>
};<br><br>

// Class-level final<br>
class FinalClass final <br>
{<br>
    // No other class can inherit from this<br>
};<br><br><br>


#Summary<br>
-Multiple inheritance can be powerful but may cause ambiguity.<br>
-Interfaces in C++ are just abstract classes with pure virtual functions.<br>
-Pure virtual functions force derived classes to implement behavior.<br>
-Use override for safer polymorphosism.<br>
-Use final to prevent overrideng or inheritance.<br>
