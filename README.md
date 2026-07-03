# Alacritty Dropdown

This program provides drop-down functionality to Alacritty terminal emulator on
X Window System.

## Features

 * **Single instance** - Only one application will be run per user
 * **Independent** - A separate Alacritty configuration file is used, so it
   doesn't interfere with non-Dropdown Alacritty instances
 * **Adaptive resizing** - Upon startup, window size is adjusted to screen size
 * **Secure** - Source code is small and simple so it can be read and verified
   before installing

## Usage

### Requirements

This program requires external executables to be available on the system.
Ensure the following commands are available before running the program:
alacritty, wmctrl, xdotool, xprop, flock, grep, timeout.

```shell
# Install dependencies on Debian based systems
apt install alacritty wmctrl xdotool x11-utils
```

### Installation

Copy `alacritty-dropdown` manually, or install it using `make`.

```shell
# Install to default location
make install
```

### Configuration

There is an example configuration file provided, which should be adjusted to
your preferences. As the program is limited to a single instance, the provided
configuration uses a dedicated `tmux` session to add support for tabs. The
program assumes the configuration file is located at
`$XDG_CONFIG_HOME/alacritty/alacritty-dropdown.toml`. If you want to store the
configuration in a different location, you should make a change to the source
code.

```shell
# Use the example configuration file
mkdir -p "$XDG_CONFIG_HOME/alacritty"
cp example.alacritty-dropdown.toml "$XDG_CONFIG_HOME/alacritty/alacritty-dropdown.toml"
```

Finally, bind your preferred key in your desktop environment settings to
Alacritty Dropdown.
