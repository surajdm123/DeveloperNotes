#### Why Numpy?
- It is faster.
- It is convenient.

```
import numpy as np                  //To import numpy
a = np.array([1,2,3])               // To create a numpy array
b = np.array([[1,2],[1,2,3]])       // To create a multidimension array
a.shape                             // This will return the dimensions of the array
a.ndim                              // Returns the number of rows
np.arange(10)                       // Returns a ndarray ranging from 1-9
np.arange(2,12)                     // Returns a ndarray ranging from 2-11
np.arange(2,12,2)                   // Returns a ndarray ranging from 2-11 but in skips of 2
np.zeros((3,2))                     // Returns a (3,2) ndarray of 0s
np.ones((3,2))                      // Returns a (3,2) ndarray of 1s
np.full((3,2),3)                    // Returns a (3,2) ndarray of 2s
np.full((3,2),2)                    // Returns a (3,2) ndarray of 3s
np.full((3,2),2.2, dtype=np.int)    // Returns a (3,2) ndarray of 2s - only int values
np.eye(3)                           // Creates an identity matrix of dimensions 3 X 3
np.diag([1,2,3,4,5])                // Creates a diagnol matrix with values given in the list
np.tile([1,2,3],(3,1))              // Stacks [1,2,3] horizontally three times
np.tile([1,2,3],(3,2))              // Stacks [1,2,3] horizontally three times and vertically two times
np.random.random()                  // Returns a random value between 0 to 1
50*np.random.random()               // Returns a value between 0 - 50
48*np.random.random() + 2           // Returns a value between 2 - 50

np.linspace(1,50,100)               // Returns 100 values from 1 - 50 and are equally spaced
np.arange(18).reshape(2,3,3)        // Reshape the dimensions of the numpy array
np.shares_memory(a,b)               // Retruns True if a & b share the same memory location
a.T                                 // Transposes a matrix
np.linalg.det(a)                    // returns the determinant of matrix a 
```

### Open the notebook to view more