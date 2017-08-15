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
- integration check
- encrypt/decrypt single files

usage
-------------------------

### mount/umount

`fusecry mount SOURCE_DIR MOUNT_POINT`  
`fusecry umount MOUNT_POINT`  
Data copied to mount point will remain encrypted in source directory.  

### single file encryption

`fusecry encrypt INPUT_FILE OUTPUT_FILE`  
`fusecry decrypt INPUT_FILE OUTPUT_FILE`  
`fusecry toggle TOGGLE_FILE [TOGGLE_FILE [TOGGLE_FILE ...]]`  
Toggle will encrypt raw files and decrypt encrypted files and delete originals
in the process. It asumes files with '.fcry' extension are encrypted ones.

known deficiencies and limitations
-------------------------

- file names are not being encrypted by design
- block size is fixed to 4096 (will become option to change)

future plans and missing features (in no particular order)
-------------------------

- threading
- choice and detection of chunk sizes
- password change (bulk re-encryption)

