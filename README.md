# OdinV4
# Samsung Odin v4 1.2.1-dc05e3ea - For Linux

Welcome to the GitHub repository for Samsung Odin v4 1.2.1-dc05e3ea for Linux. This tool allows you to flash firmware and custom binaries to your Samsung devices directly from a Linux environment.

## Installation

### Download and Setup

1. **Download Odin:**

   Go to the [Releases page](https://github.com/Adrilaw/OdinV4/releases) and download the `odin.zip` file.

2. **Extract the Archive:**
   Open a terminal and navigate to the directory where `odin.zip` was downloaded. Extract the files using:

```bash
unzip odin.zip
```
3. **Make Odin Executable:**
Change the permissions of the odin4 binary to make it executable:

```bash
chmod +x odin4
```
4. **Move odin4 to /bin Directory:**
To make odin4 available system-wide, move it to /bin directory

```bash
sudo cp odin4 /bin
```
# Usage
To use Samsung Odin, simply run the following command:
```bash
odin4
```
For a list of available commands and options, use the help flag:
```bash
odin4 -h
```
` 
Usage : odin4 [args...]
Odin4 downloader. odin4 version 1.2.1-dc05e3ea
 -v        SHOW VERSION
 -w        Show License
 -b        Add Bootloader file
 -a        Add AP image file
 -c        Add CP image file
 -s        Add CSC file
 -u        Add UMS file
 -e        Set Nand erase option
 -V        Home binary validation check with pit file
 --reboot  Reboot into normal mode
 --redownload   Reboot into download mode if it possible (not working in normal case)
 -d        Set a device path (detect automatically without this option)
 -l        Show downloadable devices path

IMPORTANT : You must set up your system to detect your device on LINUX host.
 create this file: /etc/udev/rules.d/51-android.rules
 to add a line to the file:
 SUBSYSTEM=="usb", ATTR{idVendor}=="04e8", MODE="0666", GROUP="plugdev"
   (http://developer.android.com/tools/device.html)
 And you maybe need to unload a module cdc_acm before downloading. (This is only needed for older kernels.)
   $sudo rmmod cdc_acm
 OR
   echo "blacklist cdc_acm" > /etc/modprobe.d/cdc_acm-blacklist.conf

Example :
$odin4 -b BL_XXXX.tar.md5 -a AP_XXXX.tar.md5 -c CP_XXXX.tar.md5 -s CSC_XXXX.tar.md5
Example (Select One Device):
$odin4 -l
PATH_OF_DEVICE_A
PATH_OF_DEVICE_B
$odin4 -b BL_XXXX.tar.md5 -a AP_XXXX.tar.md5 -c CP_XXXX.tar.md5 -s CSC_XXXX.tar.md5 -d PATH_OF_DEVICE_A

Odin Community : http://mobilerndhub.sec.samsung.net/hub/site/odin/

`


