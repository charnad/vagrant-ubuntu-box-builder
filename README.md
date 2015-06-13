## About

What this script does is:

 1. Download the Ubuntu server 64bit iso
 2. Unpack the iso, stick custom preseed file in
 3. Create temporary Virtual Box VM and let Ubuntu install run (preseed file automates the installation)
 4. Generate a vagrant box from the VM
 5. Clean up the VM

## Usage

    ./build.sh

This should do everything you need. If you don't have 
mkisofs, install [homebrew](http://mxcl.github.com/homebrew/), then:

    brew install cdrtools

The script also requires 7z:

    brew install p7zip

## Defaults

Preseed file contains installer settings. Defaults are: US locale, US keyboard layout, timezone Europe/Berlin. Feel free to modify the preseed file according to your needs.

### Viktoras' notes

Current version Ubuntu 15.04 Vivid Vervet

 - Removed initrd shenanigans, just preseed is enough
 - Switched back to wget
 - VM cleanup after build
 - Modified preseed from swedish locale to en_US

### Ben's notes

Forked Carl's repo, and it sort of worked out of the box. Tweaked 
office 12.04 release: 

 - Downloading 12.04 final release. (Today as of this writing)
 - Checking MD5 to make sure it is the right version
 - Added a few more checks for external dependencies, mkisofs
 - Removed wget, and used curl to reduce dependencies
 - Added more output to see what is going on
 - Still designed to work on Mac OS X :)
    ... though it should work for Linux systems too (maybe w/ a bit of porting)

### Carl's original README

Decided I wanted to learn how to make a vagrant base box.

Let's target Precise Pangolin since it should be releasing soon, I said.

Let's automate everything, I said.

Let's do it all on my macbook, I said.

Woo.
