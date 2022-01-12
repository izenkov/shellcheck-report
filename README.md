# shellcheck-report

Reports *.sh shellcheck issues in folder and all subfolders

> shellcheck-report scans all *.sh script files in
> specified folder and all it's subfolders recursively.
> It then calls shellcheck utility on script content and
> outputs a number of issues found.

## Dependencies

- [shellcheck](https://www.shellcheck.net)
- [Bash](https://www.gnu.org/software/bash) 4.3.* or newer

## Install / Uninstall

### Linux, macOS

```sh
./install
./uninstall
```

On macOS, if you are still running Bash 3.2 written in 2007 shellcheck-report will not run. You have two options. The recomended way would be upgrading to the latest Bash version using [Homebrew](https://brew.sh) or [Macports](https://www.macports.org) package managers. Second option would be backporting shellcheck-report to Bash 3.2 or porting to a different shell (zsh for example). Here is the [link](https://github.com/izenkov/free-the-bash) to Homebrew based utility for upgrading macOS Bash to the latest version and setting upgraded Bash as default login shell.

### Windows Git Bash Terminal

```cmd
rem Execute from Command Prompt running as Administrator
copy shellcheck-report "%ProgramFiles%\Git\usr\bin"
```

After that shellcheck-report will be visible in /usr/bin folder inside Git Bash Terminal. And because /usr/bin is in $PATH shellcheck-report can be executed without specifing full path name.

If you get an error

```sh
shellcheck (www.shellcheck.net) not found
```

Download [shellcheck.exe](https://github.com/koalaman/shellcheck/releases/download/stable/shellcheck-stable.zip) and drop it into the same location.

```cmd
rem Execute from Command Prompt running as Administrator
copy shellcheck.exe "%ProgramFiles%\Git\usr\bin"
```

## Usage

#### Show help screen

```sh
shellcheck-report -h
```

#### Show version information

```sh
shellcheck-report -v
```

#### Scan folder

```sh
shellcheck-report .
shellcheck-report ./scripts
shellcheck-report ~/dev
```

#### Scan folder, option -0 (exclude files with 0 errors)

```sh
shellcheck-report -0 .
shellcheck-report -0 ./scripts
shellcheck-report -0 ~/dev
```

#### Scan folder, option -c (print total errors found)

```sh
shellcheck-report -c .
shellcheck-report -c ./scripts
shellcheck-report -c ~/dev
```

#### Scan folder, option -q (quiet, return exit code)

```sh
shellcheck-report -q .
shellcheck-report -q ./scripts
shellcheck-report -q ~/dev
```

## Example report

```sh
shellcheck-report 1.0.1 Jan 1, 2022

re2c-2.2

  3 ./build/__build_asan.sh
  5 ./build/__cmakebuild_check_headers.sh
  3 ./build/__cmakebuild_redundant_exports.sh
  3 ./build/__build_ubsan.sh
  3 ./build/__cmakebuild.sh
  3 ./build/__cmakebuild_glibcxx_debug.sh
  3 ./build/__cmakebuild_iwyu.sh
  3 ./build/__cmakebuild_clang_msan.sh
  3 ./build/__build_redundant_exports.sh
  3 ./build/__cmakebuild_mingw.sh
  3 ./build/__cmakebuild_clang.sh
  3 ./build/__cmakebuild_ubsan.sh
  3 ./build/__build_m32.sh
  5 ./build/__build_check_headers.sh
  2 ./build/re2c-as-subproject/build.sh
  3 ./build/__build_mingw.sh
  3 ./build/__build_clang.sh
  1 ./build/split_man.sh
  3 ./build/__build_mingw_slibtool.sh
  3 ./build/__cmakebuild_nodebug.sh
  4 ./build/__alltest.sh
  2 ./build/__build_iwyu.sh
  3 ./build/__cmakebuild_m32.sh
  3 ./build/__cmakebuild_asan.sh
  3 ./build/__build.sh
  3 ./build/__build_glibcxx_debug.sh
  0 ./build/gen_help.sh
  3 ./build/__build_clang_msan.sh
  9 ./build/__distcheck.sh
  3 ./build/__build_nodebug.sh
 16 ./examples/c/__run_all.sh
 10 ./examples/go/__run_all.sh
  0 ./built-and-install.sh
711 ./ltmain.sh
  0 ./autogen.sh
  9 ./test/__run_unicode_tests.sh
 14 ./test/golang/__run_all.sh
 10 ./test/posix_captures/.gen/__gen.sh
 24 ./test/posix_captures/.run/__run.sh
711 ./build-aux/ltmain.sh

1599 issues in 40 *.sh files
```

## Exit codes (-q option)

- 0: All files successfully scanned with no issues.
- 1: All files successfully scanned with some issues.
- 3: Bad syntax or options

## References

- [Google Shell Guide](https://google.github.io/styleguide/shellguide.html)

## License

[MIT](LICENSE)
