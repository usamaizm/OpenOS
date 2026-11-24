# OpenOS

OpenOS is an operating-system project built around the principle that users should be able to use, study, modify, and share the software that makes up their system.

## Project principles

- **Open-source software only.** OpenOS aims to include software whose source is available under an OSI-approved open-source license. Proprietary applications and proprietary driver packages are excluded.
- **No proprietary GPU drivers.** OpenOS will use open graphics drivers rather than closed vendor driver packages.
- **Open graphics stack first.** Mesa and Vulkan are first-class parts of the graphics platform. RADV is the preferred Vulkan driver for supported AMD Radeon GPUs; Intel's ANV Vulkan driver is also a target.
- **Respect upstream licenses.** OpenOS's project code is licensed under GNU GPL version 3.0. This does not relicense the Linux kernel or other separately licensed components; each included component retains its own license and notices.
- **User freedom.** The project favors software and distribution choices that let users inspect, modify, rebuild, and share their systems.

## Firmware policy

The policy for firmware files that are distributed only as binaries, without corresponding source code, has not yet been decided. This needs a deliberate decision because some AMD and Intel hardware may require firmware for full functionality. Until that policy is settled, firmware inclusion should be reviewed individually and clearly documented; do not describe binary firmware as open-source software.

## Graphics direction

- Mesa: core open-source graphics stack.
- Vulkan: first-class graphics and compute API.
- RADV: AMD Radeon Vulkan driver.
- ANV: Intel Vulkan driver.
- Proprietary NVIDIA drivers and other proprietary GPU driver packages: excluded from OpenOS.

Hardware support must not override the project's open-source software policy. Where hardware requires excluded components, some features may be unavailable.

## Licensing

The OpenOS project code in this repository is licensed under the GNU General Public License, version 3.0. See [LICENSE](LICENSE). Third-party components are governed by their own upstream licenses.
