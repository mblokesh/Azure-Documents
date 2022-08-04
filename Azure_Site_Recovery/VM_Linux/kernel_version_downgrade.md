# The kernel version of the running operating system kernel on the source machine is not supported on the version of the mobility service installed on the source machine.

You may try to downgrade kernel. Here is an example for Ubuntu 21.04
Identify actual kernel with command:

`$ sudo uname -r
5.4.0-1086-azure`

First step is to identify the necessary packages that you need to install. This is done by executing the following command:

`$ sudo apt search linux-azure | grep 5.4.0-1085`

below command will show you the list of installed images:

`$ dpkg --list | grep linux-image`

Afterwards you know which package needs to be installed:

`$ sudo apt install linux-image-5.4.0-1085-azure`

In the next step the actual kernel gets removed:

`$ sudo apt remove linux-image-5.4.0-1086-azure`

if anyother image unsigned remove that aswell:

`$ sudo apt remove linux-image-unsigned-5.4.0-1086-azure`

During the process you confirm with **`No`** that you do not want to abort the removal process:

Kernel removal confirmation window

As the last step you initiate a reboot with 

`$ sudo reboot`

The welcome screen should now state the target kernel version.
Check the kernel version

`$ sudo uname -r
5.4.0-1085-azure`



