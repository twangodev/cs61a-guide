# Environments

## Environment Diagrams

- Environment diagrams serve as tools to conceptually understand the functioning of programs. This understanding facilitates the prediction of program behavior, especially during:
    - **Debugging**: Aids in identifying issues and understanding code flow.

## Frames

### Introduction to Frames

- **User-Defined Functions**: Creating user-defined functions will result in the generation of frames.
- **Builtin Functions**: Contrarily, built-in functions do not generate frames.
- **Global Frame**: This is the starting frame and is unique because it does not correspond to any specific call expression or function.

### Parent Frames

1. **Definition**: The parent of a function is identified as the frame where the function was initially defined.
2. **Variable Lookup**:
    - Begin the lookup in the current frame.
    - If the variable isn't present, move to the parent frame, then its parent, and so on, until the global frame.
    - If the variable still remains undiscovered across all frames, Python raises a `NameError`.

## Functions

### Function Definition

1. When a function is defined, the function's value gets bound to its name, represented as:

```
func <name>(<formal parameters>) [parent=<frame>]
```


### Function Application

1. Initiate by adding a local frame, labeled with the name of the function being executed.
2. Clone the parent of the function into the local frame, denoted as `[parent=<label>]`.
3. Bind the function's formal parameters to the respective arguments within the local frame.
4. Proceed to execute the function's body within the environment that originates from this local frame.

### Functions as Arguments

- When referencing higher-order functions that have functions as arguments, it's pivotal to note that they attach to the parent frame, not the impending local frame.

## Currying

- **Definition**: Currying transforms a function accepting multiple arguments into a function that takes just a single argument. This resultant function becomes a higher-order function, which further returns functions to process the remaining arguments.

