# CFS ZEN tweaks

## Description

The default CPU scheduler in the mainline Linux kernel
is [Completely_Fair_Scheduler (CFS)](https://en.wikipedia.org/wiki/Completely_Fair_Scheduler).

The upstream default settings are tweaked for high throughput which make the desktop applications
unresponsive under heavy CPU loads. This project contains a script that sets the CFS to use same
settings as the [linux-zen ](https://github.com/zen-kernel/zen-kernel) kernel does.

## Getting Started

### Dependencies

Runtime dependencies:

* bash
* gawk
* systemd (for systemd unit)

Build dependencies:

* cmake

### Installing

Available on [AUR](https://aur.archlinux.org/packages/cfs-zen-tweaks/).

Also see [releases page](https://github.com/igo95862/cfs-zen-tweaks/releases/tag/1.0.0) for built RPM and DEB packages.

You can also build from source using cmake build system.

### Enabling systemd unit

Tweaks can be applied on boot using provided systemd unit.

```
systemctl enable --now set-cfs-tweaks.service
```

### SELinux

Script might not work because of restrictive SELinux policy. [See this thread for directions.](https://github.com/igo95862/cfs-zen-tweaks/issues/1)

## Version History

* 1.1.0
    * Added support for kernels before version 5.13
* 1.0.0
    * Initial Release

## License

This project is licensed under the [GPL-2.0-only](https://spdx.org/licenses/GPL-2.0-only.html) License - see the COPYING file for details
