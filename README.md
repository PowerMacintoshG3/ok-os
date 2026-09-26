#  OkOS v1.0

OkOS is a **custom-engineered** operating system layer built directly on top of legacy Microsoft DOS system architectures (`MSDOS.SYS`, `IO.SYS`, and `COMMAND.COM`). It infuses retro computing environments with fortified hardware driver stacks, automated cryptographic security integrity checks, and a native assembly-level defensive watchdog layer. 

To handle base system deployment, hardware mapping, and memory unlocking, the platform incorporates **CuteMouse**, the **HX DOS Extender**, and native command binaries (**XCOPY**, **MEM**, and **DISPLAY**) pulled directly from the FreeDOS project open-source base.

---

##  Key Architectural Pillars

* **Core Subsystem Abstraction:** Seamlessly mounts on top of native real-mode DOS system structures to expand internal functionality.
* **The Gatekeeper Shield (`gatekeeper.com`):** A high-performance, self-defending 16-bit x86 Terminate-and-Stay-Resident (TSR) assembly driver. It hooks directly into the Interrupt 21h vector layer to block all deletion, renaming, or modification attempts targeting core system sectors mid-air with an immediate hardware-level "Access Denied" return.
* **Cryptographic Integrity Verification:** Automated boot-time system auditing using a master SHA256 file manifest (`drive_c.sha`) to prevent silent directory corruption or unauthorized modification loops.
* **Autonomous Disaster Recovery:** Built-in automated extraction pipelines (`install.bat`) capable of executing full system self-healing loops straight from pristine localized storage snapshots (`install.zip`).

---

##  System Roadmap & 32-Bit Protected Mode

While the core initialization drivers operate natively inside **16-Bit Real Mode** for maximum motherboard BIOS compatibility, OkOS breaks past the ancient 640 KB conventional RAM barrier by leveraging 32-Bit Protected Mode interfaces (DPMI). 

A dedicated 32-bit C++ single-window Graphical User Interface framework (`explorer.exe`) featuring retro light-gray taskbars, active desktop shortcuts, and real-time BIOS clock widgets is currently stable in build testing under the HX Extender layer, with full distribution shell support arriving in the next release cycle.

---

##  Licensing & Attributions

This project is officially licensed under the terms of the **GNU General Public License v3.0 (GPLv3)**. See the `LICENSE.TXT` file inside the root directory for full open-source legal details.

### Third-Party Components Used:
* **CuteMouse (`CTMOUSE.EXE`)** - Real-mode x86 hardware mouse pointer driver (GPL).
* **HX DOS Extender Framework** - Win32 API translation server for DOS protected-mode execution (LGPL).
* **FreeDOS Utilities (`XCOPY.EXE`, `MEM.EXE`, `DISPLAY.EXE`)** - Base commands used for deployment, memory management diagnostics, and hardware font management (GPL).
