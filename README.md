# dfdmenu

**dfdmenu** is a simple fish script that generates cached `.desktop` entries for use with `dmenu`*(-wl)*.

## Usage

1. `$ dfdmenu generate-cache` will create and populate 3 universal `fish` variables that act as cached pairs of `.desktop` entry Name's and Exec strings
2. `$ dfdmenu` will spawn `dmenu-wl` with all the possible valid entries. After an entry has been chosen, it's Exec parameter is fed to `sh -c` and it is executed.

The script also respects `.desktop`'s `NoDisplay` properties and doesn't cache nor display apps that match that criteria.

The CLI arguments to pass to `dmenu(-wl)` are the ones in the global `$dmenu_opts` array.

The script tracks and caches `.desktop` files in `/usr/share/applications` and `$HOME/.local/share/applications`. If you wish to track `.desktop` files in any other location, modify the script and append them to the `locations` variable.

## Pacmam hook

To use the provided `pacman` hook, replace `/path/to/dfdmenu` with an actual path to the `dfdmenu` script on your machine and place the hook file in a location in which pacman will recognize it (most likely `/etc/pacman.d/hooks`).

This will result in the cache being (re)generated once any `pacman` operation modifies any .desktop file.
