# Crystal Arch Linux Base

My fork to build a vanila minimalistic Arch Linux vagrant box. It is based on
newly available official box at
[archlinux/arch-boxes](https://github.com/archlinux/arch-boxes). Detailed
instructions can be found there.

## Main differences

* Only virtualbox-iso build. All qmeu/kvm builder files are untouched.
* No Polkit.
* Change the root filesystem from btrfs to xfs.
* Mirrorlist are fixed instead of `rankmirrors`, which takes unnecessarily long time.
* ISO are downloaded separately (a result of poor network), and iso_url refers
  to local file.

## Building

1. Change mirror server in install.sh.
2. Download the ISO and placed in the ./packer_cache
3. Follow steps of original building steps.
4. Only build virtualbox box: `packer build --only=virtualbox-iso vagrant.json`
