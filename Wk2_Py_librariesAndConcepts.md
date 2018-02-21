**Scope rules**

- LEGB :  **L**ocal **E**nclosing function **G**lobal **B**uilt-in
- **name error exception** often is raised if Python cannot find an object with the name provided

**Class**
To remove elements of a list, you can use remove function. **Note** if multiple occurences of an element exists, only the first occurance is removed

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

# Function vs Class
Source: [Python Function versus Class: what is the difference between using either methods?](https://www.quora.com/Python-

Function-versus-Class-what-is-the-difference-between-using-either-methods)
Functions are easier to work with and understand than objects. However, one of the key benefits of classes is that they allow _inheritance_. This means you can create a superclass then make subclasses of it that are more specific.
