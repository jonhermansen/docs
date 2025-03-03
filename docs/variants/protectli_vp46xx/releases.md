# Release Notes

Following Release Notes describe status of Open Source Firmware development for
Protectli VP46xx

For details about our release process please read
[Dasharo Standard Release Process](../../dev-proc/standard-release-process.md).

<center>
[Subscribe to Protectli VP46xx Dasharo Release Newsletter]
[newsletter]{.md-button .md-button--primary .center}
</center>

Test results for this platform can be found
[here](https://docs.google.com/spreadsheets/d/1wI0qBSLdaluayYsm_lIa9iJ9LnPnCOZ9eNOyrKSc-j4/edit?usp=sharing).

## v1.0.19 - 2022-12-08

### Changed

- ME is now disabled by default (ME soft-disable)
- vboot is now run as separate verstage (previously was run inside bootblock)
- increased pre-RAM console buffer to fit more early cbmem logs

### Binaries

[protectli_vp4630_vp4650_v1.0.19.rom][protectli_vp4630_vp4650_v1.0.19.rom_file]{.md-button}
[sha256][protectli_vp4630_vp4650_v1.0.19.rom_hash]{.md-button}
[sha256.sig][protectli_vp4630_vp4650_v1.0.19.rom_sig]{.md-button}

[protectli_vp4670_v1.0.19.rom][protectli_vp4670_v1.0.19.rom_file]{.md-button}
[sha256][protectli_vp4670_v1.0.19.rom_hash]{.md-button}
[sha256.sig][protectli_vp4670_v1.0.19.rom_sig]{.md-button}

See how to verify signatures on [this video](https://asciinema.org/a/388861)

### SBOM (Software Bill of Materials)

- [coreboot based on c6ee1509da revision 9034fb12](https://github.com/Dasharo/coreboot/tree/9034fb12)
- [edk2 based on 7f90b9cd revision e31b7a71](https://github.com/Dasharo/edk2/tree/e31b7a71)
- [iPXE for EFI revision 988d2](https://github.com/ipxe/ipxe/tree/988d2c13cdf0f0b4140685af35ced70ac5b3283c)
- VP4670: [Cometlake1 FSP 9.0.7B.20](https://github.com/intel/FSP/tree/12160fe64bc1caaba3c2d6be44da0cd8787a2561/CometLakeFspBinPkg/CometLake1)
- VP4630 and VP4650: [Cometlake2 FSP 9.2.7B.20](https://github.com/intel/FSP/tree/12160fe64bc1caaba3c2d6be44da0cd8787a2561/CometLakeFspBinPkg/CometLake2)
- Intel i225 EFI driver version 0.10.4,
  SHA256: 2d234ecf629fc10dc0c291a1390de3d27a05c6ecbd935628b6ff154f386d061e
- Management Engine: Custom image based on ME 14.0.47.1558,
  SHA256: 7fa37e108176c9a2d0df60c93b10b3ad9c7725f1f82b87197a2991208c4cffec
- microcode:
    + CPU signature: 0x0806EC, Date: 17.11.2021, Revision: 0xF0
    + CPU signature: 0x0A0660, Date: 15.11.2021, Revision: 0xF0
    + CPU signature: 0x0A0661, Date: 16.11.2021, Revision: 0xF0

## v1.0.18 - 2022-11-16

Test results for this release can be found
[here](https://docs.google.com/spreadsheets/d/1wI0qBSLdaluayYsm_lIa9iJ9LnPnCOZ9eNOyrKSc-j4/edit#gid=1613384145).

### Added

- Support for VP4650 and VP4670 platforms
- Platform will beep 12 times and blink HDD led on critical firmware errors

### Changed

- Disabled Intel PTT (fTPM)
- [Removed workaround for graphics power management as the issue no longer reproduces on newer revision of the hardware](https://github.com/Dasharo/dasharo-issues/issues/26)
- Binaries are built with coreboot-sdk 2021-09-23_b0d87f753c (was 0ad5fbd48d)
- Open-source graphics initialization with libgfxinit instead of proprietary and
  closed FSP GOP driver

### Binaries

[protectli_vp4630_vp4650_v1.0.18.rom][protectli_vp4630_vp4650_v1.0.18.rom_file]{.md-button}
[sha256][protectli_vp4630_vp4650_v1.0.18.rom_hash]{.md-button}
[sha256.sig][protectli_vp4630_vp4650_v1.0.18.rom_sig]{.md-button}

[protectli_vp4670_v1.0.18.rom][protectli_vp4670_v1.0.18.rom_file]{.md-button}
[sha256][protectli_vp4670_v1.0.18.rom_hash]{.md-button}
[sha256.sig][protectli_vp4670_v1.0.18.rom_sig]{.md-button}

See how to verify signatures on [this video](https://asciinema.org/a/388861)

### SBOM (Software Bill of Materials)

- [coreboot based on c6ee1509da revision ed9f6fe0](https://github.com/Dasharo/coreboot/tree/ed9f6fe0)
- [edk2 based on 7f90b9cd revision e31b7a71](https://github.com/Dasharo/edk2/tree/e31b7a71)
- [iPXE for EFI revision 988d2](https://github.com/ipxe/ipxe/tree/988d2c13cdf0f0b4140685af35ced70ac5b3283c)
- VP4670: [Cometlake1 FSP 9.0.7B.20](https://github.com/intel/FSP/tree/12160fe64bc1caaba3c2d6be44da0cd8787a2561/CometLakeFspBinPkg/CometLake1)
- VP4630 and VP4650: [Cometlake2 FSP 9.2.7B.20](https://github.com/intel/FSP/tree/12160fe64bc1caaba3c2d6be44da0cd8787a2561/CometLakeFspBinPkg/CometLake2)
- Intel i225 EFI driver version 0.10.4,
  SHA256: 2d234ecf629fc10dc0c291a1390de3d27a05c6ecbd935628b6ff154f386d061e
- Management Engine: Custom image based on ME 14.0.47.1558,
  SHA256: 7fa37e108176c9a2d0df60c93b10b3ad9c7725f1f82b87197a2991208c4cffec
- microcode:
    + CPU signature: 0x0806EC, Date: 17.11.2021, Revision: 0xF0
    + CPU signature: 0x0A0660, Date: 15.11.2021, Revision: 0xF0
    + CPU signature: 0x0A0661, Date: 16.11.2021, Revision: 0xF0

## v1.0.17 - 2022-08-17

Test results for this release can be found
[here](https://docs.google.com/spreadsheets/d/19YnBLxHw0mae-SQ2xl6BgPeims9hH_oVGwyF70pj9EY/edit#gid=1614315669).

### Added

- [Tools for resigning Vboot images with one RW partition](../../../guides/vboot-signing/)

### Changed

- Set thermal throttling temperature to 80 degrees
- Disabled UEFI Secure Boot by default

### Fixed

- Platform rebooting every 56 minutes
- Incorrect menu labels displayed in network boot menu
- Built-in audio jack does not work

### Binaries

[protectli_vault_cml_v1.0.17.rom_file][protectli_vault_cml_v1.0.17.rom_file]{.md-button}
[protectli_vault_cml_v1.0.17.rom_hash][protectli_vault_cml_v1.0.17.rom_hash]{.md-button}
[protectli_vault_cml_v1.0.17.rom_sig][protectli_vault_cml_v1.0.17.rom_sig]{.md-button}

See how to verify signatures on [this video](https://asciinema.org/a/388861)

### SBOM (Software Bill of Materials)

- [coreboot based on 4.16 revision d662831d](https://github.com/Dasharo/coreboot/tree/d662831d)
- [edk2 based on 7f90b9cd revision 576aa6a4](https://github.com/Dasharo/edk2/tree/576aa6a4)
- [iPXE for EFI revision 988d2](https://github.com/ipxe/ipxe/tree/988d2c13cdf0f0b4140685af35ced70ac5b3283c)
- [Cometlake2 FSP 9.2.7B.20](https://github.com/intel/FSP/tree/10eae55b8eb0febfa2dfabf4017701b072866170/CometLakeFspBinPkg/CometLake2)
- Intel i225 EFI driver version 0.10.4,
  SHA256: 2d234ecf629fc10dc0c291a1390de3d27a05c6ecbd935628b6ff154f386d061e
- Management Engine: Custom image based on ME 14.0.47.1558,
  SHA256: 7fa37e108176c9a2d0df60c93b10b3ad9c7725f1f82b87197a2991208c4cffec
- microcode:
    + CPU signature: 0x0806EC, Date: 28.04.2021, Revision: 0xEC
    + CPU signature: 0x0A0660, Date: 28.04.2021, Revision: 0xEA
    + CPU signature: 0x0A0661, Date: 29.04.2021, Revision: 0xEC

## v1.0.16 - 2022-07-13

Test results for this release can be found
[here](https://docs.google.com/spreadsheets/d/19YnBLxHw0mae-SQ2xl6BgPeims9hH_oVGwyF70pj9EY/edit#gid=1614315669).

### Added

- [Vboot Verified Boot](../../../guides/vboot-signing/)
- [TPM Measured Boot](https://docs.dasharo.com/unified-test-documentation/dasharo-security/203-measured-boot/)
- [Vboot recovery notification in UEFI Payload](https://docs.dasharo.com/unified-test-documentation/dasharo-security/201-verified-boot/)
- [UEFI Shell](https://docs.dasharo.com/unified-test-documentation/dasharo-compatibility/30P-uefi-shell/)
- [UEFI Secure Boot](https://docs.dasharo.com/unified-test-documentation/dasharo-security/206-secure-boot/)
- [Intel ME soft disable](https://docs.dasharo.com/unified-test-documentation/dasharo-security/20F-me-neuter/)
- [BIOS flash protection for Vboot recovery region](https://docs.dasharo.com/unified-test-documentation/dasharo-security/20J-bios-lock-support/)

### Changed

- [Changed supported CPUs to Comet Lake stepping 2](https://github.com/intel/FSP/tree/master/CometLakeFspBinPkg#comet-lake-binary-differences)

### Fixed

- [i225 network controller initialization takes too much time](https://github.com/Dasharo/dasharo-issues/issues/65)
- [CVE-2022-29264](https://cve.mitre.org/cgi-bin/cvename.cgi?name=2022-29264)

### Binaries

[protectli_vault_cml_v1.0.16.rom][v1.0.16_rom]{.md-button}
[sha256][v1.0.16_hash]{.md-button}
[sha256.sig][v1.0.16_sig]{.md-button}

See how to verify signatures on [this video](https://asciinema.org/a/388861)

### SBOM (Software Bill of Materials)

- [coreboot based on 4.16 revision dfaaf44d](https://github.com/Dasharo/coreboot/tree/dfaaf44d)
- [edk2 based on 7f90b9cd revision 5345a611](https://github.com/Dasharo/edk2/tree/5345a611)
- [iPXE for EFI revision 988d2](https://github.com/ipxe/ipxe/tree/988d2c13cdf0f0b4140685af35ced70ac5b3283c)
- [Cometlake2 FSP 9.2.7B.20](https://github.com/intel/FSP/tree/10eae55b8eb0febfa2dfabf4017701b072866170/CometLakeFspBinPkg/CometLake2)
- Intel i225 EFI driver version 0.10.4,
  SHA256: 2d234ecf629fc10dc0c291a1390de3d27a05c6ecbd935628b6ff154f386d061e
- Management Engine: Custom image based on ME 14.0.47.1558,
  SHA256: 7fa37e108176c9a2d0df60c93b10b3ad9c7725f1f82b87197a2991208c4cffec
- microcode:
    + CPU signature: 0x0806EC, Date: 28.04.2021, Revision: 0xEC
    + CPU signature: 0x0A0660, Date: 28.04.2021, Revision: 0xEA
    + CPU signature: 0x0A0661, Date: 29.04.2021, Revision: 0xEC

## v1.0.13 - 2022-03-22

### Added

- UEFI boot support
- i225 network controller network boot support
- Customized boot menu keys
- Customized setup menu keys
- Configurable boot order
- Configurable boot options

### Changed

- ME version to 14.0.47.1558

### Known issues

- [i225 network controller initialization takes too much time](https://github.com/Dasharo/dasharo-issues/issues/65)

### Binaries

[protectli_vault_cml_v1.0.13.rom][v1.0.13_rom]{.md-button}
[sha256][v1.0.13_hash]{.md-button}
[sha256.sig][v1.0.13_sig]{.md-button}

See how to verify signatures on [this video](https://asciinema.org/a/388861)

### SBOM (Software Bill of Materials)

- [coreboot based on 4.16 revision 546e1c86](https://github.com/Dasharo/coreboot/tree/546e1c86)
- [edk2 based on 7f90b9cd revision 7f90b9cd](https://github.com/Dasharo/edk2/tree/7f90b9cd)
- [iPXE for EFI revision 988d2](https://github.com/ipxe/ipxe/tree/988d2c13cdf0f0b4140685af35ced70ac5b3283c)
- [Cometlake1 FSP 9.0.7B.20](https://github.com/intel/FSP/tree/10eae55b8eb0febfa2dfabf4017701b072866170/CometLakeFspBinPkg/CometLake1)
- Intel i225 EFI driver version 0.9.03,
  SHA256: 63e77b237dc9a8aacdd7465675ee88afc01dad3204156a91a0976a4ad1ed5b00
- Management Engine: Custom image based on ME 14.0.47.1558,
  SHA256: 7fa37e108176c9a2d0df60c93b10b3ad9c7725f1f82b87197a2991208c4cffec
- microcode:
    + CPU signature: 0x0806EC, Date: 28.04.2021, Revision: 0xEC
    + CPU signature: 0x0A0660, Date: 28.04.2021, Revision: 0xEA

[newsletter]: https://newsletter.3mdeb.com/subscription/n2EpSxtqL
[protectli_vp4630_vp4650_v1.0.19.rom_file]: https://3mdeb.com/open-source-firmware/Dasharo/protectli_vault_cml/v1.0.19/protectli_vp4630_vp4650_v1.0.19.rom
[protectli_vp4630_vp4650_v1.0.19.rom_hash]: https://3mdeb.com/open-source-firmware/Dasharo/protectli_vault_cml/v1.0.19/protectli_vp4630_vp4650_v1.0.19.rom.sha256
[protectli_vp4630_vp4650_v1.0.19.rom_sig]: https://3mdeb.com/open-source-firmware/Dasharo/protectli_vault_cml/v1.0.19/protectli_vp4630_vp4650_v1.0.19.rom.sha256.sig
[protectli_vp4670_v1.0.19.rom_file]: https://3mdeb.com/open-source-firmware/Dasharo/protectli_vault_cml/v1.0.19/protectli_vp4670_v1.0.19.rom
[protectli_vp4670_v1.0.19.rom_hash]: https://3mdeb.com/open-source-firmware/Dasharo/protectli_vault_cml/v1.0.19/protectli_vp4670_v1.0.19.rom.sha256
[protectli_vp4670_v1.0.19.rom_sig]: https://3mdeb.com/open-source-firmware/Dasharo/protectli_vault_cml/v1.0.19/protectli_vp4670_v1.0.19.rom.sha256.sig
[protectli_vp4630_vp4650_v1.0.18.rom_file]: https://3mdeb.com/open-source-firmware/Dasharo/protectli_vault_cml/v1.0.18/protectli_vp4630_vp4650_v1.0.18.rom
[protectli_vp4630_vp4650_v1.0.18.rom_hash]: https://3mdeb.com/open-source-firmware/Dasharo/protectli_vault_cml/v1.0.18/protectli_vp4630_vp4650_v1.0.18.rom.sha256
[protectli_vp4630_vp4650_v1.0.18.rom_sig]: https://3mdeb.com/open-source-firmware/Dasharo/protectli_vault_cml/v1.0.18/protectli_vp4630_vp4650_v1.0.18.rom.sha256.sig
[protectli_vp4670_v1.0.18.rom_file]: https://3mdeb.com/open-source-firmware/Dasharo/protectli_vault_cml/v1.0.18/protectli_vp4670_v1.0.18.rom
[protectli_vp4670_v1.0.18.rom_hash]: https://3mdeb.com/open-source-firmware/Dasharo/protectli_vault_cml/v1.0.18/protectli_vp4670_v1.0.18.rom.sha256
[protectli_vp4670_v1.0.18.rom_sig]: https://3mdeb.com/open-source-firmware/Dasharo/protectli_vault_cml/v1.0.18/protectli_vp4670_v1.0.18.rom.sha256.sig
[protectli_vault_cml_v1.0.17.rom_file]: https://3mdeb.com/open-source-firmware/Dasharo/protectli_vault_cml/v1.0.17/protectli_vault_cml_v1.0.17.rom
[protectli_vault_cml_v1.0.17.rom_hash]: https://3mdeb.com/open-source-firmware/Dasharo/protectli_vault_cml/v1.0.17/protectli_vault_cml_v1.0.17.rom.sha256
[protectli_vault_cml_v1.0.17.rom_sig]: https://3mdeb.com/open-source-firmware/Dasharo/protectli_vault_cml/v1.0.17/protectli_vault_cml_v1.0.17.rom.sha256.sig
[v1.0.16_rom]: https://3mdeb.com/open-source-firmware/Dasharo/protectli_vault_cml/v1.0.16/protectli_vault_cml_v1.0.16.rom
[v1.0.16_hash]: https://3mdeb.com/open-source-firmware/Dasharo/protectli_vault_cml/v1.0.16/protectli_vault_cml_v1.0.16.rom.sha256
[v1.0.16_sig]: https://3mdeb.com/open-source-firmware/Dasharo/protectli_vault_cml/v1.0.16/protectli_vault_cml_v1.0.16.rom.sha256.sig
[v1.0.13_rom]: https://3mdeb.com/open-source-firmware/Dasharo/protectli_vault_cml/protectli_vault_cml_v1.0.13.rom
[v1.0.13_hash]: https://3mdeb.com/open-source-firmware/Dasharo/protectli_vault_cml/protectli_vault_cml_v1.0.13.rom.sha256
[v1.0.13_sig]: https://3mdeb.com/open-source-firmware/Dasharo/protectli_vault_cml/protectli_vault_cml_v1.0.13.rom.sha256.sig
