Day 2 Smart Pointers & RAII<br><br>
1. RAII (Resource Acquisition Is Initialization)<br>
{<br>
Definition: A C++ idiom that binds resource management (memory, file handles, sockets, etc.) to object lifetime.<br>
Principle: Acquire resources in the constructor, release them in the destructor.<br>
Benefit: Automatic cleanup, prevents resource leaks, esception-safe code.<br>
Example(conceptual):<br>
class FileGuard<br>
  {<br>
  public:<br>
  FileGuard(const char* filename){file = fopen(filename,"r") ;}<br>
  ~FileGuard() { if(file) fclose (file); }<br><br>

  private:<br>
  FILE* file;<br>
  }<br>
---------------FileGuard automatically closes the file when it goes out of scope<br>
}<br><br><br>
2. Smart Pointers<br>
{<br>
Definition: Objects that manage dynamic memory automatically, following RAII.<br>
Types in modern C++:<br>
  a) std::unique_ptr<br>
  Owns a resource exclusively (cannot be copied, only moved).<br>
  Automatically deletes the resource when it goes out of scope.<br>
  Use case: Single ownership.<br>
  {<br>
  std::unique_ptr<int> ptr = std::make_unique<int>(42)<br>
  }<br><br>
  b) std::shared_ptr<br>
  Shared ownership (reference-counted).<br>
  Deletes the resource when the last owner goes out of scope.<br>
  Use case: Multiple owners.<br>
  {<br>
  std::shared_ptr<int> ptr1 = std::make_shared<int>(42);<br>
  std::shared_ptr<int> ptr2 = ptr1; // shared ownership<br>
  }<br><br>
  c) std::weak_ptr<br>
  Non-owning reference to a shared_ptr.<br>
  Does not increase reference count.<br>
  Useful to avoid cyclic references.<br>
  std::weak_ptr<int> wptr = ptr1;<br><br>
3. Benefits of Smart Pointers<br>
 -Automatic memory management -> prevents leaks.<br>
 -Exception-safe code -> no need to manually delete.<br>
 -Clear ownership semantics(unique_ptr vs shared_ptr).<br><br>
4. Best Practices<br>
 -Prefer std::unique_ptr unless shared ownership is necessary.<br>
 -Avoid raw new / delete in modern C++.<br>
 -Use std::weak_ptr to break cycles in shared_ptr graphs.<br>
 -RAII + SmartPointers together provide robust resource management.<br><br>


}<br>
