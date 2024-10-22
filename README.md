## What ?

A simple Bash-Compatible script that turns off history and tracks exported variables so these are unset when exiting `incognito`

## Why ?

Sometimes when dealing with API Token and sensitive information, I like to turn off history. 
This script will help achieve that in a better way, while also supporting `private export`

## How ?

 - This script needs to be sourced to work correctly. So after installation you can use `source incognito`.
 Configure an alias for it so it is less typing and more doing.

```bash
user@hostname $ chmod +x setup.sh
user@hostname $ ./setup.sh --prefix=/home/user/scripts
user@hostname $ echo 'alias incognito="source incognito"' >> $HOME/.bash_aliases
user@hostname $ incognito
```

 - You can use the export command with the `nonprivate` argument so the variable is retained upon deactivation

```bash
(incognito) user@hostname $ export SECRET="Password12345" nonprivate
```

 - When you are done with the shell, simply use `deactivate` which will exit `incognito` and clear exported variables

```bash
(incognito) user@hostname $ deactivate
```

## Installation

**Installation in /usr/local/bin by default**

```bash
user@hostname $ ./setup.sh 
```

**Installation in another specified directory**

```bash
user@hostname $ ./setup.sh --prefix=/home/user/scripts/incognito
```

You're welcome!