
# Getting help 
- `help(function name)` The help function is very handy if all you need is minor clarification on how a specific method works.
- `type()` is equivalent to class function in R
- to determine the methods available to you based on the object type
  - dir function with object name or type as input  e.g. `dir(str)` will give you a list of attributes available
  - To get additional help on the attributes: `str.replace?`

# Basics
- lists
  - Declaration: `x = [2,44,6,8]`
  - list operations: 
     - Add object: `listName.append()`
     - Concatanate two lists: `listName1 + listName2`
     - Reverse the order: `listName.reverse()`
     - Sort: `listName.sort()` <- *in-place* method Vs Sorted: `newListName = sorted(oldListName)` <- create a new sorted list
     - Count number of objects in list: `len(listName)`
     - NOTE: list operations (except `sorted`) are *in-place* methods i.e. they won't return any values, but modify original list in-place
  - list comprehension : 
    - to calculate square of numbers in a list e.g. `numbers = range(10)`
    Long way -- for loop
    ```python
      for number in numbers:
        square = number ** 2;
        squares.append(square)
    ```
    Short efficient way -- list comprehension
    
    `squares = [numbers**2 for number in numbers]`
    - sum the odd numbers from 0 through 9
      `sum([i for i in range(10) if i%2 == 0 ])`
    
    - Create dictionary
      `d = {key: value for (key, value) in iterable}`
    
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
  - extremely useful for set operations (**note** these return lists)
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
    - From a list of keys and values
    
```python
cluster_colors = ["red", "orange", "green", "blue", "purple", "gray"]
regions = ["Speyside", "Highlands", "Lowlands", "Islands", "Campbelltown", "Islay"]
region_colors = dict(zip(regions, cluster_colors))

```
  - operations
    - Derive value of a key: `age["ram"]`
    - increment value of a key: `age["ram"] += 1`
    - get list of keys or values: `age.keys()` ; `age.values()` <- the returned values here is 'view' object which is updated as you modify the original dictionary
    - determine object membership i.e. if a certain key is in the dictionary: `"ram" in age`
    - you can loop through keys. `for name in age:` or `for name in age.keys():` or if you want to parse in sorted manner `for name in sorted(age.keys()):` or `for name in sorted(age.keys(), reverse = True):`
    - 
```python
    s = 'A - 13, B - 14, C - 29, M - 99'
    mydict = dict((k.strip(), v.strip()) for k,v in 
                  (item.split('-') for item in s.split(',')))

    #It does 3 things:

     #   split the string into "<key> - <value>" parts: s.split(',')
     #   split each part into "<key> ", " <value>" pairs: item.split('-')
     #   remove the whitespace from each pair: (k.strip(), v.strip())

```

```python
  string = "abc=123,xyz=456"
  dict(x.split('=') for x in string.split(','))`
```  
```python
sentence = 'Jim quickly realized that the beautiful gowns are expensive'
 #  Create a dictionary count_letters with keys consisting of each unique letter in the sentence and values consisting of the number of times each letter is used in this sentence. Count upper case and lower case letters separately in the dictionary.

count_letters = {}
for letter in sentence:
    if(letter != ' '):
        count_letters[letter] = count_letters.get(letter, 0) + 1
#print(count_letters) 
```

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
  
## Reading and writing files
- Reading
  ```python
    filename = "read.txt"
    for line in open(filename):
      print(line)
      line = line.rstrip() # this removes the \n at the end of each line and returns a string. And since strings are immutable, have to reassign
      print(line)
      line = line.rstrip().split(" ") # will split the \n stripped string by " " and return a list 
      print(line)
  ```
 - Writing

  ```python
      F = open("output.txt","w") # open a file with 'write' handle
      F.write("Python\n") # write something. Note that new line is specified
      F.close() # close file
  ```
  
  ```python
      F = open("input.txt", "w")
      F.write("Hello\nWorld")
      F.close()
      lines = []
      for line in open("input.txt"):
          lines.append(line.strip())
      print(lines) 
  ```
 
**Functions**

- maximise code resuse and minimize redundancy by procedural decomposition

```python
  def add(a,b):
    mysum = a+b
    return mysum
 
 add(12,5)
```

```python

  def sum_and_sub(a,b):
    mysum = a+b
    mydiff = a - b
    return(mysum, mydiff) # return tuple
