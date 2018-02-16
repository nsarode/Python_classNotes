
**Getting help**
- `help(function name)` The help function is very handy if all you need is minor clarification on how a specific method works.
- `type()` is equivalent to class function in R
- to determine the methods available to you based on the object type
  - dir function with object name or type as input  e.g. `dir(str)` will give you a list of attributes available
  - To get additional help on the attributes: `str.replace?`

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
  - Declaration: `x = (1,2,3,4)` or `x = (2,)` <- if you want to declare a tuple with a single object. `x = (2)` will be      identified as integer.
  - tuple operations
    - append : not possible, tuples are *immutable*
    - Concatanation`x + (3,4,7)`
    - Length/count number of objects: `len(x)`
    - count number of times an object repeats: `x=(1,4,2,3,4)`; To determine the number of times 4 is repeated `x.count(4)`
    - sum of all objects within tuple: `sum(x)`
    - packing : adding objects to a tuple e.g. `x = 23`; `y = 38`; `packedTuple = (x,y)`
    - unpacking : `(a,b) = packedTuple`
    - for loop: if I have a list of tuples 
      
          ```python
          
          coordinates = [(23,45),(32,65),(47,44)]
          for (x,y) in coordinates:
            print(x,y)
          
          ```
- ranges : immutable *sequence* of integers
  - Declaration: `range(startingValue,stoppingValue, stepSize)` ; e.g. `range(4)` <- startingValue & step size optional. stoppingValue *non-inclusive* 
  - To view the declared range: `list(range(4))` <- not recommended to convert to list, use as-is to save memory
- strings : immutable *sequence* of characters
  - declaration: `S = "Python"` or `S = 'Python'` or `S = '''Python'''`
  - case sensitive
  - all sequence operations can be performed on them (see **sequences** below)
  - membership tests: `"y" in S` <- answer should be `True`
  - polymorphism: `+` = concatanation; `*` = addition 
  - explicitly turn number into a string: `str(4)` e.g. "four equals" + str(4)
  - replace elements: `name = "Tina Fey"`; `new_name= name.replace("T","t")` <- Note: since strings are immutable, we had to declare a new variable name to direct the output of replace to
  - split : `names = name.split(" ")` <- give character that you want to use to split the string. this should give you a string with two objects "Tina" and "Fey"
  - change case of specific object within string: `names[0].upper()` ; `names[0].lower()`

- Sets : unordered collection of distinct hashable objects
  - CANNOT be : indexed, contain repeat objects (if you try to add a repeat element, nothing happens)
  - two types : set <- mutable and frozen set <- immutable
  - declaration: Empty set : `id = set()`; set with numbers: `id = set([1,2,3,4,7,8,9])`
  - add element: `id.add(5)`
  - extremely useful for set operations 
    - `male = set([3,5])` ; `female = id - male`
    - union operation: `everyone = male | female`
    - interserct: `everyone & set([2,4])`
    - e.g. word = "ghewihtqgjhowbhgwoingoe"; To do operations on this string, we could convert this into set. 
      `letters = set(word)`
      `len(letters)` <- will give list of unique alphabets (remember that set will keep only unique letters)
- Dictionaries (equivalent to Perl Hashes)
  - unordered key value pairs where keys are immutable
  - declaration: 
    - Empty dictionaries: `age = {}` or `age = dict()`
    - with data: `age = {"ram":24, "sita":22, "laxman": 19, "ravan":35}`
  - operations
    - Derive value of a key: `age["ram"]`
    - increment value of a key: `age["ram"] += 1`
    - get list of keys or values: `age.keys()` ; `age.values()` <- the returned values here is 'view' object which is updated as you modify the original dictionary
    - determine object membership i.e. if a certain key is in the dictionary: `"ram" in age`
    - you can loop through keys. `for name in age:` or `for name in age.keys():` or if you want to parse in sorter manner `for name in sorted(age.keys()):` or `for name in sorted(age.keys(), reverse = True):`
- `newList = list(oldeList)` or `newList = oldeList[:]` <- two ways of creating copies without both of them referring to the same object
- the following code will return 3
  ```
    x=3
    y=x
    y=y-1 
    x
  ```
- the following code will return [24,3,4]
  ```
    L1 = [2,3,4]
    L2 = L1
    L2[0] = 24 
    L1 
  ```
  
**Sequences**
  - Lists, tuples, "range objects"
  - These all support commond sequence operations, but also have methods of their own for specific operations
  - for specific unit access indexing starts at: from left:  0 ; from right: -1
  - slicing using `listName[start:end]` <- end not inclusive
  - lists do not necessarily need to be composed of objects of the same type, though it is common practice
 
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
  


