# Kernel Programming Template for macOS + arm64 + VS Code

This repository is a template for developing Linux kernel and/or modules on macOS
running on a Mac with Apple Silicon (arm64) using VS Code.

Each part of this equation is optional, but it's what I used in the
[tutorial](https://mastermakrela.com/kernel/lkp) for compiling the kernel on macOS.

## Setup

This repository assumes you have cloned the kernel source (`v6.5.7`)
into a sibling directory, i.e.:

```bash
.
├── kernel-dev
└── linux
```

## Quickstart

0. Clone this repository
   `git clone https://github.com/mastermakrela/kernel-dev.git`

1. Clone the kernel and compile it

   - how? [Compiling Linux kernel on macOS](https://mastermakrela.com/kernel/lkp/kernel-dev-on-macos)

2. get an image for the VM

   - how? [Development VM](https://mastermakrela.com/kernel/lkp/kernel-dev-on-macos#development-vm)

3. run the VM
   - `./qemu-run.sh`
   - questions? [Running the development VM](https://mastermakrela.com/kernel/lkp/kernel-dev-on-macos#running-the-development-vm)

## Recommended extensions

1. [C/C++](https://marketplace.visualstudio.com/items?itemName=ms-vscode.cpptools) from Microsoft

   Corresponding config file: [`c_cpp_properties.json`](.vscode/c_cpp_properties.json)

2. [Clang-Format](https://marketplace.visualstudio.com/items?itemName=xaver.clang-format)

   Corresponding config file: [`.clang-format`](.clang-format)
   It's a symlink to file that will exist after you get the kernel source.

3. [Makefile Tools](https://marketplace.visualstudio.com/items?itemName=ms-vscode.makefile-tools)

4. [checkpatch](https://marketplace.visualstudio.com/items?itemName=idanp.checkpatch)

   automatically checks your code for kernel style violations

<!--
## Development

First you need a kernel:

1. `cd linux`
2. `make defconfig`
3. `make -j$(nproc)`

If you're on ARM you're good to go, on x86 you need to update the path in [qemu-run.sh](qemu-run.sh)

Now you can open the [module](modules/hello_world/hello_world.c) and start developing.
You can build the module with `make`
and copy it to the VM with `cp *.ko ../../share`.

Test that it works with `insmod hello_world.ko` and `rmmod hello_world.ko` (inside the VM). -->
