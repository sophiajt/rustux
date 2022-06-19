# rustux

A thought experiment in creating a Rust-based Linux distro.

Note: this is UNSUPPORTED. It's just for fun :D

## Picking the distro

For this experiment, I picked [Arch linux](https://archlinux.org/) as it felt like the easiest way to start with a known, well-supported base. You could also use some of the Linux-from-scratch style distros.

For the installation of Arch, I chose to only install the basic graphical system without installing any desktops. We'll pick our window manager later.

For this I chose: `archlinux-2022.06.01-x86_64.iso`

Then `archinstall` on boot.
Then, I set the profile to the `xorg` profile. Made a user. Set up NetworkManager.
Finish the install and reboot and we're in. Now to start installing our Rust tools.

## Installing Rust

Install Rust via [rustup](https://rustup.rs/)
If you chose Arch, you can also install [paru](https://github.com/Morganamilo/paru) (a Rust-based AUR tool). It will also install Rust for you.

You may want to install [rust-analyzer](https://github.com/rust-lang/rust-analyzer) to go with helix (below).

## Install our first tools

Once Rust is installed, it's time to add some good commandline tools to help us do the rest of the setup. Arch doesn't come with vim by default. That's okay, we have [helix](https://github.com/helix-editor/helix).

You can also install `ripgrep` and `fd-find` from cargo here.

## Install leftwm

Install [leftwm](https://github.com/leftwm/leftwm), a Rust-based window manager
Install [leftwm-theme](https://github.com/leftwm/leftwm-theme), so we can easily pick a theme

You may also want to install `elogind` if you have any issues getting leftwm to work. 

## Install alacritty

We need a terminal, and [alacritty](https://github.com/alacritty/alacritty) fits the bill.

You may also want to configure `leftwm` to run alacritty as your default terminal.

## Startup X

Let's configure leftwm and get into a graphical environment.

With `elogind`, we can make our .xinitrc:

```shell
# .xinitrc
exec dbus-launch leftwm
```

Then `startx` and we're in.

## Shell

Let's give ourselves a shell. [nushell](https://github.com/nushell/nushell) is great. You can install [starship](https://github.com/starship/starship) to go with it.

You may want to install some nerd fonts to get the most out of these.

`let-env EDITOR = "helix"` will let you set a default editor.

If you want to make `nu` your default shell, you may want to run `config env` and set up the PATH to be what you want. You can put something like this at the bottom.

```nushell
let-env PATH = [
  # all your paths
]
```

## Areas that need some love

Graphical apps in general. There are [some](https://github.com/rust-unofficial/awesome-rust) but it's still really early days for Rust and graphical apps.

We don't have a browser. If you're brave, you can try using [servo](https://github.com/servo/servo).

## Going further

You can go deeper by installing the [rewrite of coreutils to Rust](https://github.com/uutils/coreutils)

