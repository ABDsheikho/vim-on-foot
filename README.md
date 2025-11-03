# vim-on-foot

A foot config file with vim-like keybinds.

## Introduction

[foot](https://codeberg.org/dnkl/foot) is a fast, lightweight and minimalistic Wayland terminal emulator.

And `vim-on-foot` is just a [default foot config file](https://codeberg.org/dnkl/foot/src/branch/master/foot.ini)
that provides some convenient vim-like keybinds added to its settings.

This differs from the usual vim keybinds **(such as `dd` to delete an entire line)**,
and it can be considered as *normal shortcuts*.
For that, it relies heavily on the `Alt` key as its Mod key.

*So hopefully you don't use `Alt` as Mod key that much.*

## Dependency

- [foot terminal](https://codeberg.org/dnkl/foot)

## Installation

### Without overriding any existing config (suitable for experimenting and testing)

```shell
git clone https://github.com/ABDsheikho/vim-on-foot
cd vim-on-foot/
foot -c foot.ini
```

You can remove the vim-on-foot directory after completion.
Or copy it `foot.ini` into your `~/.config/foot/` directory, and change it as you like.

If you don't have a `~/.config/foot/` directory, try the next options.

### By creating config

```shell
git clone https://github.com/ABDsheikho/vim-on-foot "${XDG_CONFIG_HOME:-$HOME/.config}"/foot
```

It's preferred to remove the git repo and initialize your own one.

### By forking (suitable for personal customization)

1. first fork the repo
1. clone your fork of `vim-on-foot`
   ```shell
   git clone https://github.com/<replace-your-username-here>/vim-on-foot "${XDG_CONFIG_HOME:-$HOME/.config}"/foot
   ```

Now you can make changes to your `foot.ini` file and push them to your fork.

## Keybinds

foot has the following *modes*:

- Raw mode.
- Unicode input mode.
- Search mode.
- URL mode.
- Regex mode. *(custom made)*
- Select mode. *(via mouse)*

In Raw mode, keys & keybinds that interact with TUI apps can overlap and interfere with foot keybinds, and vise versa.
While in other modes, foot will block any key combination from passing to TUI apps until exiting the mode.

Regex mode is *custom made* mode, therefore this config doesn't offer any regex keybinds.

The following is a list of all **action-keybind** *currently provided* by foot, with vim-on-foot opt-in.
For more info about each *action* check out `man foot.ini`

### Normal/Navigation keybinds

| action | keybinds | Note |
| --- | --- | --- |
| scrollback-up-page | `Alt+Page_Up` | |
| scrollback-up-half-page | `Alt+u` | |
| scrollback-up-line | `Alt+k` `Alt+Up` | |
| scrollback-down-page | `Alt+Page_Down` | |
| scrollback-down-half-page | `Alt+d` | |
| scrollback-down-line | `Alt+j` `Alt+Down` | |
| scrollback-home | `Alt+h` `Alt+Home` | |
| scrollback-end | `Alt+l` `Alt+End` | |
| clipboard-copy | `Alt+y` `Alt+c` | |
| clipboard-paste | `Alt+p` `Alt+v` | |
| primary-paste | `Alt+P` `Alt+V` | |
| search-start | `Alt+/` `Alt+F` | |
| font-increase | `Alt+plus` `Alt+equal` | |
| font-decrease | `Alt+minus` | |
| font-reset | `Alt+0` | |
| spawn-terminal | `Alt+w` | |
| minimize | none | default |
| maximize | none | default |
| fullscreen | `Alt+Shift+Return` `Alt+Shift+Enter` | |
| pipe-visible | none | default |
| pipe-scrollback | none | default |
| pipe-selected | none | default |
| pipe-command-output | none | default |
| show-urls-launch | `Alt+o` | similar to o for open a new line, but for urls |
| show-urls-copy | `Alt+O` | |
| show-urls-persistent | `Alt+Control+o` | launche url without exiting url-mode |
| prompt-prev | `Alt+K` | enable shell integration first, check [shell-integration](https://codeberg.org/dnkl/foot/wiki#shell-integration) |
| prompt-next | `Alt+J` | enable shell integration first, check [shell-integration](https://codeberg.org/dnkl/foot/wiki#shell-integration) |
| unicode-input | `Alt+i` `Control+Shift+u` | i for input unicode, try input `99ff` or `1f60d` then press enter to confirm |
| color-theme-switch-1 | `Alt+1` | |
| color-theme-switch-2 | `Alt+2` | |
| color-theme-toggle | `Alt+t` | t for toggle |
| noop | none | default |
| quit | `Alt+q` | |

### search-bindings

| action | keybinds | Note |
| --- | --- | --- |
| cancel | `Escape` `Alt+[` | |
| commit | `Return` `Enter` | default |
| find-prev | `Alt+n` | |
| find-next | `Alt+N` | |
| cursor-left | `Left` `Alt+h` | |
| cursor-left-word | `Alt+b` `Control+Left` | |
| cursor-right | `Right` `Alt+l` | |
| cursor-right-word | `Alt+w` `Control+Right` | |
| cursor-home | `Home` `Alt+0` `Control+a` | |
| cursor-end | `End` `Alt+$` `Control+e` | |
| delete-prev | `BackSpace` | default |
| delete-prev-word | `Alt+a` `Control+BackSpace` | |
| delete-next | `Delete` | default |
| delete-next-word | `Alt+s` `Control+Delete` | |
| delete-to-start | `Alt+A` `Control+u` | |
| delete-to-end | `Alt+S` `Control+k` | |
| extend-char | `Alt+L` `Shift+Right` | |
| extend-to-word-boundary | `Alt+W` `Control+w` `Control+Shift+Right` | |
| extend-to-next-whitespace | `Control+Shift+w` | default |
| extend-line-down | `Alt+J` `Shift+Down` | |
| extend-backward-char | `Alt+H` `Shift+Left` | |
| extend-backward-to-word-boundary | `Alt+B` `Control+Shift+Left` | |
| extend-backward-to-next-whitespace | none | default |
| extend-line-up | `Alt+K` `Shift+Up` | |
| clipboard-paste | `Alt+p` `Alt+v` | |
| primary-paste | `Alt+P` `Alt+V` | |
| unicode-input | `Alt+i` `Control+Shift+u` | i for input unicode, try input `99ff` or `1f60d` then press enter to confirm |
| scrollback-up-page | `Alt+Page_Up` | |
| scrollback-up-half-page | `Alt+u` | |
| scrollback-up-line | `Alt+k` `Alt+Up` | |
| scrollback-down-page | `Alt+Page_Down` | |
| scrollback-down-half-page | `Alt+d` | |
| scrollback-down-line | `Alt+j` `Alt+Down` | |
| scrollback-home | none | default |
| scrollback-end | none | default |

### url-bindings

| action | keybinds | Note |
| --- | --- | --- |
| cancel | `Escape` `Alt+[` | |
| toggle-url-visible | `t` | default |

## Credits

- [dnkl](https://codeberg.org/dnkl) for creating this awesome, fast, and lightweight Wayland terminal.

## License

[MIT license](./LICENSE).
