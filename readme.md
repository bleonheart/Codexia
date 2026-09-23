<p align="center">
 <strong>Codexia — GLua & Garry's Mod Developer Toolkit</strong><br/>
 A practical collection of automation, analysis, cleanup, documentation, and asset-processing tools.<br/>
 Built to remove repetitive maintenance work from large Lua projects and server content pipelines.
</p>

<p align="center">
 <img src="./logo.svg" alt="Codexia Logo" width="220" />
</p>

<p align="center">
 <img src="https://img.shields.io/badge/Python-3.10%2B-blue?logo=python&logoColor=white" alt="Python 3.10+" />
 <a href="https://github.com/bleonheart/Codexia/stargazers">
  <img src="https://img.shields.io/github/stars/bleonheart/Codexia?style=social" alt="GitHub Stars" />
 </a>
</p>

---

## Overview

Codexia is a toolbox of standalone utilities created around real Garry's Mod, GLua, Lilia, documentation, localization, and content-maintenance workflows.

The repository focuses on small tools that can be used independently instead of requiring one large application or framework.

Typical uses include:

- Auditing and cleaning GLua code
- Generating and validating documentation
- Finding hooks, functions, privileges, and network strings
- Checking localization coverage
- Processing Source-engine assets
- Merging and splitting addon collections
- Automating repetitive repository maintenance

## Quick Start

Clone the repository:

```bash
git clone https://github.com/bleonheart/Codexia.git
cd Codexia
```

Most utilities live in the `files` directory and can be executed directly:

```bash
python files/remove_lua_comments.py <directory>
```

Some scripts expose command-line arguments while others contain configurable paths or values near the top of the file.

## Tool Categories

### GLua & Code Analysis

Utilities for inspecting, comparing, cleaning, and transforming Lua code.

- `compare_functions.py`
- `function_comparison_report.py`
- `find_lia_types.py`
- `remove_lua_comments.py`
- `remove_trailing_underscores.py`
- `replace_unused_vars.py`
- `strip_sh_prefix.py`
- `unused_variable_finder.py`
- `unusedvarfinder_cleaner.py`
- `unusedvarscleaner.py`

### Hooks & Documentation

Tools for discovering hooks, maintaining generated documentation, and comparing documentation with actual code usage.

- `add_extensive_examples.py`
- `cleanup_docs.py`
- `fix_hook_names.py`
- `format_gamemode_hooks.py`
- `format_gamemode_hooks_v2.py`
- `hooks_discover_update_docs.py`
- `hooks_doc_usage_report.py`
- `missinghooks.py`

### Localization

Utilities for finding missing, duplicated, or unused language entries.

- `localization_analysis_report.py`
- `localization_analysis_report_fixed.py`
- `remove_duplicate_language_keys.py`

### Networking & Framework Utilities

Tools for common Garry's Mod and Lilia development tasks.

- `generate_network_strings.py`
- `privilege_report.py`
- `lua_item_table_builder.py`
- `convert_panels_format.py`
- `convert_panels_to_individual_files.py`

### Asset & Content Processing

Utilities for Source-engine assets and large addon collections.

- `addon_merge_and_split.py`
- `addon_merge_clean_split.py`
- `extract_cdmaterials.py`
- `folder_splitter.py`
- `gmod_asset_cleaner.py`

### Lua Packaging

Small utilities for combining or reorganizing Lua source trees.

- `lua_bundle.py`
- `lua_stack.py`

### General Cleanup

Additional maintenance tools used across projects.

- `remove_asterisks.py`
- `remove_duplicate_keys.py`
- `test_at_patterns.py`

## Example Workflows

Remove Lua comments recursively:

```bash
python files/remove_lua_comments.py <directory>
```

Generate network-string registration code:

```bash
python files/generate_network_strings.py <lua_root> <output_lua>
```

Compare documented and implemented functions:

```bash
python files/compare_functions.py <source_dir> <output_dir>
```

## Requirements

- Python 3.10 or newer
- Additional dependencies vary by script

Some utilities may use optional packages such as:

```bash
python -m pip install srctools humanize
```

Review the script before running it to determine whether additional dependencies or project-specific paths are required.

## Safety

Several utilities modify, rename, move, or delete files.

When using cleanup or transformation scripts:

1. Work inside a version-controlled repository or backup
2. Review configuration and input paths
3. Run reporting or analysis modes first when available
4. Inspect the resulting diff before committing changes

## Repository Structure

```text
Codexia/
├── files/
│   ├── addon_merge_and_split.py
│   ├── compare_functions.py
│   ├── generate_network_strings.py
│   ├── gmod_asset_cleaner.py
│   ├── remove_lua_comments.py
│   └── ...
└── readme.md
```

## Contributing

Contributions and additional focused utilities are welcome.

1. Fork the repository
2. Create a feature branch
3. Add or improve a utility
4. Test it against representative input
5. Open a pull request describing the workflow and expected behavior

---

<p align="center">
 <strong>Automate the repetitive work. Keep the project work.</strong>
</p>