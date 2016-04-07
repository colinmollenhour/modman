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

  * Linux/Unix or OSX (not cygwin, see _Windows Users_ below)
  * bash
  * Common utilities available in your PATH: grep (POSIX), find, ln, cp, basename, dirname
  * Web server must follow symlinks
  * git and/or subversion are optional (not required for "deploy" command)

### Magento Users

If using template files in a modman module, you must either:

#### Option 1:

Use a [patched](https://gist.github.com/colinmollenhour/35c0d32dd651c4c8c840/revisions) version of Mage/Core/Block/Template.php. This gist is itself a modman module so you can install it by cloning it directly or you can integrate it into your environment some other way.

```
$ modman clone template-patch https://gist.github.com/35c0d32dd651c4c8c840.git
```

*NOTE:* I provide no warranties for using this patch. Use at your own risk!

#### Option 2:
Enable "Allow Symlinks" (found under System > Configuration > Advanced > Developer).

![Allow Symlinks](https://f.cloud.github.com/assets/1337461/43324/820d4d96-567f-11e2-947a-167bf76db33f.png)

*NOTE:* Disabling this security protection does decrease security as it allows template files to be loaded from any location. However, the risk is not so much symlinks as it is specially crafted template paths. The patched Template.php file (Option 1) allows the use of symlinks but should still prevent templates from being loaded from directories other than the app/design directory.

### Windows Users

Windows (including cygwin) is not supported by this script, but there is a [PHP-port of
modman](https://github.com/sitewards/modman-php) which works on Windows. I am not affiliated
with the authors and do not provide support for the PHP port, only a link here for reference.

## Installation

To install Modman, you can either install the library in your user's root folder, or you can install Modman globally.
Regardless of which option you choose, first run one of these two scripts to download the Modman repo.
```
bash < <(wget -q --no-check-certificate -O - https://raw.github.com/colinmollenhour/modman/master/modman-installer)

or

bash < <(curl -s -L https://raw.github.com/colinmollenhour/modman/master/modman-installer)
```

####1. Root Folder

If you'd like to keep the script in its native location at ``` ~/bin/ ```, just reload your Bash profile.
```
source ~/.profile
```

####2. Installing Modman Globally

To make the script global after downloading, move the Modman script to an appropriate script folder, (e.g. ``` /usr/local/bin/ ``` or something similar within /usr/*).
Moving it to one of the paths already loaded in your $PATH variable will automatically pick it up without a ~/.profile reload.
```
mv ~/bin/modman /usr/local/{{ preferred folder }}
```

And then finally, alias Modman with a symlink if you want something shorter to type (optional)
```
ln -s /usr/local/{{ preferred folder }}/modman /usr/local/{{ preferred folder }}/{{ symlink }}
```

Note: modman is simply a bash script, so to use it you just need to place it in your $PATH
and change its mode to executable.

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
