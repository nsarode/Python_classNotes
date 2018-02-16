
**Getting help**
- `help(function name)` The help function is very handy if all you need is minor clarification on how a specific method works.
- `type()` is equivalent to class function in R
- to determine the methods available to you based on the object type
  - dir function with object name or type as input  

**Basics**
- lists
  - Declaration: `x = [2,44,6,8]`
  - list operations: 
     - Add object: `listName.append()`
     - Concatanate two lists: `listName1 + listName2`
     - Reverse the order: `listName.reverse()`
     - Sort: `listName.sort()` <- *in-place* method Vs Sorted: `newListName = sorted(oldListName)` <- create a new sorted list
     - Count number of objects in list: `len(listName)`
     - NOTE: list operations (except `sorted`) are *in-place* methods i.e. they won't return any values, but modify original list in-place
- tuples
  - Declaration: `x = (1,2,3,4)`
  - tuple operations
    - Concatanation`x + (3,4,7)`
    - Length/count of objects: `len(x)`
    - packing : adding objects to a tuple e.g. `x = 23`; `y = 38`; `packedTuple = (x,y)`
    - unpacking : `(a,b) = packedTuple`
    - for loop: if I have a list of tuples 
      
          ```python
          
          coordinates = [(23,45),(32,65),(47,44)]
          for (x,y) in coordinates:
            print(x,y)
          
          ```
**Methods, functions, attributes, objects**
- Methods are functions associated with objects, whereas data attributes are data associated with objects. correct 
  - Function (a method) always ends with () e.g. `x= np.array([1,2,3])`; Function mean will be written as `x.mean()` 
Attribute doesn't end with () e.g. `x.shape`
- Types of objects
  - immutable objects : strings and tuples
  - mutable objects : dictionaries and lists
- Importing libraries/modules
  - `import numpy as np`<- saves typing
  - `from math import pi` <- no need to import the whole module, just the parts you need
  
 **Numbers & basic calculations**
  - Numbers
    - integers
    - floating point : number with decimal
    - complex numbers
  - basic calculations or operations
    - `//` integer division or floor division rounds down the answer to the closest integer e.g. `15//7 = 2`
  - _ stores the value of the last operation : this is pretty handy if you want to do operations on the fly with the current answer
  - expressions and boolean
    - boolean types i.e. `True` or `False`, SHOULD be capitalized
    - boolean operations : `and`, `or`, `not`
  
 **Sequences**
  - Lists, tuples, "range objects"
  - These all support commond sequence operations, but also have methods of their own for specific operations
  - for specific unit access indexing starts at: from left:  0 ; from right: -1
  - slicing using `listName[start:end]` <- end not inclusive
  - lists do not necessarily need to be composed of objects of the same type, though it is common practice
  
