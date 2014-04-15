easy-code-profiling
===================

How to profile scientific codes easily.  


1 - You need `gprof`. It is installed by default on almost every linux distribution.  
2 - Compile your code with option `-pg`  
```
gfortran -pg main.90
```

3 - Execute your code as usual  
```
./mdft
```

Execution time should be representative of a usual run. Do not profile your code with test cases that are made to finish shortly. If your code takes 2 days to finish, that make your run last for half a day at minimum.  
Why? Because some initializations, memory allocations, input reading etc. may be time limitants for short runs, not for canonical runs.

4 - Profile  
```
gprof ./mdft
```


