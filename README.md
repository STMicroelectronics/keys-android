# stm32mp2-keys #

This module is used to store examples of secrets (keys) used during development phase.
It is part of the STMicroelectronics delivery for Android.

## Description ##

This module targets STM32MP25 in OpenSTDroid v6.2.0.
Please see the release notes for more details.

## Documentation ##

* The [release notes][] provide information on the release.
[release notes]: https://wiki.st.com/stm32mpu/wiki/STM32_MPU_OpenSTDroid_release_note_-_v6.2.0

## Dependencies ##

This module can't be used alone. It is part of the STMicroelectronics delivery for Android.

## Contents ##

### Replay Protected Memory Block (RPMB) ###
The RPMB provides a secure area where data integrity is ensured by authentication.
The RPMB authentication key must be programmed into the eMMC RPMB controller and fused into OTP.

rpmbk.bin is the default test key used across distributions during development.

```bash
echo "D3EB3EC36E334C9F988CE2C0B85954610D2BCF8664844DF2AB56E6C61BB701E4" > rpmbk.txt
xxd -r -p rpmbk.txt rpmbk.bin
```

### Trusty device master key ###
The base key "Trusty device master key" is used in the derivation of keys required by Android frameworks.

```bash
openssl rand 32  > trusty_dv_k.bin
```

## License ##

This module is distributed under the Apache License, Version 2.0 found in the [LICENSE](./LICENSE) file.
