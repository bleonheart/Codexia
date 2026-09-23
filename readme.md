<p align="center">
 <strong>Useful Python Scripts</strong><br/>
 A collection of developer utilities for Garry's Mod, GLua, Lilia, documentation, localization, asset processing, and code analysis.<br/>
 Built to automate repetitive maintenance tasks and make large Lua projects easier to audit, clean, document, and ship.<br/>
</p>

<p align="center">
 <img src="https://img.shields.io/badge/Python-3.10%2B-blue?logo=python&logoColor=white" alt="Python 3.10+" />
 <a href="https://github.com/bleonheart/Useful-Python-Scripts/stargazers">
  <img src="https://img.shields.io/github/stars/bleonheart/Useful-Python-Scripts?style=social" alt="GitHub Stars" />
 </a>
</p>

<h1 align="center">Useful Python Scripts</h1>

---

## Overview

This repository contains standalone Python tools created for day-to-day development and maintenance work around Garry's Mod and GLua projects.

The scripts cover:

- Localization auditing and cleanup
- Hook discovery and documentation
- Lua code analysis and cleanup
- Network string generation
- Garry's Mod asset inspection
- Addon merging and splitting
- Documentation maintenance
- Function and variable analysis
- Folder and content organization

Most tools are intentionally independent so you can copy or run only the script you need.

## Quick Start

Clone the repository:

```bash
git clone https://github.com/bleonheart/Useful-Python-Scripts.git
cd Useful-Python-Scripts
```

Run a script directly:

```bash
python files/remove_lua_comments.py <directory>
```

Some tools expose command-line arguments while others use configurable paths near the top of the script.

## Requirements

- Python 3.10 or newer
- Additional packages are only required by specific tools

Common optional dependencies:

```bash
python -m pip install srctools humanize
```

## Tools

### Localization

- `localization_analysis_report.py`  
  Analyze framework and module language files, report missing or unused localization keys, and optionally clean unused entries.

- `localization_analysis_report_fixed.py`  
  Extended localization analysis with improved pattern detection and reporting.

- `remove_duplicate_language_keys.py`  
  Remove duplicate localization entries.

### Hooks & Documentation

- `hooks_discover_update_docs.py`  
  Discover hooks in Lua code, compare them with documentation, and update generated hook data.

- `hooks_doc_usage_report.py`  
  Compare documented hooks against their real usage in the codebase.

- `format_gamemode_hooks.py` / `format_gamemode_hooks_v2.py`  
  Normalize hook documentation formatting.

- `add_extensive_examples.py`  
  Add expanded examples to hook documentation.

- `missinghooks.py`  
  Find hooks that are used in Lua but missing from documentation.

- `cleanup_docs.py`  
  Clean generated module documentation directories.

### Networking

- `generate_network_strings.py`  
  Discover network strings and generate Lua registration code.

### Lua Utilities

- `lua_bundle.py`  
  Combine Lua files from a directory into a single output file.

- `lua_stack.py`  
  Stack Lua source files using explicit source and output arguments.

- `lua_item_table_builder.py`  
  Build consolidated item tables from per-file `ITEM.*` definitions.

- `remove_lua_comments.py`  
  Remove line and block comments from Lua files.

- `strip_sh_prefix.py`  
  Remove the `sh_` prefix from matching Lua filenames.

- `remove_trailing_underscores.py`  
  Clean trailing underscore arguments from Lua definitions and calls.

### Code Analysis

- `compare_functions.py`  
  Compare functions and produce documentation-coverage analysis.

- `function_comparison_report.py`  
  Generate function comparison reports across Lua files.

- `find_lia_types.py`  
  Discover unique `lia.*` function namespaces used by a gamemode.

- `unused_variable_finder.py`  
  Run GLuaLint across multiple directories and collect unused-variable results.

- `replace_unused_vars.py`  
  Replace reported unused variables with underscores.

- `unusedvarscleaner.py`  
  Batch-process unused-variable reports.

- `unusedvarfinder_cleaner.py`  
  Lightweight unused-variable finder and cleanup utility.

### Asset Management

- `extract_cdmaterials.py`  
  Extract `cdmaterials` paths from Source engine model files.

- `gmod_asset_cleaner.py`  
  Locate and optionally remove unused sounds, images, particles, models, and materials.

- `addon_merge_and_split.py`  
  Merge addon folders and split the resulting content into deployment-sized packs.

- `addon_merge_clean_split.py`  
  Merge, clean, report, and split Garry's Mod content in one workflow.

- `folder_splitter.py`  
  Separate gmpublisher content into Lua and material containers.

- `convert_panels_format.py`  
  Convert panel configuration data between formats.

### Miscellaneous

- `privilege_report.py`  
  Compare used privileges against registered privileges.

- `remove_duplicate_keys.py`  
  Remove duplicate key/value lines while preserving the first occurrence.

## Example

Generate network-string registration code:

```bash
python files/generate_network_strings.py <lua_root> <output_lua>
```

Remove Lua comments recursively:

```bash
python files/remove_lua_comments.py <directory>
```

Compare documented and implemented functions:

```bash
python files/compare_functions.py <source_dir> <output_dir>
```

## Notes

Many scripts were created for real project-maintenance workflows and may assume a Garry's Mod or Lilia-style directory structure. Review configurable paths and options before running tools that modify files.

For destructive cleanup scripts, use a backup or version-controlled working tree so changes can be reviewed and reverted.

## Contributing

Improvements and additional utilities are welcome.

1. Fork the repository
2. Create a feature branch
3. Add or improve a utility
4. Test it against representative input
5. Open a pull request with a clear description of the workflow it supports
