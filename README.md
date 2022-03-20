#  `javacard-helloworld`

## Build status

[![Build Java Card applet](https://github.com/trombik/javacard-helloworld/actions/workflows/build.yml/badge.svg)](https://github.com/trombik/javacard-helloworld/actions/workflows/build.yml)

An example repository to build `helloworld` example. The purpose of the
repository is to create a template project that can be used for Java Card
applet projects, providing a common file system structure, and reproducible CI
on GitHub Actions.

The repository includes the following repositories as `git` `submodule` under
`vendor` directory.

* [`jcardsim`](https://github.com/licel/jcardsim)
* [`oracle_javacard_sdks`](https://github.com/martinpaljak/oracle_javacard_sdks)
* [`vsmartcard`](https://github.com/frankmorgner/vsmartcard)

## Known issues

The repository does not include source code to build (yet).

## Usage

Clone (or update) the repository.

Update `git` `submodules`:

```console
git submodule update --init --recursive
```
