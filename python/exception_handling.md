# Exception handling

## Assertion errors

Use assertion errors to ensure that variables contain appropriate values.

``` python
x = 5
assert x < 5
```

Output:
```
Traceback (most recent call last):
  File "main.py", line 2, in <module>
    assert x < 5
AssertionError
```

You can modify the text that is printed with an `AssertionError`. Hat tip to [this Stack Overflow](https://stackoverflow.com/questions/3807694/how-to-change-the-message-in-a-python-assertionerror) answer.

``` python
x = 5
assert x < 5, 'x is not less than five.'
```

Output:
```
Traceback (most recent call last):
  File "main.py", line 2, in <module>
    assert x < 5, 'x is not less than five.'
AssertionError: x is not less than five.
```
