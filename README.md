# About

This repository provides WSL kernel settings to enable USB cameras and gamepads. It also includes a `.wslconfig` file to apply the custom kernel. \
Modifying your WSL kernel can potentially cause serious issues with your computer. \
I offer no warranty of any kind regarding the use or implementation of the contents of this repository.  Use at your own risk.

# Usage

1. Clone this repository.
2. Within WSL, clone the Microsoft WSL2-Linux-Kernel repository: `git clone https://github.com/microsoft/WSL2-Linux-Kernel.git`
3. Navigate into the cloned repository: `cd WSL2-Linux-Kernel`
4. Place the `.config` file from this repository into the `WSL2-Linux-Kernel/` directory.
5. Build the kernel: `sudo make -j$(nproc) && sudo make modules_install -j$(nproc) && sudo make install -j$(nproc)`
6. Copy the compiled kernel (`vmlinux`) to your Windows home directory: `cp vmlinux /mnt/c/Users/<windows-user-name>/vmlinux`
7. Place the `.wslconfig` file from this repository into your Windows home directory.
8. Shut down WSL: `wsl --shutdown`
9. Reboot your computer.
10. Verify the kernel has been updated by running `uname -a` in WSL.  Successful kernel modification will be indicated by `-microsoft-standard-WSL2+` at the end of the output, along with a build date matching your build time after the `#`.

# Information
If you want to know what I did, please refer https://qiita.com/N622/items/5c7cecd625e23c6e3911 
