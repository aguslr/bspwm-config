# bspwm configuration

## About

This repository stores my configuration of [bspwm][bspwm], *a tiling window
manager based on binary space partitioning*, and [sxhkd][sxhkd], *a simple X
hotkey daemon*.

## Getting the files

### Using Git

If we have Git installed on the system, we can get the files directly from the
repository:

```sh
git clone https://gitlab.com/aguslr/bspwm-config
```

After this, every time we want to update the files we do:

```sh
cd bspwm-config && git pull
```

### Without Git

If Git is not installed, we can still get the files as long as we have a basic
Unix environment available:

```sh
wget https://gitlab.com/aguslr/bspwm-config/-/archive/main/bspwm-config-main.tar.gz -O - | tar -xzv --strip-components 1 --exclude={README.md,demo.gif}
```

## Installing with Stow

To easily create and manage links to the files we can use [GNU Stow][stow] as
follows:

```sh
stow -vt ~ -S .
```

## Demo

![Demo GIF](https://gitlab.com/aguslr/bspwm-config/raw/main/demo.gif "Demo")

[bspwm]: https://github.com/baskerville/bspwm
[sxhkd]: https://github.com/baskerville/sxhkd
[stow]: https://www.gnu.org/software/stow/
