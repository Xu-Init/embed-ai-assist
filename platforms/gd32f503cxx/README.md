# GD32F503Cxx Platform Profile

The project entry point is [../../projects/gd32f503cxx/config.json](../../projects/gd32f503cxx/config.json).
See [../../projects/gd32f503cxx/docs/MATERIALS.md](../../projects/gd32f503cxx/docs/MATERIALS.md)
for board references, provenance and unresolved device/build settings.

F503/F50x series datasheets, application notes and SDK are shared through the
existing `../gd32f503vgt6/` import. The project config points to those real files;
this profile intentionally does not duplicate or relocate the shared platform.
The existing V project remains unchanged.

GD32F503C-START has separate schematic, demos and board-support code under
the C project's reference directories. Do not reuse V-EVAL pin maps, memory
assumptions or its LCD application as C hardware facts. A full C device suffix
has not been confirmed and no C-specific generation adapter is certified.
