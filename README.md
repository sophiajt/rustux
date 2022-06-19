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

## 


Things I'd like to try;

* replace fd for find
* replace ripgrep for grep
* add in a Rust-based window manager (leftwm)
* nushell as shell
* bat for cat
* lapce for graphical editor
* helix for terminal editor
* alacritty as the terminal
* 
