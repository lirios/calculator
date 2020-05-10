Liri Calculator
===============

[![License](https://img.shields.io/badge/license-GPLv3.0-blue.svg)](https://www.gnu.org/licenses/gpl-3.0.html)
[![GitHub release](https://img.shields.io/github/release/lirios/calculator.svg)](https://github.com/lirios/calculator)
[![GitHub issues](https://img.shields.io/github/issues/lirios/calculator.svg)](https://github.com/lirios/calculator/issues)
[![Snap Status](https://build.snapcraft.io/badge/lirios/calculator.svg)](https://build.snapcraft.io/user/lirios/calculator)
[![CI](https://github.com/lirios/calculator/workflows/CI/badge.svg?branch=develop&event=push)](https://github.com/lirios/calculator/actions?query=workflow%3ACI)

A cross-platform material design calculator.

![Screenshot](https://raw.githubusercontent.com/lirios/calculator/develop/.project/screenshots/calculator1.png)

## Dependencies

Qt >= 5.10.0 with at least the following modules is required:

 * [qtbase](http://code.qt.io/cgit/qt/qtbase.git)
 * [qtdeclarative](http://code.qt.io/cgit/qt/qtdeclarative.git)
 * [qtquickcontrols2](http://code.qt.io/cgit/qt/qtquickcontrols2.git)

The following modules and their dependencies are required:

 * [cmake](https://gitlab.kitware.com/cmake/cmake) >= 3.10.0
 * [cmake-shared](https://github.com/lirios/cmake-shared.git) >= 1.0.0
 * [fluid](https://github.com/lirios/fluid.git) >= 1.0.0

## Installation

```sh
mkdir build
cd build
cmake -DCMAKE_INSTALL_PREFIX=/path/to/prefix ..
make
make install # use sudo if necessary
```

Replace `/path/to/prefix` to your installation prefix.
Default is `/usr/local`.

You can also append the following options to the `cmake` command:

 * `-DCALCULATOR_WITH_FLUID:BOOL=ON`: Build with a local copy of the Fluid sources.

## Licensing

Licensed under the terms of the GNU General Public License version 3 or, at your option, any later version.
