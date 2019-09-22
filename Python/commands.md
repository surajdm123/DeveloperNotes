### _Commands that are not common_

```
%timeit [i***3 for i in range(10)]          // Returns the time taken to execute this command
```

##### Whenever you want to copy a list or a numpy array, they share the same memory location with normal assignment. We need to use the copy function.
```
a = [1,2,3]
b = a.copy()
```