# Dasharo firmware building guide

## Intro

This guide shows how to build Dasharo firmware for NovaCustom devices. It
contains two components:

- [BIOS firmware](#build-dasharo-bios-firmware)
- [EC firmware](#build-dasharo-ec-firmware)

## Requirements

This guide was verified on Ubuntu 22.04. In practice, any Linux distribution
with [Docker](https://www.docker.com/) support should be enough to complete it.

Make sure that you have following packages installed:

- Docker
    + follow [Install Docker Engine on Ubuntu](https://docs.docker.com/engine/install/ubuntu/)
    + follow [Post-installation steps for Linux](https://docs.docker.com/engine/install/linux-postinstall/)
- Git

    ```bash
    sudo apt -y install git
    ```

## Build Dasharo BIOS firmware

1. Clone the Dasharo coreboot repository:

    ```bash
    git clone https://github.com/Dasharo/coreboot.git
    ```

1. Navigate to the source code directory and checkout to the desired revision:

    ```bash
    cd coreboot
    ```

    > Replace `X.Y.Z` with a valid version

    === "NS5x ADL"
        ```bash
        git checkout novacustom_ns5x_adl_vX.Y.Z
        ```

    === "NV4x ADL"
        ```bash
        git checkout novacustom_nv4x_adl_vX.Y.Z
        ```

    === "NS5x TGL"
        ```bash
        git checkout novacustom_ns5x_tgl_vX.Y.Z
        ```

    === "NV4x TGL"
        ```bash
        git checkout novacustom_nv4x_tgl_vX.Y.Z
        ```

1. Checkout submodules:

    ```bash
    git submodule update --init --recursive --checkout
    ```

1. Start docker container:

    === "NS5x ADL"
        ```bash
        docker run --rm -it -u $UID \
           -v $PWD:/home/coreboot/coreboot \
           -w /home/coreboot/coreboot \
           coreboot/coreboot-sdk:2021-09-23_b0d87f753c /bin/bash
        ```

    === "NV4x ADL"
        ```bash
        docker run --rm -it -u $UID \
           -v $PWD:/home/coreboot/coreboot \
           -w /home/coreboot/coreboot \
           coreboot/coreboot-sdk:2021-09-23_b0d87f753c /bin/bash
        ```

    === "NS5x TGL"
        ```bash
        docker run --rm -it -u $UID \
           -v $PWD:/home/coreboot/coreboot \
           -w /home/coreboot/coreboot \
           coreboot/coreboot-sdk:0ad5fbd48d /bin/bash
        ```

    === "NV4x TGL"
        ```bash
        docker run --rm -it -u $UID \
           -v $PWD:/home/coreboot/coreboot \
           -w /home/coreboot/coreboot \
           coreboot/coreboot-sdk:0ad5fbd48d /bin/bash
        ```

1. Inside of the container, configure the build process:

    === "NS5x ADL"
        ```bash
        make distclean && cp configs/config.novacustom_ns5x_adl .config
        ```

    === "NV4x ADL"
        ```bash
        make distclean && cp configs/config.novacustom_nv4x_adl .config
        ```

    === "NS5x TGL"
        ```bash
        make distclean && cp configs/config.novacustom_ns5x_tgl .config
        ```

    === "NV4x TGL"
        ```bash
        make distclean && cp configs/config.novacustom_nv4x_tgl .config
        ```

1. Start the build process:

    ```bash
    make olddefconfig && make
    ```

This will produce a Dasharo binary placed in `build/coreboot.rom`.

## Build Dasharo EC firmware

1. Clone the Dasharo ec repository:

    ```bash
    git clone https://github.com/Dasharo/ec.git
    ```

1. Navigate to the source code directory and checkout to the desired revision:

    ```bash
    cd ec
    ```

    > Replace `X.Y.Z` with a valid version

    === "NS5x ADL"
        ```bash
        git checkout novacustom_ns5x_adl_vX.Y.Z
        ```

    === "NV4x ADL"
        ```bash
        git checkout novacustom_nv4x_adl_vX.Y.Z
        ```

    === "NS5x TGL"
        ```bash
        git checkout novacustom_ns5x_tgl_vX.Y.Z
        ```

    === "NV4x TGL"
        ```bash
        git checkout novacustom_nv4x_tgl_vX.Y.Z
        ```

1. Checkout submodules:

    ```bash
    git submodule update --init --recursive --checkout
    ```

1. Build the EC firmware:

    === "NS5x ADL"
        ```bash
        EC_BOARD_VENDOR=novacustom EC_BOARD_MODEL=ns5x_adl ./build.sh
        ```

        The resulting image will be placed in: `novacustom_ns5x_adl_ec.rom`.

    === "NV4x ADL"
        ```bash
        EC_BOARD_VENDOR=novacustom EC_BOARD_MODEL=nv4x_adl ./build.sh
        ```

        The resulting image will be placed in: `novacustom_nv4x_adl_ec.rom`.

    === "NS5x TGL"
        ```bash
        EC_BOARD_VENDOR=novacustom EC_BOARD_MODEL=ns5x_tgl ./build.sh
        ```

        The resulting image will be placed in: `novacustom_ns5x_tgl_ec.rom`.

    === "NV4x TGL"
        ```bash
        EC_BOARD_VENDOR=novacustom EC_BOARD_MODEL=nv4x_tgl ./build.sh
        ```

        The resulting image will be placed in: `novacustom_nv4x_tgl_ec.rom`.

## Install Dasharo firmware

The Dasharo firmware can be flashed in following ways, depending on your
situation:

- To flash Dasharo for the first time, refer to the
  [initial deployment guide](initial-deployment.md).
- To update Dasharo, refer to the [firmware update guide](firmware-update.md).
