# mas-cli

A simple command line interface for the Mac App Store. Designed for scripting 
and automation.

## Install

[Homebrew](hb) is the preferred way to install:

    brew install argon/mas/mas

Alternatively binaries are available in the [GitHub Releases](ghreleases)

## Usage

Each application in the Mac App Store has a product identifier which is also
used for mas-cli commands. Using `mas list` will show all installed
applications and their product identifiers.

    $ mas list
    446107677 Screens
    407963104 Pixelmator
    497799835 Xcode

To install or update an application simply run `mas install`:

    $ mas install 808809998
    ==> Downloading PaintCode 2
    ==> Installed PaintCode 2

Use `mas outdated` to list all applications with pending updates.

    $ mas outdated
    497799835 Xcode (7.0)
    446107677 Screens VNC - Access Your Computer From Anywhere (3.6.7)

To install all pending updates run `mas upgrade`.

    $ mas upgrade
    Upgrading 2 outdated applications:
    Xcode (7.0), Screens VNC - Access Your Computer From Anywhere (3.6.7)
    ==> Downloading Xcode
    ==> Installed Xcode    
    ==> Downloading iFlicks
    ==> Installed iFlicks    

## Build from source

`mas` currently requires the [bundler](http://bundler.io/) RubyGem in order to 
bootstrap and build the project. There are a number ways to install bundler but
if you have never used it before then installing it with `gem` should be enough.

```
$ gem install bundler
```

You can now bootstrap the project by executing the `bootstrap` script
from the mas sources script directory:

```
$ ./script/bootstrap
```

You can now build from Xcode by opening `mas-cli.xcodeproj`, or from the Terminal:

```
$ ./script/build
```

Build output can be found in the `build/` directory within the project.

```
$ ./build/mas
```

## License

Code is under the MIT license.

[hb]: https://brew.sh
[ghreleases]: https://github.com/argon/mas/releases

