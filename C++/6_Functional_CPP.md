#Lambda Expressions<br>
##Definition
Anonymous functions without a name
Can be used as function objects on the fly
Commonly used for short callbacks, STL algorithms, and event handling

##Syntax

//[capture](parameters)->return_type{body}
auto sum = [](int a, int b) -> int {return a + b};
int result = sum(3, 5); //result = 8

##Explanation
[ ] : capture external variables
(int a, int b): parameters
->int : return type(optional)
{return a + b} : function body

##Example with STL algorithm

#include <algorithm>
#include <vector>
#include <iostream>

std::vector<int> numbers = {1, 2, 3, 4, 5};
int count = std::count_if(numbers.begin(), numbers.end(), [](int n){ return n % 2 == 0; });
std::cout << count; // number of even numbers = 2

#std::function & std::bind
##std::function
Can store function pointers, lambdas, member functions in a uniform type
Allows functions to be stored and passed like variables

#include <functional>
#include <iostream>

std::function<int(int,int)> add = [](int a,int b){ return a+b; };
std::cout << add(2,3); // 5


##std::bind
Binds some arguments of a function to create a new callable object
Useful for callbacks and event handling

#include <functional>
#include <iostream>

int Multiply(int a, int b){ return a*b; }

auto times10 = std::bind(Multiply, std::placeholders::_1, 10);
std::cout << times10(5); // 50 = 5*10

_1, _2, etc. indicate the positions of arguments to be passed later


#Delegate(C++ style)
##Definition
Similar to delegates in C#
Allows storing and calling functions as objects
In C++, typically implemented using lambda + std::function + bind

##Example
#include <functional>
#include <vector>
#include <iostream>

std::vector<std::function<void(int)>> callbacks;

void RegisterCallback(std::function<void(int)> cb){ callbacks.push_back(cb); }

void TriggerCallbacks(int value){
    for(auto& cb : callbacks) cb(value);
}

int main(){
    RegisterCallback([](int n){ std::cout << "Callback: " << n << "\n"; });
    TriggerCallbacks(42); // "Callback: 42"
}

##Explanation
callbacks vector stores multiple functions
Functions are registered via RegisterCallback anc triggered via TriggerCallbacks
Mimics C#-style delegates in C++ for event/callback chains

#Key Takeaways
1. Lambda Expressions → Anonymous functions for inline callbacks
2. std::function → Store and pass function objects like variables
3. std::bind → Pre-bind some arguments, create new function objects
4. C++ Delegates → Combine lambda + std::function + bind for flexible event/callback handling
