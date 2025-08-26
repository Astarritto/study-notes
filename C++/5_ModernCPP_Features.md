# Templates in C++<br>
Templates allow wrtiting generic code that works with different data types without rewriting the same logic.
<br><br>
## Function Template<br>
A function template works with any type:<br>
<br> 
```cpp
template <typename T>
T add(T a, T b)
{
    return a + b;
}

int main()
{
    cout << add<int>(3, 5) << "\n";     // 8
    cout << add<double>(2.5, 4.1) << "\n"; // 6.6
}
```
<br>
<br>
## Class Template<br>
Classs templates define generic data structures:
<br>

```cpp
template <typename T>
class Box
{
private:
    T value;
public:
    Box(T v) : value(v) {}
    T getValue() { return value; }
};

int main()
{
    Box<int> intBox(42);
    Box<string> strBox("Hello");

    cout << intBox.getValue() << "\n";   // 42
    cout << strBox.getValue() << "\n";   // Hello
}
```
<br>
<br>
<br>
# Standard Template Libray (STL)<br>
The STL provides ready-made data structures and algorithms.<br>
Some common containers: <br>
## vector<br>
A dynamic array that automatically resizes.<br>

```cpp
#include <vector>
#include <iostream>
using namespace std;
int main()
{
    vector<int> v = {1, 2, 3};
    v.push_back(4);  // add element
    v[1] = 20;       // access by index

    for (int x : v) cout << x << " "; // 1 20 3 4
}
```
<br>
## map<br>
A sorted key-value container(implemented as a balanced binary tree).<br>
Keys are unique and automatically ordered.<br><br>

```cpp
#include <map>
#include <iostream>
using namespace std;

int main()
{
    map<string, int> ages;
    ages["Alice"] = 25;
    ages["Bob"] = 30;

    for (auto& [name, age] : ages)
    {
        cout << name << " : " << age << "\n";
    }
    // Output is ordered by key
}
```
<br><br>

## unordered_map<br>
A hash-table based key-value container.<br>
Faster average lookup, but keys are not ordered.<br>
```cpp
#include <unordered_map><br>
#include <iostream><br>
using namespace std;<br><br>

int main() <br>
{<br>
    unordered_map<string, int> scores;<br>
    scores["Math"] = 95;<br>
    scores["English"] = 88;<br><br>

    for (auto& [subject, score] : scores) 
    {
        cout << subject << " : " << score << "\n";
    }
}
```
<br><br><br>


# Iterators<br>
Iterators act like pointers for STL containers.<br>
They allow traversal without knowing the underlying structure.<br>
Example: Using Iterators with vector<br>
```cpp
#include <vector>
#include <iostream>
using namespace std;

int main()
{
    vector<int> v = {10, 20, 30};

    // Explicit iterator
    for (vector<int>::iterator it = v.begin(); it != v.end(); ++it) 
    {
        cout << *it << " "; // 10 20 30
    }
    cout << "\n";

    // Modern range-based loop
    for (int x : v) cout << x << " "; // 10 20 30
}
```
<br>
Iterators also support algorithms like (find), (sort), (for_each) from <algorithm>.<br><br>


#Summary<br>
Templates -> Write generic code once, use with any type.<br>
STL containers -> Ready-made data structures(vector, map, unordered_map)<br>
Iterators -> Provide a unified way to traverse containers.<br><br>

These features make modern C++ both powerful and efficient for real-world applications.<br>
