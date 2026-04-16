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

There are 2 ways to set the interpreter:
- using the absolute path to the targeted binary: `#!/bin/bash`
- using the `env` utility to find the specified binary: `#!/usr/bin/env bash`

The advantage of the second approach is that it searches for the executable in the user's `$PATH` environment variable, which makes scripts more portable across systems 
where Bash may not be installed at `/bin/bash` (such as FreeBSD or NixOS).

## Passing options to the interpreter

When using the absolute path, you can pass options directly to the interpreter. For example, to run the script in debug mode:
```bash
#!/bin/bash -x
```

When using `env`, you cannot pass options on the shebang line, instead use `set` inside the script:
```bash
#!/usr/bin/env bash
set -x
```

## `#!/bin/sh` vs `#!/bin/bash`

- Use `#!/bin/sh` when your script only uses POSIX-compliant syntax and you want maximum portability
- Use `#!/bin/bash` when your script relies on Bash-specific features

## First script

- create a new file and edit it via your favorite text editor (mine is Vim): `vim hello_world`
- add the following content to it:
```bash
#!/bin/bash

echo "Hello World"
```
- write and quit

To be able to run the script without specifying the interpreter from the command line, you need to make the file executable:  
```bash
chmod +x hello_world
```

- Now you can run the script by typing `./` followed by the file name:
```bash
./hello_world
```

## Overriding the shebang

If, for some reason, you want to override the interpreter set in the shebang line, run the script by explicitly specifying the desired shell.  
For example, to run a script using bash no matter which shell is specified in the shebang line:
```bash
bash hello_world
```
>[!warning]  
>Note that overriding the shell interpreter is not recommended, as it may lead to unexpected behavior.
>But it might be useful to not be constantly switching between your usual shell and the one specified in the shebang line.

# How to run a Bash script in Linux (part 2 of 39)

