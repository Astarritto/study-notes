Day 1) Memory & Pointers<br>
<br>
1. Stack vs Heap<br>
   ＃Stack<br>
   {<br>
   Memory location: Stack area<br>
   Management: Automatically by compiler<br>
   Size: Relatively small<br>
   Speed: Fast<br>
   Lifetime: Created whed function is called, destroyed automatically<br>
   <br>
   Used for local variables and function calls.<br>
   Memory is automatically released when function returns.<br>
   }<br>
   #Heap<br>
   {<br>
   Memory location: Heap area<br>
   Management: Manually by developer (new/delete)<br>
   Size: Relatively large(dynamic allocation possible)<br>
   Speed: Slower<br>
   Lifetime: Persists until explicitly deleted<br>
   <br>
   Used for dynamic memory allocation. If not released, it can cause Memory Leaks.<br>
   }<br>
   <br>
<br>
3. Pointer vs Reference<br>
   #Pointer<br>
   {<br>
   Declaration: int* ptr<br>
   Can be null: Y<br>
   Can be reassigned: Y<br>
   Memory access: (*ptr)<br>
   <br>
   Stores a memory address. Can be null and can point to different objects.<br>
   }<br>
   #Reference<br>
   {<br>
   Declaration: int& ref<br>
   Can be null: N<br>
   Can be resigned: N<br>
   Memory access: Use like the original variable<br><br>
   
   An alias for another variable. Must be initialized and cannot be reassigned.<br>
   }<br>
  int value = 10;<br>
  // Pointer<br>
  int* ptr = &value;<br>
  *ptr = 20; // value = 20<br>
  // Reference<br>
  int& ref = value;<br>
  ref = 30;  // value = 30<br>
<br>
3. Dangling Pointer & Memory Leak<br>
   Dangling Pointer<br>
   {<br>
   A Pointer that points to memory that has already been freed.<br>
   <br>
   int* ptr = new int(10);<br>
   delete ptr;    // memory released<br>
   // ptr still exists but the memory is freed<br>
   // std::cout << *ptr << std::endl;  // unsafe!<br>
   ptr = nullptr; // safe<br>
   <br>
   points to memory that has beed freed<br>
   }<br>
<br>
   Memory Leak<br>
   {<br>
   Memory that is allocated but not properly released,<br>
   consuming resources until program termination.<br>
   <br>
   int* ptr = new int(10);<br>
   // delete ptr; // if not deleted, Memory Leak occurs<br>
   <br>
   allocated memory is never released, wasting system resources<br>
   }<br>
