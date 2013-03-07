# modman (Module Manager)

Developing extensions for software that doesn't allow you to separate your
files from core files, and keeping that extension under version control and
making it easy to deploy is now much, much easier. Development of this script
was inspired by Magento which forces you to mix your extension files all
throughout the core code directories. With modman, you can specify in a text
file where you want your directories and files to be mapped to, and it will
maintain symlinks for you so that your code is easy to hack and deploy.

All of your cloned/checked-out modules will be kept in a directory named
`.modman` in the location where you run `modman init`.

## Requirements

  * Linux/Unix or OSX (not cygwin)
  * bash
  * Common utilities available in your PATH: grep (POSIX), find, ln, cp, basename, dirname
  * Web server must follow symlinks
  * git and/or subversion are optional (not required for "deploy" command)
  * For Magento, if using template files in a modman module, you must enable "Allow Symlinks" (found under System > Configuration > Advanced > Developer)
  
![Allow Symlinks](https://f.cloud.github.com/assets/1337461/43324/820d4d96-567f-11e2-947a-167bf76db33f.png)
  
*NOTE:* There is no additional security risk to allowing symlinks, despite the warning which says otherwise...

## Installation

```
bash < <(wget -O - https://raw.github.com/colinmollenhour/modman/master/modman-installer)
```

or

```
bash < <(curl -s https://raw.github.com/colinmollenhour/modman/master/modman-installer)
```

```
source ~/.profile
```

Note: modman is simply a bash script, so to use it you just need to place it in your $PATH
and change it's mode to executable.

## Getting Started

Run `modman --help` to get the basic usage summary or `modman --tutorial` to
see a brief tutorial. For more in-depth information please see the
[Modman Wiki](https://github.com/colinmollenhour/modman/wiki)

## Version Control Systems

Modman currently supports subversion and git. Other VCSs could be used by
manually checking out the source code into the proper directory and using
the "deploy" command.

## Author

* Colin Mollenhour
* http://colin.mollenhour.com/
* [@colinmollenhour](https://twitter.com/colinmollenhour)
* [Follow me on github!](https://github.com/colinmollenhour)

## License

   Copyright 2009 Colin Mollenhour

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       http://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.
