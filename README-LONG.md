
[![GitHub package.json version](https://img.shields.io/github/package-json/v/xpack-dev-tools/m4-xpack)](https://github.com/xpack-dev-tools/m4-xpack/blob/xpack/package.json)
[![GitHub release (latest by date)](https://img.shields.io/github/v/release/xpack-dev-tools/m4-xpack)](https://github.com/xpack-dev-tools/m4-xpack/releases/)
[![npm (scoped)](https://img.shields.io/npm/v/@xpack-dev-tools/m4.svg?color=blue)](https://www.npmjs.com/package/@xpack-dev-tools/m4/)
[![license](https://img.shields.io/github/license/xpack-dev-tools/m4-xpack)](https://github.com/xpack-dev-tools/m4-xpack/blob/xpack/LICENSE)

# The xPack GNU M4

A standalone cross-platform (macOS/Linux) **GNU M4**
binary distribution, intended for reproducible builds.

The main target is Ubuntu 18, whose older version of this utility
fails some builds.

In addition to the the binary archives and the package meta data,
this project also includes the build scripts.

## Overview

This open source project is hosted on GitHub as
[`xpack-dev-tools/m4-xpack`](https://github.com/xpack-dev-tools/m4-xpack)
and provides the platform specific binaries for the
[xPack GNU M4](https://xpack.github.io/m4/).

This distribution follows the official
[GNU M4](https://www.gnu.org/software/m4/) releases.

The binaries can be installed automatically as **binary xPacks** or manually as
**portable archives**.

## Release schedule

The xPack GNU Bash release schedule generally follows the original GNU
[releases](https://ftp.gnu.org/gnu/m4/).

## User info

This section is intended as a shortcut for those who plan
to use the GNU M4 binaries. For full details please read the
[xPack GNU M4](https://xpack.github.io/m4/) pages.

### Easy install

The easiest way to install GNU M4 is using the **binary xPack**, available as
[`@xpack-dev-tools/m4`](https://www.npmjs.com/package/@xpack-dev-tools/m4)
from the [`npmjs.com`](https://www.npmjs.com) registry.

#### Prerequisites

A recent [xpm](https://xpack.github.io/xpm/),
which is a portable [Node.js](https://nodejs.org/) command line application
that complements [npm](https://docs.npmjs.com)
with several extra features specific to
**C/C++ projects**.

It is recommended to install/update to the latest version with:

```sh
npm install --location=global xpm@latest
```

For details please follow the instructions in the
[xPack install](https://xpack.github.io/install/) page.

#### Install

With the `xpm` tool available, installing
the latest version of the package and adding it as
a development dependency for a project is quite easy:

```sh
cd my-project
xpm init # Add a package.json if not already present

xpm install @xpack-dev-tools/m4@latest --verbose

ls -l xpacks/.bin
```

This command will:

- install the latest available version,
into the central xPacks store, if not already there
- add symbolic links to the central store
(or `.cmd` forwarders on Windows) into
the local `xpacks/.bin` folder.

The central xPacks store is a platform dependent
location in the home folder;
check the output of the `xpm` command for the actual
folder used on your platform.
This location is configurable via the environment variable
`XPACKS_STORE_FOLDER`; for more details please check the
[xpm folders](https://xpack.github.io/xpm/folders/) page.

It is also possible to install GNU M4 globally, in the user home folder:

```sh
xpm install --global @xpack-dev-tools/m4@latest --verbose
```

After install, the package should create a structure like this (macOS files;
only the first two depth levels are shown):

```console
$ tree -L 2 /Users/ilg/Library/xPacks/\@xpack-dev-tools/m4/1.4.19-3.1/.content/
/Users/ilg/Library/xPacks/\@xpack-dev-tools/m4/1.4.19-3.1/.content/
├── README.md
├── bin
│   ├── gm4 -> m4
│   └── m4
├── distro-info
│   ├── CHANGELOG.md
│   ├── licenses
│   └── scripts
├── libexec
│   └── libiconv.2.dylib
└── share
    └── info

8 directories, 5 files
```

No other files are installed in any system folders or other locations.

#### Uninstall

The binaries are distributed as portable archives; thus they do not need
to run a setup and do not require an uninstall; simply removing the
folder is enough.

To remove the links created by xpm in the current project:

```sh
cd my-project

xpm uninstall @xpack-dev-tools/m4
```

To completely remove the package from the central xPack store:

```sh
xpm uninstall --global @xpack-dev-tools/m4
```

### Manual install

For all platforms, the **xPack GNU M4**
binaries are released as portable
archives that can be installed in any location.

The archives can be downloaded from the
GitHub [Releases](https://github.com/xpack-dev-tools/m4-xpack/releases/)
page.

For more details please read the
[Install](https://xpack.github.io/m4/install/) page.

### Versioning

The version strings used by the GNU M4 project are two number strings
like `9.1`, extended to `1.4.19` to look like semver;
to this string the xPack distribution adds a four number,
but since semver allows only three numbers, all additional ones can
be added only as pre-release strings, separated by a dash,
like `1.4.19-3`. When published as a npm package, the version gets
a fifth number, like `1.4.19-3.1`.

Since adherence of third party packages to semver is not guaranteed,
it is recommended to use semver expressions like `^1.4.19` and `~1.4.19`
with caution, and prefer exact matches, like `1.4.19-3.1`.

## Maintainer info

For maintainer info, please see the
[README-MAINTAINER](https://github.com/xpack-dev-tools/m4-xpack/blob/xpack/README-MAINTAINER.md).

## Support

The quick advice for getting support is to use the GitHub
[Discussions](https://github.com/xpack-dev-tools/m4-xpack/discussions/).

For more details please read the
[Support](https://xpack.github.io/m4/support/) page.

## License

Unless otherwise stated, the content is released under the terms of the
[MIT License](https://opensource.org/licenses/mit/),
with all rights reserved to
[Liviu Ionescu](https://github.com/ilg-ul).

The binary distributions include several open-source components; the
corresponding licenses are available in the installed
`distro-info/licenses` folder.

## Download analytics

- GitHub [`xpack-dev-tools/m4-xpack`](https://github.com/xpack-dev-tools/m4-xpack/) repo
  - latest xPack release
[![Github All Releases](https://img.shields.io/github/downloads/xpack-dev-tools/m4-xpack/latest/total.svg)](https://github.com/xpack-dev-tools/m4-xpack/releases/)
  - all xPack releases [![Github All Releases](https://img.shields.io/github/downloads/xpack-dev-tools/m4-xpack/total.svg)](https://github.com/xpack-dev-tools/m4-xpack/releases/)
  - [individual file counters](https://somsubhra.github.io/github-release-stats/?username=xpack-dev-tools&repository=m4-xpack) (grouped per release)
- npmjs.com [`@xpack-dev-tools/m4`](https://www.npmjs.com/package/@xpack-dev-tools/m4/) xPack
  - latest release, per month
[![npm (scoped)](https://img.shields.io/npm/v/@xpack-dev-tools/m4.svg)](https://www.npmjs.com/package/@xpack-dev-tools/m4/)
[![npm](https://img.shields.io/npm/dm/@xpack-dev-tools/m4.svg)](https://www.npmjs.com/package/@xpack-dev-tools/m4/)
  - all releases [![npm](https://img.shields.io/npm/dt/@xpack-dev-tools/m4.svg)](https://www.npmjs.com/package/@xpack-dev-tools/m4/)

Credit to [Shields IO](https://shields.io) for the badges and to
[Somsubhra/github-release-stats](https://github.com/Somsubhra/github-release-stats)
for the individual file counters.
