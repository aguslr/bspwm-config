# bspwm configuration

## About

This repository stores my configuration of [bspwm][bspwm], which is *a tiling
window manager based on binary space partitioning*, and [sxhkd][sxhkd], *a
simple X hotkey daemon*.

## Getting the files

### Using Git

If we have Git installed on the system, we can get the files directly from the
repository:

```sh
git clone git://github.com/aguslr/bspwm-config.git
```

After this, every time we want to update the files we do:

```sh
cd bspwm-config && git pull
```

### Without Git

If Git is not installed, we can still get the files as long as we have a basic
Unix environment available:

```sh
wget https://github.com/aguslr/bspwm-config/tarball/master -O - | tar -xzv --strip-components 1 --exclude={README.md}
```

[bspwm]: https://github.com/baskerville/bspwm
[sxhkd]: https://github.com/baskerville/sxhkd