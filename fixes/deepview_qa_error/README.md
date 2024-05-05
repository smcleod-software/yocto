The bbappend file in this folder fixes the following QA error when building with bitbake:

ERROR: QA Issue: /usr/lib/python3.10/site-packages/bin/deepview-modelclient contained in package deepview-rt 
requires /workdir/build_xwayland/tmp/work/armv8a-fslc-linux/deepview-rt/2.4.46-aarch64-r0/recipe-sysroot-native/usr/bin/nativepython3, 
but no providers found in RDEPENDS:deepview-rt? [file-rdeps]

To fix, copy the bbappend file to the following location (assumes docker-yocto-build as build root):
docker-yocto-build/sources/meta-freescale-ml/recipes-libraries/deepview-rt

For further info, see the following link/topic:
https://community.nxp.com/t5/i-MX-Processors/bitbake-imx-image-full-FAILED-for-imx-linux-kirkstone-imx-5-15/m-p/1657601#M206551