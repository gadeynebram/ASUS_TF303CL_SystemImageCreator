ASUS_TF303CL_SystemImageCreator (Add root package)
=========================

Create system.img for ASUS TF303CL

### How to use

1. run `scripts/build_make_ext4fs.sh`
  - Fetch required source tree from AOSP to `src` directory
  - Build `make_ext4fs` binary for packing `system.img`
  - `make_ext4fs` will be in `bin` directory

2. run `scripts/build_applypatch.sh`
  - Fetch required source tree from AOSP to `src` directory
  - Build `applypatch` binary for applying delta OTA updates
  - `applypatch` will be in `bin` directory

3. run `scripts/build.sh`
  - Fetch ROM file of TF303CL (11.4.1.34, WW version) to `work` directory
  - Extract ROM file and get system directory
  - Inject root package
  - Put whatever your want in `work/system` when pausing
  - Pack `system.img` from `work/system`

### Download

 * Enter fastboot mode by issuing 'adb reboot bootloader' command or power-on with 'power key + volume up'
 * Use 'fastboot flash system system.img' to download image to your phone
 * Reboot to recovery and wipe data if needed
