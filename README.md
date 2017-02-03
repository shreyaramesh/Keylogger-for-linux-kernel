# Keylogger-for-linux-kernel
Script to run a key logger than records each keystroke and saves it into a file. Caesar's cipher has been implemented to encrypt the keystrokes entered into the file.

Output will be the encrypted version of the pressed keys.

For example,

	Hello_Linux =>  Ly``]_TAB_~[.pb 



keylogger
=========

Linux kernel level keylogger.

To build:
>make

To install the keylogger module:
>sudo insmod keylogger.ko

Test whether the module is loaded:
>lsmod | grep "keylogger"

Test whether the logging is happening:
>cat /var/log/kern.log
The log file will show the keystrokes logged after the module has been loaded.

To uninstall the keylogger module:
>sudo rmmod keylogger



TO DO:

1. Figure out how to get status of Capslock key. Since this module could be loaded when the capslock is already enabled, we cannot depend on just listening for Capslock key press event.

2. Keep configuration info like keycode to ascii mapping separately. And load it at runtime.

