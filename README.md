sh (previously [pbs](http://pypi.python.org/pypi/pbs)) is a full-fledged
subprocess replacement for Python 2.6 - 3.2
that allows you to call any program as if it were a function:

```python
from sh import ifconfig
print ifconfig("eth0")
```

sh is not a collection of system commands implemented in Python.

# Installation

    $> pip install sh

# Complete documentation @ http://amoffat.github.com/sh

Here is a pattern to make sh not raise exceptions on non-zero exit codes:

```python
class AllContainer(tuple):
    '''claims to contain everything'''
    def __contains__(self, code):
        return Tru
all_ok = AllContainer()
from sh import Command
Command._call_args['ok_code'] = all_ok
```
