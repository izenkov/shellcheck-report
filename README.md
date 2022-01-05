# shellcheck-report

Reports *.sh shellcheck issues in folder and all subfolders

> shellcheck-report scans all *.sh script files in
> cpecified folder and all it's subfolders recursivly.
> It then calls shellcheck utility on script content and
> outputs a number of issues found.

## Dependencies

[shellcheck](https://www.shellcheck.net)

## Install / Uninstall

```sh
./install
./uninstall
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

#### Run shellcheck report on a folder

```sh
shellcheck-report .
shellcheck-report ./scripts
shellcheck-report ~/dev
```

## Example report

```sh
shellcheck-report 1.0 Jan 1, 2022

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

## References

[Google Shell Guide](https://google.github.io/styleguide/shellguide.html)

## License

[MIT](LICENSE)
