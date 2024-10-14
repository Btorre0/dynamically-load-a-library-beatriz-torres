# Assignment 9

the dynamivally loaf a library program purpose is building a mechanism by which the program can load the library into memory (at run time), retrieve the addresses (function and variables) contained inthe library from memory, execute the function ( or access those variables), and unload the library from the memory.

# Loading the Library

Since I am using a mac, using a Unix library. In order to load in the a library, we will be using the following functions:
(```#include <dlfcn.h>```)
```dlopen, dlsym, dlclose```

# steps:

1. use dlopen to load the library

2. use dlsym to get the address of function and/or variables

3. use the retrieved function pointers to call the function

4. unload the library


## context

the header ```<dlfcn.h>``` will be used for dunamic loading functions. In order to load in the library, we will have to use (libmylibrary is a placeholder, not the actual name of the library)```dlopen("libmylibrary.dylib", RTLD_LAZY)```. In order to get the function, we will have to use the following (call function will be init as "my_function") ```dlsym(handle, "my_function")```. Then we will hit it with the ```my_function``` to get the funcition address. To unload, we will use ```dlclose(handle)```.