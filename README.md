![](examples/nordlicht-logo.png)

**nordlicht** is a C library for converting video files into colorful barcodes. It is inspired by the [Moviebarcode Tumblr](http://moviebarcode.tumblr.com/), but aims at the next logical step: Integrating these barcodes into video players to make navigation faster and more precise.

*nordlicht* provides a command line tool, which you can use to generate your own barcodes easily.

## Examples

Here's the barcode for [Tears of Steel](http://tearsofsteel.org/). It was created by taking the movie's frames at regular intervals, scaling them to 1 pixel width, and appending them. You can differentiate inside and outside scenes, the credits, and the "secret" scene at the end:

![](examples/tears-of-steel.png)

This barcode of [Elephants Dream](http://www.elephantsdream.org/) uses the *vertical* style, which compresses video's frames to columns and rotates them counterclockwise. This style emphasizes the movement of characters:

![](examples/elephants-dream-vertical.png)

## Installation

- Arch Linux: Install the [`nordlicht`](https://aur.archlinux.org/packages/nordlicht/) package from the [AUR](https://wiki.archlinux.org/index.php/Arch_User_Repository)
- Ubuntu: Install `nordlicht` from Launchpad's [ppa:blinry/nordlicht](https://launchpad.net/~blinry/+archive/nordlicht), [here's how](https://help.launchpad.net/Packaging/PPA/InstallingSoftware)
- Gentoo: Install the `media-video/nordlicht` package from the [multimedia overlay](https://gitorious.org/gentoo-multimedia/gentoo-multimedia), [here's how](https://www.gentoo.org/proj/en/overlays/userguide.xml)
- On other distributions, get CMake, FFmpeg, libpng, [popt](http://freecode.com/projects/popt), and [help2man](https://www.gnu.org/software/help2man/), and issue: `mkdir build && cd build && cmake .. && make && make install`

## Usage

### Command line tool

Basic usage: `nordlicht video.mkv -w 1000 -h 150 -o barcode.png` converts *video.mkv* to a barcode of 1000 x 150 pixels size and writes it to *barcode.png*. Run `nordlicht --help` to learn more.

### Library

See [examples/nordlicht-example.c](examples/nordlicht-example.c) for two short examples of the library's API.

## Integrations

### mpv

For [mpv](http://mpv.io/) (>= 0.3.6), there is an experimental [lua plugin](/utils/mpv-nordlicht.lua). Symlink the file from `~/.mpv/lua/`, and mpv displays a live-updating barcode of the current video file at the top. You can turn it on and off by pressing `n`. You'll ImageMagick! This is how it looks like (for [Decay](http://www.decayfilm.com/)):

![](/examples/mpv-integration.png)

For mpv >= 0.2.0, there is an older script called [mpv-nordlicht](/utils/mpv-nordlicht). Put it in your `PATH` and use it instead of `mpv`. It doesn't support multiple files, and you cannot hide the barcode.

## Contributing

Development of *nordlicht* happens on GitHub. Please report any bugs or ideas to the [issue tracker](https://github.com/blinry/nordlicht/issues). To contribute code, fork the repository and submit a pull request.

You can also help by packaging the software for your favorite operating system, or writing an integration for your favorite video player. Even rough prototypes are highly appreciated!

*nordlicht* uses [semantic versioning](http://semver.org/).

## License: GPLv2+

*nordlicht* is free software; you can redistribute it and/or modify it under the terms of the GNU General Public License as published by the Free Software Foundation; either version 2 of the License, or (at your option) any later version.

The header image shows an Aurora Borealis, which is called "Nordlicht" (nord-/lɪ[ç](https://en.wikipedia.org/wiki/Voiceless_palatal_fricative)t/) in German. The picture was taken in Greenland during the [Shelios 2012 expedition](http://shelios.com/sh2012) and is available under the [Creative Commons Attribution-NonCommercial License](https://creativecommons.org/licenses/by-nc/2.0/).
