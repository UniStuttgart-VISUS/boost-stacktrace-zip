# boost-stacktrace-zip

This repository provides the [Boost.Stacktrace](https://github.com/boostorg/stacktrace) library including all internal dependencies as a single zip file.
This allows direct downloading from within a CMake script, without the need to fetch many git submodules.
The zip file can be found on the releases page.

## zip file generation

```sh
git clone --depth 1 --branch boost-1.80.0 https://github.com/boostorg/boost.git
cd boost
git submodule update --init --depth 1 tools/boostdep tools/cmake libs/stacktrace
python3 tools/boostdep/depinst/depinst.py stacktrace
find . -name ".git" -prune -exec rm -rf "{}" \;
zip -r ../boost-stacktrace.zip *
```
