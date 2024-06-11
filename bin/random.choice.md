```python
#!/usr/bin/python3
"""
Usage: random.choice <arg>...
Output a randomly chosen argument

Examples:

    choose a fruit:

        $ random.choice apple banana orange
        banana
        $ random.choice apple banana orange
        apple

    choose a random integer from [1;10]:

        $ random.choice {1..10}
        7

        $ seq 1 10 | xargs random.choice
        6

    Note, `xargs random.choice` is similar to `shuf -n 1`. The latter must be
    more efficient on large stdin.
"""
import os
import random
import sys


self, *args = sys.argv
if not args:
    print(os.path.basename(self), "what?", file=sys.stderr)
    sys.exit(1)

print(random.choice(args))
```
