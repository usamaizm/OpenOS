# OpenOS Roadmap

OpenOS is a multi-architecture, open-source-only operating-system project. This roadmap is a staged engineering plan, not a claim that a bootable system currently exists.

## Stage 0 — Define the buildable target
- [ ] Select the initial architecture and reference hardware (recommend x86-64 in an emulator).
- [ ] Choose the kernel strategy: upstream Linux-based distribution or independent kernel. Record the decision and rationale.
- [ ] Define the official-release policy for firmware, drivers, microcode, and other binary components.
- [ ] Establish reproducible build requirements and supported toolchains.

## Stage 1 — Bootable development image
- [ ] Produce a minimal bootable image in QEMU using only permitted components.
- [ ] Document the boot chain and every included component/license.
- [ ] Add automated image-build and smoke-test workflows.
- [ ] Publish a hardware compatibility matrix with evidence.

## Stage 2 — Usable base system
- [ ] Establish init/service management, storage layout, networking, user accounts, and package management.
- [ ] Define update, rollback, recovery, and installation procedures.
- [ ] Add accessibility and localization foundations.
- [ ] Audit official images for non-free components.

## Stage 3 — Hardware and graphics
- [ ] Add open driver support incrementally.
- [ ] Test Mesa/Vulkan paths on supported hardware.
- [ ] Document unsupported devices where proprietary firmware is required.
- [ ] Track architecture-specific build and runtime coverage.

## Stage 4 — Release engineering
- [ ] Reproducible builds and signed release artifacts.
- [ ] Security response and vulnerability disclosure process.
- [ ] Independent review of licensing and image contents.
- [ ] Stable release criteria, support policy, and upgrade path.

## Release rule

Do not call OpenOS bootable, hardware-supported, secure, or release-ready until that claim is demonstrated by repeatable builds, tests, and published evidence.
