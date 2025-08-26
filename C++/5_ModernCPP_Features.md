# Templates in C++<br>
Templates allow wrtiting generic code that works with different data types without rewriting the same logic.
<br><br>
## Function Template<br>
A function template works with any type:<br>
<br> 
<pre>```cpp
template <typename T><br>
T add(T a, T b) <br>
{<br>
    return a + b;<br>
}<br>
<br>
int main() <br>
{<br>
    cout << add<int>(3, 5) << "\n";     // 8<br>
    cout << add<double>(2.5, 4.1) << "\n"; // 6.6<br>
}```</pre><br>
<br>
## Class Template<br>
Classs templates define generic data structures:<br>
<pre>```cpp
template <typename T><br>
class Box <br>
{<br>
private:<br>
    T value;<br>
public:<br>
    Box(T v) : value(v) {}<br>
    T getValue() { return value; }<br>
};<br>
<br>
int main() <br>
{<br>
    Box<int> intBox(42);<br>
    Box<string> strBox("Hello");<br>
<br>
    cout << intBox.getValue() << "\n";   // 42<br>
    cout << strBox.getValue() << "\n";   // Hello<br>
}``` </pre><br>
<br>
<br>
# Standard Template Libray (STL)<br>
The STL provides ready-made data structures and algorithms.<br>
Some common containers: <br>
## vector<br>
A dynamic array that automatically resizes.<br>
<pre>```cpp
#include <vector><br>
#include <iostream><br>
using namespace std;<br>
int main() <br>
{<br>
    vector<int> v = {1, 2, 3};<br>
    v.push_back(4);  // add element<br>
    v[1] = 20;       // access by index<br>
<br>
    for (int x : v) cout << x << " "; // 1 20 3 4<br>
}``` </pre><br>
<br>
## map<br>
A sorted key-value container(implemented as a balanced binary tree).<br>
Keys are unique and automatically ordered.<br><br>
<pre>```cpp
#include <map><br>
#include <iostream><br>
using namespace std;<br>
<br>
int main() <br>
{<br>
    map<string, int> ages;<br>
    ages["Alice"] = 25;<br>
    ages["Bob"] = 30;<br><br>

    for (auto& [name, age] : ages)
    {
        cout << name << " : " << age << "\n";
    }
    // Output is ordered by key
}``` </pre><br><br>

## unordered_map<br>
A hash-table based key-value container.<br>
Faster average lookup, but keys are not ordered.<br>
<pre>```cpp
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
}``` </pre><br><br><br>


# Iterators<br>
Iterators act like pointers for STL containers.<br>
They allow traversal without knowing the underlying structure.<br>
Example: Using Iterators with vector<br>
<pre>```cpp           
#include <vector><br>
#include <iostream><br>
using namespace std;<br>
<br>
int main() <br>
{<br>
    vector<int> v = {10, 20, 30};<br>

    // Explicit iterator
    for (vector<int>::iterator it = v.begin(); it != v.end(); ++it) 
    {
        cout << *it << " "; // 10 20 30
    }
    cout << "\n";

    // Modern range-based loop
    for (int x : v) cout << x << " "; // 10 20 30
}``` </pre><br>
//Iterators also support algorithms like (find), (sort), (for_each) from <algorithm>.<br><br>


#Summary<br>
Templates -> Write generic code once, use with any type.<br>
STL containers -> Ready-made data structures(vector, map, unordered_map)<br>
Iterators -> Provide a unified way to traverse containers.<br><br>

These features make modern C++ both powerful and efficient for real-world applications.<br>
