# SchemToSchematic - GTNH Fork

Convert WorldEdit 1.13+ `.schem` files to legacy `.schematic` files for use with **GregTech: New Horizons** (Minecraft 1.7.10).

## What this tool does

GTNH uses modded block IDs that go well beyond the vanilla 0-255 range. This fork adds support for those extended IDs so that schematics convert correctly for use in GTNH.

## Usage

1. Open the tool in your browser.
2. Drag and drop one or more `.schem` files (or click to browse).
3. If any blocks are unknown, a form will appear asking for the legacy block ID and metadata for each.
4. Enter the values, click **Convert Files**, and the `.schematic` files will download automatically.
5. Your mappings are saved locally so you won't be prompted again for the same blocks.

## Forked from

[SchemToSchematic](https://github.com/PureGero/SchemToSchematic) by PureGero
