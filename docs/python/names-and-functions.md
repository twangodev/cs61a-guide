# Names and Functions

## Values

### Primitive Data Types
Integers, Strings, Floats, Booleans
Expressions evaluate to values

## Names
Assigning values to names, otherwise known as variables (can also represent functions)

### Assignment Statements
The statement which defines the variable

!!! tip
    Python does not evaluate assignment statements (nothing is returned when you assign a variable)

Variables assigned in Python are inherently mutable (that does not mean the object is mutable)
### Split Expressions

```python
a = 1
b = 2
a, b = b, a # Operation happens instantly: The values for a and b are swapped 
```

## Environment Diagram
Allows for the tracking of value of variables on a per-frame basis, however will typically show the final state of the program
Environment diagrams allow you to track the value of variables and abstract away sequences of computation

## Functions
A sequence of code that performs a specific task and can be reused easily.

### Inputs and Outputs
- Inputs are known as arguments
- Outputs are known as return values

### Function Creation
- Functions can be created with the `def` statement
- Indents are required to give scope, give body, etc.

### Anatomy
#### Function signature
Indicates name and number of arguments
#### Function Body
Defines the computation performed when the function is applied

### Default Return
Default return type is `None` (equivalent to `null`).

### Environment Diagram Scopes
Environment Diagram has different frames (or scopes).

### Calling user-defined functions
1. Retrieve intrinsic name (i.e. the real name, or the real function, as function names can be reassigned)
2. Bind function parameters to arguments within the frame
3. Execute the body with the environment