# f2py example

This is [some fortran code](https://github.com/numpy/numpy/blob/f8585390699704d820ceeca2ab0f8c96c500022e/numpy/f2py/tests/src/string/char.f90#L4) from the f2py tests.

Build with:

```bash
f2py -c char.f90 -m char
```

Regenerate the c bindings already in the repo using:

```bash
f2py char.f90 -m char
```

And here's a short example of using the module, stolen from the f2py tests:

```python
import char
import numpy as np

strings = np.array(["ab", "cd", "ef"], dtype="c").T
inp, out = char.char_test.change_strings(
            strings, strings.shape[1])
print(strings)
print(inp)
print(out)
```
