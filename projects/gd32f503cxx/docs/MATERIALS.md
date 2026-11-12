# GD32F503Cxx Development Profile

## Purpose

Independent future-development profile for GD32F503C devices. The exact chip
suffix and user's future board are not yet confirmed; `cxx` is a placeholder,
not an asserted device order code. Official GD32F503C-START V1.1 documents and
Demo Suites V1.0.4 are board references, not confirmed user-board facts.

No original C/V project, shared library or V welcome-page code is modified.
No code generation, build, flashing or hardware validation is claimed. No
successful state file is invented. Existing generic Skills are reused; a new
chip-specific Skill is unnecessary.

## Shared Series Resources

The config deliberately references existing F503/F50x series resources under
`platforms/gd32f503vgt6/`; that directory name reflects the first import, not a
restriction to the V package. Do not remove that platform while C uses it.

- `datasheets/GD32F503xx_Datasheet_Rev0.9RC6.pdf`: F503 series datasheet;
  choose the correct package pin table after confirming the full C part number.
- `datasheets/GD32F50x_用户手册_Rev1.4.pdf`: series reference manual.
- `references/application_notes/`: AN092 GPIO, AN250 clock switching,
  AN270 software development and AN278 hardware development.
- `references/errata/`: F50x usage limitations; check device revision applicability.
- `sdk/GD32F50x_Firmware_Library/`: common CMSIS, startup, standard peripherals,
  USB library and linker scripts. Register APIs may be shared; package pins,
  available peripherals and memory size still need device-specific confirmation.

Only the existing-project snapshot contains a second SDK copy, to preserve the
original sibling-library paths without changing any source files.

## C-Specific References

- `references/existing_project/GD32F50Cx_Project/`: unchanged snapshot of the
  supplied original C project, including its `build.sh`.
- `references/existing_project/GD32F50x_Firmware_Library/`: matching sibling SDK.
- `references/demos/GD32F503C_START_Demo_Suites/`: complete official C-START
  examples, Utilities, board documents and change log.
- `schematic/GD32F503C-START-V1.1.pdf`: official reference-board schematic copy.
- `references/demos/GD32F503C_START_Demo_Suites/Docs/User Guide/`: English and
  Chinese official user guides.
- `App/outputs/`: reserved for future Skill results; not a copied V state.

Sources:

- `/home/kylonxu/work/core/5_cloud_cam/GD32_RTOS_BR01_r001/GD32_SDK/GD32F50Cx_Project`
- Its sibling `GD32F50x_Firmware_Library`.
- Official Demo originally supplied in `temp/GD32F50x_Demo_Suites_V1.0.4.7z`,
  extracted under the assistant V project's reference directory.

Board support header `Utilities/gd32f503c_start.h` defines LED1=PB5,
LED2=PC13, LED3=PB4, wakeup key=PA0, USART0 TX=PA9 and RX=PA10. These are
reference-code mappings, not substitutes for schematic/device verification.
Do not copy the V-EVAL PC7/PC8/PC9 LED map or assume its EXMC LCD is on C-START.

## Blocking Checks Before Development or Flashing

1. Confirm the full C part number, package, Flash/RAM and actual board.
2. The supplied Keil project target is `GD32F503C_START`, but its Device and SVD
   device references still name `GD32F503RG`, not a confirmed C part. Its CPU
   descriptor claims 1 MiB Flash and 128 KiB RAM. Keep this as reference evidence,
   not an authoritative C memory map. Do not auto-build/flash from it yet.
3. The supplied GCC script selects `gd32f503xG_flash.ld`. Confirm this capacity
   matches the real C device before using it. Original scripts remain untouched.
4. No real SVD was found in the supplied materials. Acquire the official F50x
   device pack/SVD if needed; a Keil path reference is not the SVD itself.
5. Confirm RTOS, architecture, toolchain, debug probe and desired features.

No `schematic_path`, SVD, functional-spec or active IDE path is configured.
After confirming the official C-START board, `schematic_path` can be set to
`schematic/GD32F503C-START-V1.1.pdf`; otherwise supply the actual board schematic.
Absent RTOS/architecture/build/flash values may take framework defaults, so this
profile is a materials entry point, not permission to generate or deploy code.
Global tool paths still retain Windows defaults. Framework S7b does not directly
support a `build.sh`-only build system. A C snapshot is read-only reference, not
an automatically synchronized checkout of the formal C source.

## Entry Point

Use `projects/gd32f503cxx/config.json` for future Skill requests. Before requesting
edits, identify the formal code location and confirm the blocking checks above.
The formal C code can remain in its original repository; it need not be cloned
into this assistant project. Do not run V firmware on the C board.
