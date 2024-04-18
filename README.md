# crosvm-pixel8
Please note this is a work in progress.
A crosvm build environment targeting the Pixel 8, using the AOSP build tools and Rust.

# Dependencies
As per the [AOSP Documentation](https://source.android.com/docs/setup/start/requirements), you'll need to install these packages.
```sh
sudo apt install git-core gnupg flex bison build-essential zip curl zlib1g-dev libc6-dev-i386 libncurses5 x11proto-core-dev libx11-dev lib32z1-dev libgl1-mesa-dev libxml2-utils xsltproc unzip fontconfig
sudo apt install repo
```

Then you'll need to [install rust](http://rustup.rs).

Also install the android target for rust:
```sh
rustup target add aarch64-linux-android
```
Note [this (old-ish) tutorial](https://mozilla.github.io/firefox-browser-architecture/experiments/2017-09-21-rust-on-android.html) for reference.
Though bear in mind this is NDK oriented, we are building with the AOSP toolchain.

# Usage
Hypothetically:
```sh
cd platform

# This only clones the build tools needed from AOSP, not the entire source tree.
# However it will still take up alot of space.
./fetch-aosp-repo.sh

# Once the AOSP projects are done syncing, activate the toolchain.
source build/envsetup.sh

# Set the lunch menu to target 'aosp_shiba', from 'trunk_staging' and with 'userdebug' build mode. 
lunch aosp_shiba-trunk_staging-userdebug

# Build crosvm
mm external/crosvm
```
