# bm

Quickly jump to bookmarked places in your filesystem.

## Requirements

- [fzf](https://github.com/junegunn/fzf.vim)
- [exa](https://github.com/ogham/exa) _(optional)_

## Install

If you have a `~/bin` folder that is in your `PATH`, just run the following
command after cloning this repo and `cd`ing into it:

```shell
ln -s $(realpath bm) ~/bin/bm
```

If you don't have a `~/bin` folder, either create one and add it to your `PATH` or
install `bm` in a folder that is in your `PATH`.

To add a keyboard shortcut for `bm`, add a line to your `~/.inputrc`. The
following example sets `C-j` to automatically pick a bookmark and `cd` into it:

```shell
"\C-j": "\C-ucd $(bm --expand-interactive)\C-m\C-l"
```

Or, if you use `pushd`:

```shell
"\C-j": "\C-upushd $(bm --expand)\C-m\C-l"
```

## Usage

```shell
# Creates a bookmark for the current directory, using it's basename as the bookmark name
bm
# Creates a bookmark for the current directory named "hello"
bm hello
# Remove existing bookmark hello
bm --remove hello
# Interactively pick a bookmark and remove it (Esc to escape)
bm --remove-interactive
# List available bookmarks
bm --list
# Preview the contents of hello
bm --preview hello
# Expand bookmark hello to its full path
bm --expand hello
# Interactively pick a bookmark and resolve it (Esc to cancel)
bm --expand-interactive
```
