# mem-xrandr
xrandr, but memorizes your xrandr configuration for various devices connected

See [DESIGN.md](DESIGN.md) for the long-term design, and the mem-xrandr shell script for a proof of concept.

## Installation

copy the "mem-xrandr" script to a location of your choosing, preferably on your `$PATH`.

## Usage

`mem-xrandr` works almost exactly like xrandr, except for the following:

- if your xrandr command is successful, the output is saved for your particular combination of detected displays.
- running `mem-xrandr` with no arguments will use a saved configuration, if one exists.

In other words, you run `mem-xrandr` with your desired configuration once:

```
mem-xrandr --output eDP-1 --auto --output DP-1 --right-of eDP-1 --auto
```

and next time you connect the same displays up to the same ports, you can recover that configuration with:

```
mem-xrandr
```