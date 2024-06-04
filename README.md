# Alacritty Dropdown

This program provides drop-down functionality to Alacritty terminal emulator on
X Window System.

## Features

 * **Single instance** - Only one application will be run per user
 * **Independent** - A separate Alacritty configuration file is used, so it
   doesn't interfere with non-Dropdown Alacritty instances
 * **Secure** - Source code is small and simple so it can be read and verified
   before installing

## Usage

### Requirements

This program requires external executables to be available on the system.
Ensure the following commands are available before running the program:
alacritty, wmctrl, xdotool, xprop, flock, grep.

```shell
# Install dependencies on Debian based systems
apt install alacritty wmctrl xdotool x11-utils util-linux grep
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
`$HOME/.alacritty-dropdown.yml`. If you want to store the configuration in a
different location, you should make a change to the source code.

```shell
# Use the example configuration file
cp example.alacritty-dropdown.yml ~/.alacritty-dropdown.yml
```

Depending on your desktop resolution and font's size and aspect-ratio, you
might want to adjust the size of the terminal emulator window. The example file
assumes an aspect-ratio of 0.75 and a 1080p resolution.

Example calculation for `columns` dimension:
```
columns = width / font.size / ratio
160 = 1080 / 9 / 0.75
```

Finally, bind your preferred key using your your desktop environment to Alacritty Dropdown.

## Notes

This program is not intended to be used in an environment running a Wayland compositor.
