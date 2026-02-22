# SchematicConverterGTNH

Browser-based tool that converts WorldEdit 1.13+ `.schem` files to legacy `.schematic` files for GTNH (Minecraft 1.7.10).

## Project structure

- `index.html` — UI, file handling, custom mapping form, localStorage persistence
- `schemtoschematic.js` — Core conversion logic, `blocksNamespace` lookup table, block state parsing
- `nbt.js` — NBT parser (third-party)
- `zlib.js` — Zlib decompression (third-party)

## Key functions

- `findUnknownBlocks(arrayBuffer, callback, customMappings)` — Scans palette for blocks not in `blocksNamespace` or custom mappings, returns base names
- `_testConvertToLegacyBlockId(namespaceKey, customMappings)` — Non-DOM version of conversion used for unknown block detection
- `convertToLegacyBlockId(namespaceKey)` — Nested inside `schemtoschematic()`, converts 1.13+ block state keys to `(id << 4) | meta`
- `convertBlockData(root)` — Iterates block data, splits combined values into Blocks/Data/AddBlocks arrays

## Custom mapping rotation

Custom-mapped blocks auto-detect rotation from block state properties:
- `facing=` → meta is set to direction value (down=0, up=1, north=2, south=3, west=4, east=5)
- `axis=` → user meta lower 2 bits preserved, upper bits set from axis (y=+0, x=+4, z=+8)

This matches the conventions used by `blocksNamespace` for built-in blocks.

## Do not modify

- `nbt.js`, `zlib.js` — Third-party libraries
