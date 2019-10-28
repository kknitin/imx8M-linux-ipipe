# imx8M-linux-ipipe
A rudimentary Linux kernel with ipipe patches for IMX8M SoC
Thanks to Philippe Gerum's inputs and with some debugging we (me and Sharan yagneswar at MIND music labs, Stockholm)
managed to get a bootable kernel with xenomai on IMX8M mini soc (We used the Compulab module).

Get the ipipe-arm64 kernel for 4.14.78 from the official ipipe-arm64 repo.
You can download the tar ball from here
https://gitlab.denx.de/Xenomai/ipipe-arm64/-/archive/ipipe-core-4.14.78-arm64-2/ipipe-arm64-ipipe-core-4.14.78-arm64-2.tar.gz

From the root directory of the kernel apply the following patches in the below order (remember to pass -p1 option while patching)
1. imx-patches/mainline-ipipe-to-imx-ipipe.patch
2. ipipe-patches/gpc-psci-ipiped.patch
3. imx-patches/0001-uapi-Add-ion.h-to-userspace.patch (this is optional I think)

The second patch was the key to solve the hard lockup we faced.

Note: I haven't tested to build with these patches and test but we use the same patches in our yocto recipes so should work.


