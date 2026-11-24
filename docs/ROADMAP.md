# OpenOS — Founding Roadmap

**Status:** Founding document. This roadmap turns the principles stated in
[README.md](../README.md) into a phase plan. It records only what the
README and [LICENSE](../LICENSE) already decide, and lists as open
questions everything they leave undecided. The staged engineering
milestones live in [ROADMAP.md](../ROADMAP.md); the initial design brief
lives in [ARCHITECTURE.md](../ARCHITECTURE.md).

## Commitments (already decided)

These are stated in the README and bind every later phase:

- **Open-source software only.** Official OpenOS releases include
  open-source software. Proprietary applications, proprietary drivers,
  closed-source firmware, and other proprietary binary blobs are excluded.
- **No binary blobs, even at a cost.** Official releases must not bundle
  proprietary firmware or other closed binary components, even when
  excluding them limits hardware functionality.
- **Best-effort hardware support.** OpenOS does not guarantee that every
  device or feature will work. Hardware that requires proprietary
  components may be unsupported or only partially functional.
- **GPLv3 project code.** OpenOS project code is licensed under the GNU
  General Public License, version 3.0. This does not relicense the Linux
  kernel or other separately licensed components; each component retains
  its own license and notices, and upstream licenses are respected.
- **Multi-architecture, within the policy.** OpenOS is intended to support
  multiple processor architectures where the system can be built and
  maintained in accordance with the open-source-only and no-binary-blob
  policies: x86-64 and ARM / AArch64 on compatible platforms, other
  architectures when they can meet the same requirements.
- **RISC-V is a strategic priority,** because the RISC-V instruction-set
  architecture is openly specified. Implementations whose hardware designs
  and supporting documentation are also openly available are preferred.
  An open instruction-set architecture does not by itself make a chip,
  board, firmware, or peripheral open; the two must be distinguished.
- **Graphics direction.** Mesa is the core open-source graphics stack and
  Vulkan is a first-class graphics and compute API. RADV (AMD Radeon) and
  ANV (Intel) are the Vulkan driver targets. Nouveau may be included for
  NVIDIA hardware only where it can operate without proprietary firmware
  or other binary blobs; NVIDIA's proprietary driver stack and firmware
  are excluded. The no-proprietary-component policy applies the same way
  across networking, wireless, storage, processors, and motherboards.
- **User freedom does not change official policy.** Users may modify their
  own installations, including adding components they choose; such
  additions are user modifications, not official OpenOS content.
- **Vendor cooperation is encouraged.** Hardware vendors are encouraged to
  publish open specifications, source code, open firmware, and
  upstream-compatible drivers, toward an open hardware ecosystem of
  openly documented, inspectable, and modifiable designs.

## Phases

### Phase 1 — Definition (current phase)

The project's principles, architecture strategy, and graphics direction
are recorded in the README. Repository conventions (editor configuration,
text/binary handling, pull-request review) are in place. No
operating-system implementation exists yet, and no claim of a bootable
system is made.

### Phase 2 — Foundation choices

Resolve the open decisions listed below: kernel strategy, first target
architecture and reference hardware, boot chain, userspace foundations,
and package management. Every choice must be checked against the
commitments above before it is recorded — in particular, no choice may
introduce a proprietary binary component into an official release.

### Phase 3 — First build

Produce a minimal bootable image for the first reference target using
only permitted components, following the staged milestones in
[ROADMAP.md](../ROADMAP.md): a repeatable build, a documented boot chain,
a complete component and license inventory, and an audit of the image for
non-free components.

### Phase 4 — Broadening

Expand architecture coverage (with RISC-V as the strategic priority) and
open driver support incrementally, validate the Mesa / Vulkan graphics
paths on real hardware, and publish hardware compatibility based on
tested evidence — documenting, rather than hiding, the devices the
no-blob policy leaves unsupported.

## Open decisions

The README leaves the following undecided. Each is a question for the
project maintainer; nothing in this document answers them.

1. **Kernel strategy:** Will OpenOS be built on an upstream kernel (the
   README's licensing notes contemplate the Linux kernel without choosing
   it) or on an independently developed kernel?
2. **First target architecture and order:** RISC-V is the strategic
   priority, but which architecture and reference hardware come first for
   the initial build, and in what order do the others follow?
3. **Firmware boundary:** Official releases must not bundle proprietary
   firmware. Where exactly is the line for firmware that resides on the
   hardware itself — for example platform firmware or CPU microcode the
   hardware requires before any OpenOS component runs?
4. **Boot chain:** What firmware assumptions, bootloader, and root
   filesystem will the first build use?
5. **Userspace foundations:** Which libc, init / service manager, shell,
   and core utilities will the base system use?
6. **Package management:** What package format and update mechanism will
   the system use, and what are the update, rollback, and recovery
   procedures?
7. **Desktop or shell environment:** The README sets a graphics stack but
   no user environment. What desktop or shell direction, if any, does the
   project adopt?
8. **Graphics sequencing:** RADV, ANV, and blob-free Nouveau are all
   named targets. Which are in scope for the first build, and which
   follow later?
9. **Hardware-support evidence:** What testing standard decides that a
   device or platform counts as supported in the published compatibility
   information?
