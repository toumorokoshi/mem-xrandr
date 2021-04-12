# DESIGN

mem-xrandr

## User journeys

### mem-xrandr load

The command with no input will set the screens to the previous memoized resolutions and displays.

### mem-xrandr -- {xrandr args}

The command will act like xrandr, at set the displays accordingly.

In the case the configuration was successful, the configuration will be saved as the configuration to use when running `mem-xrandr load`

## Design Details

### uniquely identifying the environment

The environment that the user wants to run in can be affected by multiple factors, including:

- if an eGPU is plugged in
- what displays are connected

For now, xrandr and listing the displays available with possible options seems sufficient.

### command name

the command name was chosen to prefix "mem" to ensure that you don't have auto-completion not match after "xrandr", since that will be a complete command.