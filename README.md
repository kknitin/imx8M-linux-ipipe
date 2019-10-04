# imx8M-linux-ipipe
A rudimentary Linux kernel with ipipe patches for IMX8M SoC
Thanks to Philippe Gerum's inputs and with some debugging we (me and Sharan yagneswar at MIND music labs, Stockholm) 
managed to get a bootable kernel with xenomai on IMX8M mini soc (We used the Compulab module).

The linux-kernel git submodule is mainline kernel for 4.14.y from IMX repository 
(https://source.codeaurora.org/external/imx/linux-imx; branch = git.kernel.org/linux-stable/linux-4.14.y) 

There are two sets of patches, one for ipipe related stuff and other set is imx related stuff.
We took the mainline branch andd applied the ipipe patch generated from ipipe-arm64 mainline
(because at that time the 4.4.78 patch was not avaialable, now it is you can use that I guess)

Clone  the kernel from above link or just fetch the git submodule contents, then apply the patches in the following order.
1. ipipe-patches/ipipe-4.14.78.patch
2. mainline-ipipe-to-imx-ipipe.patch
3. ipipe-patches/gpc-psci-ipiped.patch

The last patch was the key to solve the hard lockup we faced.
