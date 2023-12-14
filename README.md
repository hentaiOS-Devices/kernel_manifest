![Banner](assets/kmhead.png)

# Kernel Manifest

This repository provides the manifest for [kernels](https://source.android.com/devices/architecture/kernel) that used for building hentaiOS. Kernel sources can be acquired using [Repo](https://source.android.com/setup/develop/repo#init) and should be built without further configuration by running `build/build.sh` from the root of your source checkout.

## Downloading sources and build tools

Use [repo](https://source.android.com/setup/develop/repo#init) to download the sources, toolchain, and build scripts. Some kernels require sources from multiple git repositories, while others require only single source. Using the `repo` approach ensures a correct source directory setup.

Download the sources for the appropriate branch

```bash
mkdir android-kernel && cd android-kernel
```

```bash
repo init -u https://github.com/hentaiOS-Devices/kernel_manifest.git -b BRANCH
```

```bash
repo sync
```

The following table lists the `BRANCH` names for kernels available through this method

| Device                                                       | Binary path in hentaiOS tree                                                                                                                                | Repo branches                                 |
|--------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------|
| Mi 10 Mi 10 Pro Mi 10T (Pro) Mi 10 Ultra POCO F2 Pro POCO F3 | device/xiaomi/umi-kernel device/xiaomi/cmi-kernel device/xiaomi/apollo-kernel device/xiaomi/cas-kernel device/xiaomi/lmi-kernel device/xiaomi/alioth-kernel | android-msm-gourami-4.19-ursamoon-uq1a |
| Pixel 6 Pixel 6 Pro Pixel 6a Pixel 7 Pixel 7 Pro                         | device/google/raviole-kernel                                                                                                                                | android-gs-5.10-ursamoon-uq1a          |
## Building the kernel

Then build the kernel with:

```bash
build/build.sh
```

The kernel binary, modules, and corresponding image are located in the `out/BRANCH/dist` directory.
