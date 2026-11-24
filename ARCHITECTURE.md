# OpenOS Architecture — Initial Design Brief

**Status:** Planning document. No kernel or boot architecture is selected by this document.

## Product contract

OpenOS aims to be a multi-architecture operating-system project whose official releases contain only software that meets the project's open-source-only and no-proprietary-binary policy. Hardware support is best-effort; devices requiring excluded firmware or drivers may not work.

## Decisions required before implementation

1. **Kernel strategy:** Decide between an upstream-kernel distribution and an independently developed kernel. This is the largest scope and maintenance decision.
2. **First target:** Select one emulated x86-64 machine as the reproducible reference target before expanding to ARM/AArch64 or RISC-V.
3. **Boot chain:** Specify firmware assumptions, bootloader, kernel image, initramfs, and root filesystem.
4. **Userspace:** Select libc, init/service manager, shell, core utilities, package format, and update mechanism.
5. **Graphics:** Define the initial graphics stack and exact supported driver/firmware policy.
6. **Build system:** Make image construction deterministic and auditable, with a bill of materials and license inventory.

## Suggested system layers

- Firmware and bootloader
- Kernel and device drivers
- Initramfs and early userspace
- Base userspace and service manager
- Package/update/recovery system
- Desktop or shell environment
- Developer and administration tools

## Non-negotiable invariants

- No proprietary binary blobs in official releases.
- Third-party components retain their own licenses and notices.
- Every supported device claim must cite a tested hardware/software combination.
- User-added components are distinct from official project policy.
- Build artifacts must be traceable to source and toolchain inputs.

## First demonstrable milestone

Build and boot a minimal OpenOS image in QEMU, record its exact source inputs, and publish a repeatable build and smoke-test procedure. Only after that milestone should the project expand hardware targets.
