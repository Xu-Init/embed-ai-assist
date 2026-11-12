# GD32F503VGT6 Materials

## Scope

This import classifies user-provided documents and existing code. Original files
are retained unchanged. No generation, compilation, flashing, or hardware
verification has been performed. Existing binaries are reference artifacts only.

The reference Keil project identifies GD32F503VG, Cortex-M33, 1 MiB Flash and
128 KiB RAM. Its enclosing demo directory and GCC script name GD32F503VGT6.
Confirm the actual board marking before using these settings for new firmware.

## Classification

- `platforms/gd32f503vgt6/datasheets/`: datasheet and reference manual.
- `platforms/gd32f503vgt6/references/application_notes/`: AN092, AN250,
  AN270 and AN278 application notes.
- `platforms/gd32f503vgt6/references/errata/`: chip usage limitations.
- `platforms/gd32f503vgt6/sdk/GD32F50x_Firmware_Library/`: complete supplied
  firmware library, preserving CMSIS, startup, linker and peripheral files.
- `references/existing_project/`: unchanged project snapshot and its sibling
  firmware library, preserving original relative build paths.
- `references/demos/`: original official Demo Suites archive, its nested package
  and complete extracted contents under `unpacked/GD32F50x_Demo_Suites_V1.0.4/`.
  The V-EVAL `Projects/` directory is configured as the demo input.
- `schematic/`: reserved for board schematics, not yet supplied.
- `App/outputs/`: reserved for future Skill results; no successful state invented.

The two AN278 PDFs in the source directory have identical SHA256:
`ac158d6e68bcc42a4d3a0d0870f63cd41e2db296a52ce66a45595fd91d46e56c`.
Only the underscore-named copy is imported; both source files are retained.

## Official Board References

The Demo archive contains C/K/R START and V-EVAL board documentation. For the
V package, use the following paths under
`references/demos/unpacked/GD32F50x_Demo_Suites_V1.0.4/GD32F503V_EVAL_Demo_Suites/`:

- `Docs/Schematic/GD32F503V-EVAL-V1.1.pdf`: official evaluation-board schematic.
- `Docs/User Guide/`: English and Chinese board user guides.
- `Projects/`: official peripheral demos.
- `Utilities/`: official board support code.

These are reference-board documents, not confirmed schematics for the user's
actual board, so `schematic_path` is deliberately unset. Both archive layers
were inspected; neither contains an SVD or device-pack file. The nested package's
published SHA256 is
`cb9adb22b53f53d2ac92c669f54dc5ad5ccebe208ed912ca9e3c78a62c45fc4a`.

## Sources

- Documents: `/home/kylonxu/work/core/5_cloud_cam/s1_skills/temp`
- Project: `/home/kylonxu/work/core/5_cloud_cam/GD32_RTOS_BR01_r001/GD32_SDK/GD32F50Vx_Project`
- SDK: the project's sibling `GD32F50x_Firmware_Library` directory.

## Pending Inputs

1. Board schematic source or searchable vector PDF, including connected sheets.
2. Confirm chip marking and project/board name.
3. Functional requirements and initial bring-up goals.
4. Confirm bare metal or RTOS, desired architecture and BootLoader requirements.
5. Confirm Linux GCC versus Windows Keil and actual debug probe.
6. Supply `GD32F50x.svd` or the official GD32F50x device pack if available.

SVD describes chip registers; SWD is the hardware debug interface. The supplied
Keil project references `GigaDevice.GD32F50x_DFP.1.0.0` and
`$$Device:GD32F503VG$SVD/GD32F50x.svd`, but that reference is not an embedded file.

No schematic, SVD, functional-spec or active IDE path is configured until a real
input is available. RTOS, architecture, build system and flash tool remain
unconfirmed; omitted fields can take framework defaults, so confirm them before
running code-generation or deployment Skills. The reference GCC `build.sh` is
not a Makefile and has not been integrated into S7b. Global tool paths still
contain Windows defaults and have not been changed.