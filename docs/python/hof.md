# Higher Order Functions

## Digit Manipulation

### Treating Numbers as Strings of Digits
- While it's impractical, it's beneficial to practice iteration using this method.

### Retrieving Digits
- Utilize floor division and mod (by 10) to isolate individual digits.

## Understanding Functions

### Domain
- Refers to all possible inputs a function can accept.

### Range
- Refers to all possible outputs a function can produce.

### Behavior
- Describes the relationship between the function's inputs and outputs.

### Design
- Ensure that a function is assigned one specific task but has the flexibility to be applied in numerous related scenarios.
- Emphasize the "write once, use many times" philosophy.

## Generalization
- By designing functions to handle a broad range of scenarios, we can generalize our solutions, promoting code reusability.

## Higher Order Functions

### First-Class Nature of Functions
- In Python, functions are considered first-class, meaning they can be passed around like any other object (like a string, int, etc.)

### Characteristics of Higher Order Functions
- A function qualifies as "higher order" if it:
    1. Accepts another function as an argument.
    2. Returns a function as its result.

## Lambda Functions

### Introduction
- A lambda function is a succinct way to define a function, usually fitting within a single line.
- It's useful for quick, one-off operations where a full function definition might be overkill.

### Format
```
lambda <parameters>: <expression>
```

### Anonymity of Lambda
- Lambda expressions are anonymous, meaning they do not inherently have a name bound to them. They are often used for short-term operations where naming is not required.