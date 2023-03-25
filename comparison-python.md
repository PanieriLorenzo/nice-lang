# Comparison with python

## Argument passing semantics

Argument passing in Python is... weird. Python is pass-by-object, meaning that arguments are passed by reference, but upon assigning them to a variable,
they are copied. Except if the type is immutable, in which case it is always copied. To know what will happen to your arguments, you need to be familiar
with which types are mutable and which are not. This is annoying.

Python:
```python
a = "foo"
a += "bar"
# => "foobar"
# it mutates! (actually makes a copy)

b = [1, 2]
b += [3]
# => [1, 2 ,3]

def f(a):
  a += "baz"

f(a)
# => "foobar"
# what???

def g(b):
  b += [4]

g(b)
# => [1, 2, 3, 4]
```

NL:
```python
a = "foo"
a += "bar"
# => "foobar"

b = [1, 2]
b += [3]
# => [1, 2, 3]

fn f!(a):     # bang means that the function has side-effects
  a += "baz"
end

f!(a)
# => "foobarbaz"
# makes sense

fn g!(b):
  b += [4]
end

g!(b)
# => [1, 2, 3, 4]
# makes sense
```
