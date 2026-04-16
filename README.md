# Resources

- https://linuxize.com/series/bash-scripting-fundamentals/
- https://linuxize.com/cheatsheet/bash/

# Intro

Bash is the default shell on most Linux distributions.  
Learning to write Bash scripts is an essential skill for anyone working with Linux systems, which includes DevOps engineers.  

# Bash Shebang Explained (part 1 of 39)

You might have noticed that the first line in any script starts with the `#!` characters and the path to the Bash interpreter.  

This sequence of characters (`#!`) is called the **shebang** and is used to tell the OS which interpreter to use to parse the rest of the file.  

The **interpreter** is the full path to a binary file (ex: /bin/sh, /bin/bash).  

**Examples**:
- `#!/bin/bash` - Uses bash to parse the file.
- `#!/usr/bin/env perl` - Uses the env command to find the path to the perl executable.
- `#!/usr/bin/env python3` - Executes the file using the python3 binary.

