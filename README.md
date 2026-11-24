# OpenOS

OpenOS is a multi-architecture operating-system project built around software freedom, hardware transparency, and the ability to inspect, modify, rebuild, and share the system.

## Core principles

- **Open-source software only.** Official OpenOS releases include open-source software. Proprietary applications, proprietary drivers, closed-source firmware, and other proprietary binary blobs are excluded.
- **No binary blobs.** Official releases must not bundle proprietary firmware or other closed binary components, even when excluding them limits hardware functionality.
- **Best-effort hardware support.** OpenOS does not guarantee that every device or feature will work. Hardware that requires proprietary components may be unsupported or only partially functional.
- **User freedom.** Users may modify their own installations, including adding components they choose. Such additions are user modifications and do not change the official OpenOS policy.
- **Vendor cooperation.** Hardware vendors are encouraged to publish open specifications, source code, open firmware, and upstream-compatible drivers.
- **Respect upstream licenses.** OpenOS project code is licensed under GNU GPL version 3.0. This does not relicense the Linux kernel or other separately licensed components; each component retains its own license and notices.

## Architecture strategy

OpenOS is intended to support multiple processor architectures where the operating system can be built and maintained in accordance with its open-source-only and no-binary-blob policies.

- **x86-64:** Support compatible systems without requiring proprietary drivers or firmware.
- **ARM / AArch64:** Support compatible platforms that meet the same requirements.
- **RISC-V:** A strategic priority because the RISC-V instruction-set architecture is openly specified. Prefer implementations whose hardware designs and supporting documentation are also openly available.
- **Other architectures:** Welcome when they can meet the project's openness and maintenance requirements.

An open instruction-set architecture does not automatically make every processor implementation open hardware. OpenOS should distinguish open architectural specifications from the openness of an individual chip, board, firmware, and peripheral implementation.

## Graphics and hardware support

- Mesa is the core open-source graphics stack.
- Vulkan is a first-class graphics and compute API.
- RADV is the AMD Radeon Vulkan driver target.
- ANV is the Intel Vulkan driver target.
- Nouveau may be included for NVIDIA hardware only where it can operate without proprietary firmware or other binary blobs.
- NVIDIA's proprietary driver stack and proprietary firmware are excluded from official OpenOS releases.

The same policy applies across graphics, networking, wireless, storage, processors, motherboards, and other hardware: no proprietary binary components in official releases. Where hardware requires excluded components, functionality may be unavailable. Hardware compatibility is best-effort, not guaranteed.

## Open hardware direction

OpenOS supports the broader goal of an open hardware ecosystem: openly documented interfaces, inspectable designs, modifiable implementations, and vendor cooperation. Prefer hardware whose specifications and implementation can be independently studied and improved.

## Licensing

The OpenOS project code in this repository is licensed under the GNU General Public License, version 3.0. See [LICENSE](LICENSE). Third-party components remain governed by their own upstream licenses.


## Engineering documents

- [ARCHITECTURE.md](ARCHITECTURE.md) — initial system design and decisions required.
- [ROADMAP.md](ROADMAP.md) — staged bootable-image and release milestones.


## Ecosystem integration

This project is part of a set of independent, interoperable open projects. See the [ecosystem integration contract](https://github.com/usamaizm/AIDB/blob/main/docs/ECOSYSTEM_INTEGRATION.md) for its role, interoperability boundaries, and integration principles.


## Contributor attribution

Human and AI contributors must follow the [contributor identity and attribution protocol](CONTRIBUTOR_PROTOCOL.md). Keep the authenticated GitHub account separate from a contributor's self-declared identity; never guess who performed earlier work.


## Contributor attribution

Human and AI contributors should follow the [shared contributor attribution protocol](https://github.com/usamaizm/AIDB/blob/main/docs/CONTRIBUTOR_ATTRIBUTION.md). Keep the authenticated GitHub actor separate from a contributor's self-declared identity; never infer authorship from account metadata or commit style.
