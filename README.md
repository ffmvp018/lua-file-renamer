# lua-file-renamer

A small Lua utility script that scans a folder, previews or applies renames, and updates file names in batches.

## Features

- Add a prefix to each file name
- Add a suffix before the extension
- Replace text inside names
- Convert names to uppercase or lowercase
- Preview changes with `--dry-run`

## Requirements

- Lua 5.4 or newer

## Usage

```bash
lua rename_files.lua <folder> [options]
```

### Options

- `--prefix <text>`: add a prefix to each file name
- `--suffix <text>`: add a suffix before the extension
- `--replace <old>=<new>`: replace a text fragment in the name (repeatable)
- `--lowercase`: convert names to lowercase
- `--uppercase`: convert names to uppercase
- `--dry-run`: show changes without renaming files
- `--help`: show help

## Examples

```bash
lua rename_files.lua ./photos --prefix IMG_ --dry-run
lua rename_files.lua ./downloads --suffix _final --replace ' '=_
lua rename_files.lua ./archive --lowercase
```

## Notes

- Files are processed only in the target directory.
- Renames are applied in a predictable alphabetical order.
- The script uses the system's built-in file commands to list files and rename them.
