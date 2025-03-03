# Versioning

Dasharo Releases are versioned using [Semantic Versioning](https://semver.org/)
and [Keep A Changelog](https://keepachangelog.com/en/1.0.0/) to document
changes introduced in new releases.

Major version zero (0.y.z) is for initial development and may not support all
Dasharo Quality Criteria.

The only way to map Dasharo Version to version of Open Source Firmware
framework or other components included in Dasharo Release is through release
notes. Link to Dasharo Release Notes for your hardware platform can be found
in menu on the left side (Supported Hardware->Hardware Model->Releases).

## Dasharo Supporters releases

Dasharo Supporters receive firmware updates more frequently than the community.
Number of updates per year depends on the number of Dasharo Subscriptions sold
and the availability of other funding (e.g., NLNet, corporate sponsors,
community donations) but is less than 2 updates per year. Dasharo Supporters
updates are characterized by a changing patch version (`z`). Fixes and features
introduced in Dasharo Supporters releases will also be available later in
community releases. In short, being a Dasharo Supporter gives an early access to
the newest features and fixes.

## Community releases

Community releases are built and published once a year. Each community release
has a zero patch version (`x.y.0`) and the only changing number is the minor
version `y`.

## Signing keys

In Dasharo we use following rules for keys:

* GPG RSA 4096 for signing and authentication and subkey for encryption
* There few types of naming conventions, which define `Real Name` field and
  chain of trust schemes:
    - Software:
        + Real Name: `<name> open-source software release <version> signing key`
        + Signing key: `3mdeb Open Source Software Master Key <contact@3mdeb.com>`
    - Firmware:
        + Real Name: `<name> open-source firmware release <version> signing key`
        + Signing key: `3mdeb Dasharo Master Key`
    - PC Engines (firmware exception):
        + Real Name: `PC Engines open-source firmware release <version> signing key`
        + Signing key: `3mdeb Open Source Firmware Master Key <contact@3mdeb.com>`
    - Dasharo firmware produced by 3mdeb:
        + Real Name: `Dasharo release <version> compatible with <name> signing key`
        + Signing key: `3mdeb Dasharo Master Key`
    - For Dasharo firmware produced by 3mdeb on customer's behalf:
        + Real Name: `Dasharo open-source firmware <version> for <name> signing key`
        + Signing key: `3mdeb Dasharo Master Key`

`<name>` typically is in form `<vendor> <model>` or just `<vendor>` if we
release firmware for whole line of products which can be support in one binary
e.g. PC Engines. Examples:

* `Dell OptiPlex 7010/9010`
* `ASUS KGPE-D16`
* `MSI MS7D25`
* `NovaCustom`
* `Tuxedo`

Most recent status should be reflected in
[3mdeb-secpack](https://github.com/3mdeb/3mdeb-secpack) repository.
