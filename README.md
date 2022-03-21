#  `javacard-helloworld`

## Build status

[![Build Java Card applet](https://github.com/trombik/javacard-helloworld/actions/workflows/build.yml/badge.svg)](https://github.com/trombik/javacard-helloworld/actions/workflows/build.yml)
[![yamllint](https://github.com/trombik/javacard-helloworld/actions/workflows/yamllint.yml/badge.svg)](https://github.com/trombik/javacard-helloworld/actions/workflows/yamllint.yml)

## Overview

An example repository to build a small example applet. The purpose of the
repository is to create a template project that can be used for Java Card
applet projects, providing a common file system structure, and reproducible CI
on GitHub Actions.

The repository includes the following repositories as `git` `submodule` under
`vendor` directory.

* [`jcardsim`](https://github.com/licel/jcardsim)
* [`oracle_javacard_sdks`](https://github.com/martinpaljak/oracle_javacard_sdks)
* [`vsmartcard`](https://github.com/frankmorgner/vsmartcard)

The repository includes sources from
[YkOtpApplet](https://github.com/arekinath/YkOtpApplet) as an example.
[`build.yml`](.github/workflows/build.yml) GitHub Actions workflow build the
source, generates `.cap` file.

The `build.yml` GitHub Actions workflow install `pcscd`, `jcardsim`, and
`vsmartcard`. They can be used to test the applet in the CI. The repository
does not include tests.

See supported Java Card SDK versions, and JDKs at
[Version compatibility](https://github.com/martinpaljak/ant-javacard/wiki/Version-compatibility).

## Requirements

The list of packages required to build the example is defined as
`PROJECT_REQUIRED_PACKAGES` in [`build.yml`](.github/workflows/build.yml).

## Known issues

N/A

## Usage

Clone (or update) the repository.

Update `git` `submodules`:

```console
git submodule update --init --recursive
```

Set `JC_HOME` environment variable to Java Card SDK directory. Java Card SDKs
are bundled under [`vendor/oracle_javacard_sdks`](vendor/oracle_javacard_sdks).

Set `JAVA_HOME` environment variable to JDK. Note that the example below is
for Linux distributions.

Run `ant` to build the applet.

```console
export JAVA_HOME="/usr/lib/jvm/adoptopenjdk-8-hotspot-amd64"
export JC_HOME="$PWD/vendor/oracle_javacard_sdks/jc305u3_kit"
ant
```

## Resources

[oracle_javacard_sdks](https://github.com/martinpaljak/oracle_javacard_sdks),
used to install Java Card SDK.

[ant-javacard](https://github.com/martinpaljak/ant-javacard), used to build
applets with `ant`.
