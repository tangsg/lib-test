# Using and linking library code  
In general, libraries are created from many library source files, and are either built as archive files (libmine.a)    
that are statically linked into executables that use them, or as shared object files (libmine.so) that are dynamically    
linked into executables that use them. To link in libraries of these types, use the gcc command line options -L for    
the path to the library files and -l to link in a library (a .so or a .a):   
    -L{path to file containing library} -l${library name}    
    
For example, if I have a library named libmine.so in /home/newhall/lib/ then I'd do the following to link it into my program:   
   $ gcc -o myprog myprog.c  -L/home/newhall/lib -lmine      
   
   
  gcc -o main main.c -L./lib -ladd


# Creating library code   
To create a Library of code you need to do the following:   
(1) Create an INTERFACE to your library: mylib.h   
(2) Create an IMPLEMENTATION of your library: mylib.c   
(3) Create a LIBRARY OBJECT FILE that can be linked with programs that want to use our library code   
(3a) or create a SHARED OBJECT FILE from many .o files that can be linked with programs that want to use your library code   
(4) USE the library in other C code: (a) #include "mylib.h" (b) link in the libary code into a.out file   
(5) Set LD_LIBRARY_PATH environment variable for finding shared objects in non-standard locations at runtime   


  gcc -o libadd.so -c add.c   
  use -c option to gcc to tell it just to create an object file (a .o file) rather than an executable  
  

