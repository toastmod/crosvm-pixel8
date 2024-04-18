# crosvm-pixel8
A crosvm build environment targeting the Pixel 8, using purely the 

# Dependencies
As per the [AOSP Documentation](https://source.android.com/docs/setup/start/requirements), you'll need to install these packages.
```
sudo apt install git-core gnupg flex bison build-essential zip curl zlib1g-dev libc6-dev-i386 libncurses5 x11proto-core-dev libx11-dev lib32z1-dev libgl1-mesa-dev libxml2-utils xsltproc unzip fontconfig
sudo apt install repo
```

Then you'll need to [install rust](http://rustup.rs).

Also install the android target for rust:
```
rustup target add aarch64-linux-android
```
Note [this (old-ish) tutorial](https://mozilla.github.io/firefox-browser-architecture/experiments/2017-09-21-rust-on-android.html) for reference.
Though bear in mind this is NDK oriented, we are building with the AOSP toolchain.

# Usage
Hypothetically:
```
cd platform
./fetch-aosp-repo.sh
source build/envsetup.sh
lunch aosp_shiba-trunk_staging-userdebug
mm external/crosvm
```
