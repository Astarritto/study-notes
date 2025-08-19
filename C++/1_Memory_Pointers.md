Day 1) Memory & Pointers

1. Stack vs Heap
   ＃Stack
   {
   Memory location: Stack area
   Management: Automatically by compiler
   Size: Relatively small
   Speed: Fast
   Lifetime: Created whed function is called, destroyed automatically
   
   Used for local variables and function calls.
   Memory is automatically released when function returns.
   }
   #Heap
   {
   Memory location: Heap area
   Management: Manually by developer (new/delete)
   Size: Relatively large(dynamic allocation possible)
   Speed: Slower
   Lifetime: Persists until explicitly deleted
   
   Used for dynamic memory allocation. If not released, it can cause Memory Leaks.
   }
   

3. Pointer vs Reference
   #Pointer
   {
   Declaration: int* ptr
   Can be null: Y
   Can be reassigned: Y
   Memory access: (*ptr)
   
   Stores a memory address. Can be null and can point to different objects.
   }
   #Reference
   {
   Declaration: int& ref
   Can be null: N
   Can be resigned: N
   Memory access: Use like the original variable
   
   An alias for another variable. Must be initialized and cannot be reassigned.
   }
  int value = 10;
  // Pointer
  int* ptr = &value;
  *ptr = 20; // value = 20
  // Reference
  int& ref = value;
  ref = 30;  // value = 30

3. Dangling Pointer & Memory Leak
   Dangling Pointer
   {
   A Pointer that points to memory that has already been freed.
   
   int* ptr = new int(10);
   delete ptr;    // memory released
   // ptr still exists but the memory is freed
   // std::cout << *ptr << std::endl;  // unsafe!
   ptr = nullptr; // safe
   
   points to memory that has beed freed
   }

   Memory Leak
   {
   Memory that is allocated but not properly released,
   consuming resources until program termination.
   
   int* ptr = new int(10);
   // delete ptr; // if not deleted, Memory Leak occurs
   
   allocated memory is never released, wasting system resources
   }
