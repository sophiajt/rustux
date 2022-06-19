# rustux

A thought experiment in creating a Rust-based Linux distro.

## Picking the distro

For this experiment, I picked arch linux as it felt like the easiest way to start with a known, well-supported base. You could also use some of the Linux-from-scratch style distros.

For the installation of Arch, I chose to only install the basic graphical system without installing any desktops. We'll pick our window manager later.

For this I chose: `archlinux-2022.06.01-x86_64.iso`

Then `archinstall` on boot.
Then, I set the profile to the `xorg` profile. Made a user. Set up NetworkManager.
Finish the install and reboot and we're in. Now to start installing our Rust tools.

##

Things I'd like to try;

* replace fd for find
* replace ripgrep for grep
* add in a Rust-based window manager (leftwm)
* nushell as shell
* bat for cat
* 
