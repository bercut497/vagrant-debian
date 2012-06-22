Usage
-----
This is what it takes to create your own Vagrant box from the Debian netinstall ISO image:

    make [32 | 64]

Dependencies: **VirtualBox, cdrtools, vagrant**

**Note!** Mac OS X Lion seems to have a broken libarchive, unable to unpack Debian ISO files. Possible solution:

    brew tap homebrew/dupes
    brew install homebrew/dupes/libarchive
    cp /usr/bin/bsdtar /usr/bin/bsdtar.orig
    cp /usr/local/bin/bsdtar /usr/bin/bsdtar

William's notes
---------------

Forked off https://github.com/joneskoo/vagrant-debian-squeeze-32

New stuff:

- 64-bit
- Bumped to 6.0.5
- Depend on bsdtar. GNU tar can not extract ISO.
- Run with Debian's VirtualBox toolset
- General clean-up
- Added Makefile
- Check against servers MD5 sum
- Make it easier to upgrade OS version

Joonas' notes
-------------

Forked off https://github.com/cal/vagrant-ubuntu-precise-64

Made it:

- build a 32 bit Debian stable instead of Ubuntu.
- zero the image before exporting a package (requires a lot of disk space)

Ben's notes
-----------

Forked Carl's repo, and it sort of worked out of the box. Tweaked 
office 12.04 release: 

 - Downloading 12.04 final release. (Today as of this writing)
 - Checking MD5 to make sure it is the right version
 - Added a few more checks for external dependencies, mkisofs
 - Removed wget, and used curl to reduce dependencies
 - Added more output to see what is going on
 - Still designed to work on Mac OS X :)
    ... though it should work for Linux systems too (maybe w/ a bit of porting)

Carl's original README
----------------------

Decided I wanted to learn how to make a vagrant base box.

Let's target Precise Pangolin since it should be releasing soon, I said.

Let's automate everything, I said.

Let's do it all on my macbook, I said.

Woo.
