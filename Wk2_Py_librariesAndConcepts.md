# Scope rules

- LEGB :  **L**ocal **E**nclosing function **G**lobal **B**uilt-in
- **name error exception** often is raised if Python cannot find an object with the name provided

**Class**
To remove elements of a list, you can use remove function. :exclamation: if multiple occurences of an element exists, only the first occurance is removed

```python
x = [2,35,57,4,10]
x.remove(10) # to remove the element
```

Now, to remove the largest element in list x you could write `x.remove(max(x))` OR if you feel that you use this a lot, you could define a custom class definition that _inherits_ all functions of list, in addition to creating couple of its own

```python
class MyList(list):
  def remove_min(self):
    self.remove(min(self))
  def remove_max(self):
    self.remove(max(self))
```
Our custom class can be used as follows

```python
x = [2,35,57,4,10]
# dir(x) # should show all available functions for list x
y = myList(x)
# dir(y) # should show all available functions like x in addition to your custom remove_min and remove_max
y.remove_max() # should give [2,35,4,10]
```
# NumPy

`import numpy as np`

- **Numpy arrays** 
    - Declaration: `np.array()` with argument is a list. It is good practice to declare matrices with capitalized names
      `x = np.array([1,4,8])`
      
      `A = np.array([[]1,2],[4,8])` nested list object signifying the rows in the matrix
      
      To transpose the above matrix `A.transpose()`
    - an additional datatype provided by numpy that can be used to represent vectors and matrices
    - unlike dynamically growing python lists, these have a fixed size when constructed i.e. its length can't be modified once created
    - have elements of the same data type. _Default_: floating type numbers

```python
import numpy as np
# create a vector and matrix with zeros as elements
zero_vector = np.zeros(5) # single argument for the number of elements
zero_matrix = np.zeros((5,3)) # argument is a tuple with number of rows and columns as the two elements
```
  - Similarly there is `np.ones()` function that can create a vector or matrix with ones as elements
  - To create an empty array `np.empty()`

  - it can be _sliced_ and _indexed_ just like regular lists
```python
x = np.array([1,2,3])
y = np.array([4,5,6])

X = np.array([[1,2,3], [5,7,9]])
Y = np.array([[12,5,7], [22,5,9]])

# operations you can do
x[2] # index
x[0:2] # slice

x + y # add elements of array
# note that this is very different from regular lists which would simply concatanate the two lists

X[:,1] # get second column. Remember the syntax is row,column , so : will give all rows
X[:,1] + Y[:,1]
X[1,:] # get second row
X[1] # shorthand notation to get first row as above
```
**Indexing**
Numpy arrays can be accessed by both numerical and logical index
```python
#numerical
z1 = np.array([2,4,6,8,0])
z2 = z1 + 1 # [3,5,7,9,1]

index = [0,2,3]
z1[index] # [2,6,8]

idx = np.array([0,2,3])
z1[index] # [2,6,8]

#logical

z1 > 6 # (False, False, False, True, False)

z1[z1 > 6] # [8]

ind = z1 > 6 
z1[ind] # [8]
```
**Indexing vs Slicing**

Slicing gives you a _view_ of the object, so if you modify the slice, you modify the original object. In contrast, indexing gives you a _copy_ of the original data
```python
# slicing
z1 = np.array([2,4,6,8,0,8,44])
w = z1[0:4] # [2,4,6,8]
w[0] = 28 # [28,4,6,8]
z1 # [28,4,6,8,0,8,44]

# in contrast indexing
z2 = np.array([2,4,6,8,0,8,44])
ind = [0,1,2,3]
w2 = z1[ind] # [2,4,6]
w2[0] = 28 # [28,4,6,8]
z2 # [2,4,6,8,0,8,44]
```

  - linearly spaced lists from 0 to 100 using `np.linspace(start, end, desired number of points)`  :exclamation:  end number inclusive
  
    `np.linspace(0,100,10)` will give
    
    ```
    array([   0.        ,   11.11111111,   22.22222222,   33.33333333,
         44.44444444,   55.55555556,   66.66666667,   77.77777778,
         88.88888889,  100.        ])
    ```
   - logarithmatically spaced list from 10 to 100 using `np.logspace(log of starting point, log of end, number of points)` So if you want the array to start from 10, log of 10 = 1, for it to end in 100 we give log 100 = 2
   `np.logspace(1,2,10)`
   ```
   array([  10.        ,   12.91549665,   16.68100537,   21.5443469 ,
         27.82559402,   35.93813664,   46.41588834,   59.94842503,
         77.42636827,  100.        ])
   ```
   Another way to generate the above array without remembering the log10 of numbers
   `np.logspace(np.log10(10), np.log10(100), 10)`

**Dimension/shape of array**

:exclamation: shape & size below are data attributes of the arrays (not methods), hence they are not followed by ()

```python
X = np.array([[1,2,3], [5,7,9]])
X.shape # (2,3)
X.size # 6
```

```python
random.seed(4)
x = np.random.random(10) # 10 random numbers from 0 to 1
np.any(x > 0.9) # True 
np.all(x > = 0.1) # True
```


# Function vs Class
Source: [Python Function versus Class: what is the difference between using either methods?](https://www.quora.com/Python-Function-versus-Class-what-is-the-difference-between-using-either-methods)

Functions are easier to work with and understand than objects. However, one of the key benefits of classes is that they allow _inheritance_. This means you can create a superclass then make subclasses of it that are more specific.

# Matplotlib and pyplot

:exclamation: :exclamation: Since this section has numerous plots that I would prefer to be embedded in the markdown file, I am switching over to Jupyter notebook. Head on over to  [Matplotlib Jupyter notebook](../Matplotlib.ipynb)
