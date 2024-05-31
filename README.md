# Aliases & Functions in Bash and Zsh

## Aliases or Functions ?

An alias is nothing more than text substitution, if all you need is to shorten a command down to a few characters, an alias is probably what you're looking for.  
If you need to shorten multiple commands or handle multiple arguments, you're more than likely going to want a function to handle this properly (and optionally add some logic on top).

## Linux (default shell: Bash)

The (default) bash configuration file resides in "$HOME/.bashrc", inside of this file will be our bash configuration with our aliases and/or functions.

- An **alias** is written like so:

  ```bash
  alias 'lsa'='ls -a'
  ```

  Here, `lsa` is the name we give to our alias, while `ls -a` is the command we want to run when we execute it. The equal sign assigns the command(s) on the right to the name on the left.

  > _There's not much more to it than that !_

<br>

- **Functions** are where the fun begins:

  ```bash
  function gac() {
      git add "$1"
      git commit -m "$2"
  }
  ```

  Our function begins with the keyword of the same name (`function`) and the main body resides inside of curly braces (`{}`)

  > _Sounds familiar..._

  Each successive command is separated by a newline to separate them, and arguments are surrounded by double quotes (`"`) followed by `$` and the number of the argument.

## MacOS (default shell: Zsh)

The config file is also (by default) at the root of our user (`~`), if it doesn't already exist you can create it with `touch ~/.zshrc`.

- **Aliases** work practically the same in zsh with a minor difference, the name of the alias is not surrounded by quotes:

  ```bash // 'zsh' doesn't have syntax highlighting
  alias rmfr="rm -f -r"
  ```

- **Functions** work "mostly" the same, but you don't need the `function` keyword and you have access to an argument array (among other things):

  ```javascript // same as above
  del() {
      rm -f $*
  }
  ```

## Git Bash on Windows

Same as Linux; if it doesn't already exist, create `%USER%\.bashrc` and put your config inside.

For aliases in Powershell check the [documentation](https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_aliases)
