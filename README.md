# modman (Module Manager)

Developing extensions for software that doesn't allow you to separate your
files from core files, and keeping that extension under version control and
making it easy to deploy is now much, much easier. Development of this script
was inspired by Magento which forces you to mix your extension files all
throughout the core code directories. With modman, you can specify in a text
file where you want your directories and files to be mapped to, and it will
create symlinks for you so that all of your versioned code is kept in a
directory that is easy to maintain and deploy.

## Requirements

  * Linux/Unix or OSX (not cygwin)
  * bash
  * Common utilities available in your PATH: grep (POSIX), find, ln, cp, basename, dirname
  * Web server must follow symlinks
  * git and/or subversion are optional (not required for "deploy" command)

## Installation

  * [http://code.google.com/p/module-manager/downloads/list Download] or [http://code.google.com/p/module-manager/source/checkout checkout]
  * Move to or create link in your path

## Getting Started

Run `modman --help` to get the basic usage summary or `modman --tutorial` to
see a brief tutorial.

## Version Control Systems

Modman currently supports subversion and git. Other VCSs could be used by
manually checking out the source code into the proper directory and using
the "deploy" command.

## Author

* Colin Mollenhour
* http://colin.mollenhour.com/
* [https://twitter.com/colinmollenhour] @colinmollenhour
* [https://github.com/colinmollenhour Follow me on github!]

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
