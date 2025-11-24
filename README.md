# Raspberry Pi OS OCI Builder

This repository downloads official Raspberry Pi OS 32-bit (`armhf`) and 64-bit (`arm64`) disk images then converts them into OCI-compliant container images.

### How to Run

**Raspberry Pi / Apple Silicon** - Runs natively on ARM architectures.

```bash
docker run -it --rm ghcr.io/kth8/rpi-os-lite:latest-arm64
```
```bash
docker run -it --rm ghcr.io/kth8/rpi-os-lite:latest-armhf
```

**x86 PC** - Requires QEMU emulation.

```bash
docker run --rm --privileged multiarch/qemu-user-static --reset -p yes
```
```bash
docker run -it --rm --platform linux/arm64 ghcr.io/kth8/rpi-os-lite:latest-arm64
```
```bash
docker run -it --rm --platform linux/arm/v7 ghcr.io/kth8/rpi-os-lite:latest-armhf
```
