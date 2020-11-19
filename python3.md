## help function

# display objects/modules

```python
dir()
```

# display functions and types from the builtins module

```python
dir(__builtins__)
```

# display the help for a function from the builtins module.
# functions with params inside brackets [] are optional
# -> indicates the return type

```python
help(pow)

Help on built-in function pow in module __builtin__:

pow(...)
    pow(x, y[, z]) -> number
    
    With two arguments, equivalent to x**y.  With three arguments,
    equivalent to (x**y) % z, but may be more efficient (e.g. for longs).
```

# list all modules

```python
help('modules')
```

## returns the number of vowels in string

```python
def getCount(inputStr):
    return sum(1 for let in inputStr if let in "aeiouAEIOU")
```

## remove characters from string

```python
def disemvowel(string):
    return "".join(c for c in string if c not in "aeiouAEIOU")

disemvowel("hello world")
```

## return true if pin is 4/6 characters and is digits only

```python
def validate_pin(pin):
    return len(pin) in (4, 6) and pin.isdigit()
```

## returns number of digits, excluding anything containing "5". 1st and last digits inclusive

```python
#using arrays not optimal
def dont_give_me_five(start,end):
    return len([n for n in range(start,end+1) if "5" not in str(n)])

#better option
def dont_give_me_five(start, end):
    return sum('5' not in str(i) for i in range(start, end + 1))
```