```

```python
  def intersect(s1,s2):
    res = [] 
    for x in s1:
      if x in s2:
        res.append(x)
    return res
```
**Note** Difference between `random.choice(list)` vs `random.uniform(a,b)`
```python
    import random
    def password(length):
      pw = str()
      characters = "oiehowhig"
      for i in range(length):
        pw = pw + random.choice(characters) # pw += random.choice(characters) will work too
      return(pw)
```

```python
   def factorial(n):
   if n == 0:
     return 1
   else:
     N = 1
     for i in range(1, n+1):
       N *= i
     return(N) 
```
```python
sentence = 'Jim quickly realized that the beautiful gowns are expensive'

def counter(input_string):
    my_dict = {}
    for letter in input_string:
        if(letter != ' '):
            my_dict[letter] = my_dict.get(letter, 0) + 1
    return(my_dict)

address_count = counter(sentence)
most_frequent_letter = ([letter for letter in address_count.keys() if address_count[letter] == max(address_count.values())])
most_frequent_letter = most_frequent_letter[0]
print(most_frequent_letter)

```
**Homework** 
3a: A list of numbers can be very unsmooth, meaning very high numbers can be right next to very low numbers. This list may represent a smooth path in reality that is masked with random noise (for example, satellite trajectories with inaccurate transmission). One way to smooth the values in the list is to replace each value with the average of each value's neighbors, including the value itself.
Instructions: 
    Write a function `moving_window_average(x, n_neighbors)` that takes a list `x` and the number of neighbors `n_neighbors` on either side of a given member of the list to consider.
    For each value in x, `moving_window_average(x, n_neighbors)` computes the average of that value's neighbors, where neighbors includes the value itself.
    `moving_window_average` should return a list of averaged values that is the same length as the original list.
    If there are not enough neighbors (for cases near the edge), substitute the original value as many times as there are missing neighbors.
    Use your function to find the moving window sum of `x=[0,10,5,3,1,5]` and `n_neighbors=1`.
 
```python
import random
random.seed(1)

def moving_window_average(x, n_neighbors=1):
    n = len(x)
    width = n_neighbors*2 + 1 # denominator to cal avg - neighbours including the number itself - in this case = 3
    x = [x[0]]*n_neighbors + x + [x[-1]]*n_neighbors # If there are not enough neighbors (for cases near the edge), substitute the original value as many times as there are missing neighbors. In this case : [0, 0, 10, 5, 3, 1, 5, 5]
    outlist = []
    for idx, item in enumerate(x[1:]):
       # print(idx, item)
        if idx > 0:
            outlist.append((x[idx-1] + x[idx] + x[idx+1])/width)
    return(outlist)
    
x=[0,10,5,3,1,5]
print(moving_window_average(x, 1))
# worked out (on paper) answer = [3.333, 5.0, 6.0, 3.0, 3.0, 3.666]
```
3b:
- Compute and store `R=1000` random values from 0-1 as `x`.
- `moving_window_average(x, n_neighbors)` is pre-loaded into memory from 3a. Compute the moving window average for `x` for values of `n_neighbors` ranging from 1 to 9 inclusive.
- Store `x` as well as each of these averages as consecutive lists in a list called `Y`.

```python
import random

random.seed(1) # This line fixes the value called by your function,
               # and is used for answer-checking.
    
R = 1000
x = []
for n in range(R):
    ele = random.uniform(0,1) 
    x.append(ele)
Y = []
Y.append(x)
for i in range(1,10):
    mavg = moving_window_average(x,n_neighbors=i)
    Y.append(mavg)
```
3c: 

- `moving_window_average(x, n_neighbors=2)` and `Y` are already loaded into memory. For each list in `Y`, calculate and store the range (the maximum minus the minimum) in a new list `ranges`.
- Print your answer. As the window width increases, does the range of each list increase or decrease? Why do you think that is?

```python
ranges = []
# long loop way below
#for lst in Y:
#    ranges = (max(lst) - min(lst))
#    print(ranges)
ranges = [(max(lst) - min(lst)) for lst in Y] # list comprehension to the rescue !
print(ranges)
# The range decreases, because the average smooths a larger number of neighbors. Because the numbers in the original list are just random, we expect the average of many of them to be roughly 1 / 2, and more averaging means more smoothness in this value. 
```

