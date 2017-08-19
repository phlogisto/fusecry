
fusecry 
==================================================
[![Build Status](https://travis-ci.org/phlogisto/fusecry.png)](https://travis-ci.org/phlogisto/fusecry)
[![Gitter](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/fusecry/Lobby)

FUSE based encrypted (AES.MODE\_CBC) filesystem and encryption tool

requirements
-------------------------

- Linux
- python >= 3.4

install
-------------------------

### install from pypi
`pip3 install fusecry`  

### install from github
`pip3 install -U git+https://github.com/phlogisto/fusecry.git`  

### autocompletion
In addition, add the following to your `.bashrc` to enable autocompletion:  
`eval "$(register-python-argcomplete fusecry)"`

features
-------------------------

- mount
- encrypt/decrypt single files
- real time integrity check
- filesystem check

usage
-------------------------

### mount/umount

`fusecry mount SOURCE_DIR MOUNT_POINT`  
`fusecry umount MOUNT_POINT`  
Data copied to mount point will remain encrypted in source directory.  

### single file encryption

`fusecry encrypt INPUT_FILE OUTPUT_FILE -c FUSECRY_MOUNT_SETTINGS`  
`fusecry decrypt INPUT_FILE OUTPUT_FILE -c FUSECRY_MOUNT_SETTINGS`  
FUSECRY\_MOUNT\_SETTINGS is stored in ROOT directory. If you call the command
without existing settings file, it will be created.

### fsck

`fusecry fsck ROOT`
ROOT is the source dir that is to be mounted. Make sure it is not mounted
during fsck or you might get false-positive error detection.

known deficiencies and limitations
-------------------------

- file names are not being encrypted by design
- block size is fixed to 4096

future plans and missing features (in no particular order)
-------------------------

- choice and detection of block sizes
- password change (bulk re-encryption)

