### 0.3.1 / 2013-05-09

* `cd` into the root directory before running ruby. This will activate any
  `cd`/`PROMPT_COMMAND` hooks.
* Use `$PWD` instead of `readlink -f`, which is not supported on OSX.

### 0.3.0 / 2012-12-06

* `chgems` is now an executable. **Please remove the following:**
  * `/etc/profile.d/chgems.sh` symlink.
  * `. /usr/local/share/chgems/chgems.sh` from `~/.profile`, `~/.bashrc`
    or `~/.zshrc`.
* No longer override `$PS1`. This annoys users and does not work with [zsh].
* Print entering and exiting messages when spawning a sub-shell.
* Forgot to add the MIT license.

#### Makefile

* Fixed `make install` to run on FreeBSD / OpenBSD.
* No longer override `PREFIX`.

### 0.2.4 / 2012-11-19

* Updated the Makefile to be compatible with the [dash] shell.

### 0.2.3 / 2012-11-15

* Fixed a warning under [zsh] when `shift` is called and `chgems` was called
  without arguments.

### 0.2.2 / 2012-11-15

* Fixed `make install` to not automatically symlink chgems into
  `/etc/profile.d/`:
  * OS X does not have a `/etc/profile.d/`.
  * Give users the choice between global or local installation.
* Added a post-install message to the [homebrew] recipe.

### 0.2.1 / 2012-10-24

* Fixed `make install` to work on OS X.
* Added a [homebrew] recipe.

### 0.2.0 / 2012-10-16

* Install `chgems.sh` into `$PREFIX/share/chgems/`.
* Install a symlink to `chgems.sh` into `/etc/profile.d/`.

### 0.1.4 / 2012-10-14

* Preserve the current `$GEM_PATH` by calling `Gem.path`.

### 0.1.3 / 2012-10-07

* Added unit-tests using [shunit2](https://code.google.com/p/shunit2/).
* Added support for [zsh].
* Print errors to STDERR.
* Correctly pass environment variables to the sub-shell / command.
* Run commands in a sub-shell, otherwise exec a fresh `$SHELL`.
* Ensure the return value of the sub-shell / command is returned.

### 0.1.2 / 2012-10-05

* Check if the directory passed to `chgems` exists.
* Expand relative paths passed to `chgems` to absolute paths.
* Use `eval` instead of `env` to execute the command or sub-shell.
* `cd` into the directory before executing the command, then `cd` out.

### 0.1.1 / 2012-10-04

* Include `Gem.user_dir` and `Gem.default_dir` into `$GEM_PATH.

### 0.1.0 / 2012-10-04

* Initial release.

[dash]: http://gondor.apana.org.au/~herbert/dash/
[zsh]: http://www.zsh.org/

[homebrew]: http://mxcl.github.com/homebrew/
