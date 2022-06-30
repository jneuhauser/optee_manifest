# Repo manifest for OP-TEE development
This git contains repo manifests to be able to clone all source code needed to
be able to setup a full OP-TEE developer build.

All official OP-TEE documentation has moved to http://optee.readthedocs.io. The
information that used to be here in this git can be found under [manifests].

// OP-TEE core maintainers

[manifests]: https://optee.readthedocs.io/en/latest/building/gits/build.html#manifests

# Usage of this manifest for STM32MP1 based DHSOM

See the official [build] instruction for more details.

```
$ mkdir -p <optee-project>
$ cd <optee-project>
$ repo init -u https://github.com/jneuhauser/optee_manifest.git -m stm32mp1.xml -b dev/stm32mp1-dhsom
$ repo sync -j4
$ cd build
$ make -j2 toolchains
$ make PLATFORM=stm32mp1-157C_DHCOM_PDK2 all -j$(nproc)
$ dd if=../out/bin/sdcard.img of=/dev/sdX conv=fdatasync status=progress
```

[build]: https://optee.readthedocs.io/en/latest/building/gits/build.html
