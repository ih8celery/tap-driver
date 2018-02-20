version 1.0

#What is tap?

  `tap` is a driver written in perl 5 for the Test Anything Protocol.
I originally intended for tap to be a throwaway script I used in testing
[libtap++](https://github.com/ih8celery/libtap++), but now I use it as an alternative to testing with CTest
in my CMake builds. the program is simple enough to describe in this 
README, as libtap++ provides most relevant test output. this script
simply coordinates executions.

#Usage

  `tap \[options\] \[files\]`

  `tap` expects to find any options before files; the first non-option
is read as a file. if no files are found, `tap` assumes you want it to
use the current working directory. files may be executable or 
directories, which are searched recursively (depth 1) for executables.
`tap` runs the executables as it finds them.

  tap has three options, none of which may take arguments:
      `-v|-version`   -> print the version number and exit
      `-q|-quiet`     -> suppress report of tests failed
      `-h|-help`      -> print a version of this help

the second option may need some explanation for those not familiar with
[TAP](https://testanything.org). after running tests, an executable may
return the value of exit\_status(), which is the number of tests failed.
`tap` captures this return value from each executable and by default prints
a brief summary after each group of tests. `-quiet` turns off this
reporting.

#Installation

  clone this repository and copy the script somewhere on your $PATH. I
keep a bin/ directory in my $HOME for just this sort of thing.

#Copyright and License Information

Copyright 2018 Adam Marshall.


