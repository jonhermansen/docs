# Release Notes

Following Release Notes describe the status of Open Source Software development
for Dasharo Tools Suite.

For details about our release process, please read [Dasharo Standard Release
Process](../dev-proc/standard-release-process.md).

<center>
[Subscribe to Dasharo Tools Suite Newsletter]
[newsletter]{.md-button .md-button--primary .center}
</center>

[newsletter]: https://newsletter.3mdeb.com/subscription/ttzqCq9fy

## v1.1.1 - 2023-02-20

### Images

[USB bootable DTS v1.1.1 image][USB_DTS_v1.1.1]{ .md-button }
[sha256][USB_DTS_sha_v1.1.1]{ .md-button }
[sha256.sig][USB_DTS_sig_v1.1.1]{ .md-button }

[DTS v1.1.1 ISO image][ISO_DTS_v1.1.1]{ .md-button }
[sha256 ISO][ISO_DTS_sha_v1.1.1]{ .md-button }
[sha256.sig ISO][ISO_DTS_sig_v1.1.1]{ .md-button }

[USB_DTS_v1.1.1]: https://3mdeb.com/open-source-firmware/DTS/v1.1.1/dts-base-image-v1.1.1.wic.gz
[USB_DTS_sha_v1.1.1]: https://3mdeb.com/open-source-firmware/DTS/v1.1.1/dts-base-image-v1.1.1.wic.gz.sha256
[USB_DTS_sig_v1.1.1]: https://3mdeb.com/open-source-firmware/DTS/v1.1.1/dts-base-image-v1.1.1.wic.gz.sha256.sig
[ISO_DTS_v1.1.1]: https://3mdeb.com/open-source-firmware/DTS/v1.1.1/dts-base-image-v1.1.1.iso
[ISO_DTS_sha_v1.1.1]: https://3mdeb.com/open-source-firmware/DTS/v1.1.1/dts-base-image-v1.1.1.iso.sha256
[ISO_DTS_sig_v1.1.1]: https://3mdeb.com/open-source-firmware/DTS/v1.1.1/dts-base-image-v1.1.1.iso.sha256.sig

  See how to verify hash and signature on [this
  video](https://youtu.be/RF-NYcZM9JI). It works the same way with ISO image.

### Changelog

* Fixed Dasharo zero-touch initial deployment on MSI PRO Z690-A, added DDR5
  target with dedicated firmware.
* Blocked Dasharo zero-touch initial deployment on platforms where Dasharo
  firmware was detected.
* Added couple QoL improvements for Dasharo zero-touch initial deployment:
    - added platform verification step (show detected device information),
    - added firmware verification step (show hash of using binary),
    - added progress bar on first instructions,
    - used reboot as default behavior after successful flashing.
* Added improvements for HCL report.
* Added DTS ISO format image, and documentation about
  [VentoyOS](./documentation.md#run-dts-using-ventoyos) usage.
* Improved `README` of the `meta-dts` repository.
* Added service to run shell [commands from
  iPXE](./documentation.md#run-commands-from-ipxe-shell).
* Added instructions for building PoC image with [enabled UEFI Secure
  Boot](./documentation.md#build-image-with-uefi-secure-boot-support) support.

## v1.1.0 - 2022-11-02

### Images

[USB bootable DTS v1.1.0 image][USB_DTS_v1.1.0]{ .md-button }
[sha256][USB_DTS_sha_v1.1.0]{ .md-button }
[sha256.sig][USB_DTS_sig_v1.1.0]{ .md-button }

[USB_DTS_v1.1.0]: https://3mdeb.com/open-source-firmware/DTS/v1.1.0/dts-base-image-v1.1.0.wic.gz
[USB_DTS_sha_v1.1.0]: https://3mdeb.com/open-source-firmware/DTS/v1.1.0/dts-base-image-v1.1.0.wic.gz.sha256
[USB_DTS_sig_v1.1.0]: https://3mdeb.com/open-source-firmware/DTS/v1.1.0/dts-base-image-v1.1.0.wic.gz.sha256.sig

### Changelog

* Added [Dasharo zero-touch
  initial deployment](./documentation.md#dasharo-zero-touch-initial-deployment)
  for a couple of supported platforms.
* Added multiple HCL report improvements, e.g. dump information about TPM, ME.
* Refactored Dasharo Tools Suite [documentation](./overview.md).
* Added possibility to rollback using firmware dumped in HCL report.
* Added documentation about [building Dasharo Tools Suite
  image](./documentation.md#building).
* Added Github Actions to automate new version building.
* Added new tools: cbfstool, cbmem, futil, intelmetool (all from [Dasharo
  coreboot fork](https://github.com/Dasharo/coreboot/tree/coreboot-utils)),
  [binwalk](https://github.com/ReFirmLabs/binwalk),
  [uefi-firmware-parser](https://github.com/theopolis/uefi-firmware-parser),
  [mei-amt-check](https://github.com/mjg59/mei-amt-check).
* Updated flashrom to version
  [dasharo-v1.2.2](https://github.com/Dasharo/flashrom/tree/dasharo-v1.2.2).
* Deploying iPXE boot artifacts on
  [boot.dasharo.com](https://boot.dasharo.com/dts/).
* Sharing build cache on [cache.dasharo.com](https://cache.dasharo.com/yocto/dts/).

## v1.0.2 - 2022-10-19

### Images

[USB bootable DTS v1.0.2 image][USB_DTS_v1.0.2]{ .md-button }
[sha256][USB_DTS_sha_v1.0.2]{ .md-button }
[sha256.sig][USB_DTS_sig_v1.0.2]{ .md-button }

[USB_DTS_v1.0.2]: https://3mdeb.com/open-source-firmware/DTS/v1.0.2/dts-base-image-ce-v1.0.2.wic.gz
[USB_DTS_sha_v1.0.2]: https://3mdeb.com/open-source-firmware/DTS/v1.0.2/dts-base-image-ce-v1.0.2.wic.gz.sha256
[USB_DTS_sig_v1.0.2]: https://3mdeb.com/open-source-firmware/DTS/v1.0.2/dts-base-image-ce-v1.0.2.wic.gz.sha256.sig

  See how to verify hash and signature on [this
  video](https://youtu.be/oTx2iStxXOE).

### Changelog

* Added new vendor-specific menu entry, which is displayed only on supported
  platforms. For now, NovaCustom menu was added for NovaCustom NV4x and
  NovaCustom NS5x/7x laptops.
* DTS version is now printed in the main menu.
* `ec_transition` script now supports NovaCustom NV4x laptops and automatically
  download firmware used for transition both for NovaCustom NV4x NV4x and
  NovaCustom NS5x/7x laptops, [firmware
  transition](documentation.md#ec-transition) documentation is updated.
* Added kernel configuration to silence terminal logs by default (change
  `loglevel` to 1).
* Enabled GOOGLE_MEMCONSOLE_COREBOOT kernel configuration to ease getting
  firmware logs.

## v1.0.1 - 2022-09-02

### Images

[USB bootable DTS v1.0.1 image][USB_DTS_v1.0.1]{ .md-button }
[sha256][USB_DTS_sha_v1.0.1]{ .md-button }
[sha256.sig][USB_DTS_sig_v1.0.1]{ .md-button }

[USB_DTS_v1.0.1]: https://3mdeb.com/open-source-firmware/DTS/v1.0.1/dts-base-image-ce-v1.0.1.wic.gz
[USB_DTS_sha_v1.0.1]: https://3mdeb.com/open-source-firmware/DTS/v1.0.1/dts-base-image-ce-v1.0.1.wic.gz.sha256
[USB_DTS_sig_v1.0.1]: https://3mdeb.com/open-source-firmware/DTS/v1.0.1/dts-base-image-ce-v1.0.1.wic.gz.sha256.sig

  See how to verify hash and signature on [this video.](https://youtu.be/oTx2iStxXOE)

### Changelog

* Added `system76_ectool` to enable Embedded Controller [firmware
  updating](./documentation.md#ec-update).
* Added `ec_transition` script, which helps with full Dasharo/Embedded
  Controller [firmware transition](./documentation.md#ec-transition) for
  NovaCustom NS5x/7x.
* First public release: [meta-dts-ce](https://github.com/Dasharo/meta-dts-ce).

## v1.0.0 - 2022-08-09

### Images

[USB bootable DTS v1.0.0 image][USB_DTS_v1.0.0]{ .md-button }
[sha256][USB_DTS_sha_v1.0.0]{ .md-button }

[USB_DTS_v1.0.0]: https://3mdeb.com/open-source-firmware/DTS/v1.0.0/dts-base-image-ce-v1.0.0.wic.gz
[USB_DTS_sha_v1.0.0]: https://3mdeb.com/open-source-firmware/DTS/v1.0.0/dts-base-image-ce-v1.0.0.wic.gz.sha256

  ```bash
  # assuming all files have been downloaded to the same directory without
  # changing names
  sha256sum -c [sha256 file]
  ```

### Changelog

* Added auto-login functionality.
* Added user menu.
* [Dasharo HCL
  Report](../glossary.md#dasharo-hardware-compatibility-list-report), which adds
  the ability to automatically dump device information and send it to 3mdeb
  servers.
* Possibility to manually [update the Dasharo
  firmware](./documentation.md#firmware-update).
* [Bootable via iPXE](./documentation.md#bootable-over-a-network).
* [Bootable via USB](./documentation.md#bootable-usb-stick).
* Tested on NovaCustom NV4x, Dell OptiPlex 7010/9010.
