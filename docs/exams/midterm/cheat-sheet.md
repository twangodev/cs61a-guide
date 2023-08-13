# Midterm Cheat Sheet

## Names and Functions
Split Expression:
```python
a = 1
b = 2
a, b = b, a # Swaps values instantly
```

## Logical Operators

### `and`
1. Evaluate the left operand.
2. If the left operand evaluates to a falsy value, evaluate to the left operand.
3. Otherwise, evaluate to the right operand.

### `or`
1. Evaluate the left operand.
2. If the left operand evaluates to a truthy value, evaluate to the left operand.
3. Otherwise, evaluate to the right operand.

### `is`
Compares whether the variable location in memory is the same. In otherwise, it checks if it is the same instance 
of an object.

## Classes
### Inheritance
Use the `super()` to retrieve the parent class (or the class that the current class inherits from).

### Constructor
Use the `__init__(self, arg1, arg2, argN)` method to create a constructor for a class.

### `self`
When referencing the current instance, use `self.<name>`

### String Representation
#### `str`
The implementation of the `__str__` method is used when the `str(obj)` function is called on an object. This is used for
general purpose, including printing.

#### `repr`
The implementation of the `__repr__` method is used when the `repr(obj)` function is called on an object. This typically
represents a string that the computer interprets.

During a interactive session or when `eval(str)` is called, the `__repr__` method is used. 

## Lists
### List Functions
#### Appending
Use the `lst.append(item)` method to append (i.e add) an item to the end of the list.

???+ note "Equivalent to"
    Using the `lst.append(item)` method is equivalent to the following:

    ```python
    a = [1, 2, 3]
    x = 4
    
    a[len(a):] = [x]
    a = a + [x]
    a += [x]
    a.insert(len(a), x)
    ```

#### Extending
Use the `lst.extend(iterable)` method to extend the list with the items from the iterable. In other words, it appends
every item from the iterable to the end of the list.
This is equivalent to `lst[len(lst):] = iterable`.

#### Inserting
Use the `lst.insert(index, item)` to insert an item at the given index. This shifts the rest of the elments to the right.
You can think of it as `index` being the index of the item before which to insert.

```python
a = [1, 2, 3]
a.insert(0, 69)

print(a) # [69, 1, 2, 3]
```

#### Removing
Use the `lst.remove(item)` method to remove the first item from the list whose value is equal to `item`.

Use the `lst.pop([index])` method to remove the item at the given index. If no index is specified, it removes the last
item.

### List Comprehensions
Use the following syntax to create a list comprehension:
```python
[<expression> for <name> in <iterable> if <condition>]
```

### List Operations
#### Bracket Notation
To access a single item from a list with an index, use `lst[index]`.

To shallow copy a list, use `lst[:]`.

To shallow copy a slice of a list, use `lst[start:stop:step]`.

#### Addition
Use the `+` operator to concatenate two lists together. This creates a new list.

## Dictionaries
Keys must be immutable, as you cannot hash a mutable object while tracking its changes.

### Dictionary Functions
#### Get
Use `dict.get(key, default)` to get the value of the key. If the key does not exist, it returns the default value.
#### Keys
Use `dict.keys()` to get a list of the keys in the dictionary.
#### Values
Use `dict.values()` to get a list of the values in the dictionary.
#### Items
Use `dict.items()` to get a list of the key-value pairs in the dictionary. This is a list of tuples.

## Control
### Pure Functions
A pure function will only return values, such as `abs(x)` and `pow(b, e)`
Non-pure functions will have side effects, including but not limited to environment changes and prints.

### Life Cycle of User-Defined Functions
#### Definition
The operator is the name that binds to a function. The operands are evaluated.
The respective function is then called on its parameters.

#### Call and Application
1. Create a new frame
2. Parameters are bound to the arguments
3. Execute the body of the function

### Inheritance throughout Frames
The global frame is the initial frame where the program starts. It is the parent of all other frames. 
When search for names, first look within the local frame, its parent(s), then finally global frames.

## Execution Rules

### Function Definition Statements
1. Create a new function value with the intrinsic name
2. Parent is assigned to the current working frame
3. Bind the name of the function to the funciton object within the current working frame

### Assignment Statements
1. Evaluate the expression(s) that are being assigned to the name (i.e. the right side)
2. Bind the names on the left to the evaluated values in the current working frame

### Conditional Statements
1. Evaluate the header's expression
2. If the expressions evaluates to a truthy value, execute the suite, and skip the `elif` and `else` clauses
3. Otherwise, evaluate the next `elif` clause, until you reach the `else` clause.

### While Statements
1. If the condition specific in the header evaluates to a truthy value, execute the suite, and repeat the process.
2. When the condition evaluates to a false, exit the while loop. (i.e. do not execute the suite)

## Python Unique Features
### Division
The `/` operator will always return a float, even if the result is a whole number.
Use the `//` operator to perform floor division. This will return the quotient of the division, rounded down to the nearest integer.

### `None`
`None` is a special value that represents nothing, similar to `null` in other languages.

### Multiple Return Values
You can return multiple values from a function by encapsulating them in a tuple.

### Boolean Context
In Python, the following values are considered falsy:
- `False`
- `None`
- `0`
- `""`
- `[]`
- `()`
- `{}`
Truthy values are everything else.

## Recursion

### Recursive Steps
#### Identify the base case(s)
Think about the simplest and smallest possible inputs to your function, such that you know the answer immediately.

#### Recursive Leap of Faith
Call your function on a smaller input, assuming that it works correctly.

#### Recombination
Build up the answer to the original problem using the previous result

### Recursion Examples
#### Summation
In this example, we return the sum of numbers through n (including n) with term applied to each number
```python
def summation(n, term): # n must be >= 1
    # 
    if n == 1:
        return term(n)
    return term(n) + summation(n - 1, term)
```
#### Number of Eights
```python
def num_eights(pos):
    if pos % 10 == 8:
        return 1 + num_eights(pos // 10)
    elif pos < 10:
        return 0
    return num_eights(pos // 10)
```
### Tree Recursion Example
#### Counting Coins
In this example, we want to return the number of ways to make change using coins of value 1, 5, 10, 25.
```python
def get_smaller_coin(_):
    return None # Implementation not shown

def count_coins(change):
    def helper(amount, parent_coin):
        if amount == 0:
            return 1
        if amount < 0:
            return 0

        smaller_coin = get_smaller_coin(parent_coin)
        if smaller_coin is None:
            return 1
        return helper(amount - parent_coin, parent_coin) + helper(amount, smaller_coin)
    return helper(change, 25)
```

## Environment Diagrams
Environment diagrams will always begin a global frame, which is the parent of all other frames.

Primitive values are stored within the table, all other objects are referenced with pointers.

### Syntax
#### Frame Header
The syntax from the frame header is as follows:
```
f<frame number>: <origin> [parent=<parent>]
```

- `<frame number>` is the number of the frame, starting from 0
- `<origin>` is the origin of the frame, which is either `global` or `function`
- `<parent>` is the parent of the frame, which is the frame number of the parent

#### Function Syntax
The syntax for a function is as follows:
```
func<intrinsics name>(<parameters>) [parent=<parent>]
```

- `<intrinsics name>` is the name of the function
- `<parameters>` is the list of parameters, separated by commas
- `<parent>` is the parent of the frame, which is the frame number of the parent

