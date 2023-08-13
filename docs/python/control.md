# Lecture 3: Control

## Pure Functions vs Non-Pure Functions

### Pure Functions
- Functions that only return values.

???+ example
    An example of a pure function is `abs(x)` and `pow(b, e)`.


### Non-Pure Functions
- Functions that have side effects.
???+ example
    An example of a non-pure function is `print()`, which displays output and returns `None`.

## Life Cycle of a User Defined Function

### Definition Lifecycle
1. A new function is created.
2. A name is bound to the function within the current frame.

### Call Expression Lifecycle
1. Operator and operands evaluate.
2. Function called on arguments.

### Calling and Applying Lifecycle
1. A new frame is created.
2. Parameters bound to arguments.
3. Body is executed in that new environment.

### Naming Frames
- Frames are named with the $fN$ format, where $N$ is the frame identifier (ID).

### Environment & Frames
- Environment is a sequence of frames.
    1. Global frame is the initial frame.
    2. Search for variables/names starts from the local frame, to parent, then n parent, and continues all the way to the global frame.

## Miscellaneous Python Features

### Infix Functions
- A Kotlin reference to using symbols to "call" functions.

### Division
1. Regular division will lead to floats.
2. Floor division (`//`) will round down regardless.
    - Floor division by 10 will truncate the last number.
3. Modulo (`%`) will provide the remainder.
    - Opposite of floor division: when you modulo by 10, it gives you the last number.
4. Using floor and modulo results in answers in the format *x* remainder *y*.

### Multiple Return Values
- Utilize tuples for returning multiple values.

### Docstrings/Tests
- Use triple quotes, similar to `kdoc` in Kotlin.
- Doc tests provide an interpreter allowing you to write expected outputs.
    - Use `>>>` to show input, then present the expected output on the subsequent line.

### Default Arguments

## Statements
- These are executed by the interpreter to perform a specific action.

### Statement Headers
1. The header determines the statement's type.
2. Controls the subsequent suite.
3. Suites are sequences of statements.
4. Suites execute from top to bottom unless directed otherwise.

### Execution Rule of If-Statements
1. Evaluate the header expression.
    - If true, execute the suite and skip the subsequent clauses.

## Boolean Context
### False Values
- Examples: `False`, `0`, `""`, `None`, etc.

### Truth Values
- Basically, any other value not listed as a False value.

## While Statements
1. If the condition evaluates to true, the suite is executed, and then the condition is checked again.
2. If the condition is false, the loop exits.

