# dfdmenu

---

**dfdmenu** is a simple fish script that generates cached `.desktop` entries for use with `dmenu`*(-wl)*.

---

## Usage

1. `$ dfdmenu generate-cache` will create and populate 3 universal `fish` variables that act as cached pairs of `.desktop` entry Name's and Exec strings
2. `$ dfdmenu` will spawn `dmenu-wl` with all the possible valid entries.

The script also respects `.desktop`'s `NoDisplay` properties and doesn't cache nor display apps that match that criteria.

If you are using `dmenu` instead of `dmenu-wl` just change the executable in the script. Their options are mutually exclusive.
