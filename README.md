# fusionctl

fusionctl is a command-line tool and Python library for managing VMware Fusion virtual machines on macOS.

Created by pmrsec.

---

## Features

- List running and stopped VMs
- Start, stop, reset, and suspend VMs
- Manage multiple VM search locations
- Configuration stored in standard OS-specific paths
- Works as both a CLI and importable Python module

---

## Installation

### From PyPI (after publishing)

```bash
pip install fusionctl
```

### From source

```bash
git clone https://github.com/pmrsec/fusionctl.git
cd fusionctl
pip install -e .
```

---

## Usage

### Command Line

```bash
fusionctl
```

Direct commands:
```bash
fusionctl list
fusionctl start <index>
fusionctl stop <index>
fusionctl reset <index>
fusionctl suspend <index>
fusionctl paths
fusionctl add-path <directory>
fusionctl remove-path <directory>
```

---

### Python API Example


```python
from fusionctl import VMManager

manager = VMManager()
vms = manager.list_vms()

if vms:
    manager.start(vms[0].path)
```

---

## Configuration

VM search paths are saved automatically in:

- macOS: ~/Library/Application Support/fusionctl/config.json
- Linux: ~/.config/fusionctl/config.json
- Windows: %APPDATA%/fusionctl/config.json

---

## Requirements

- macOS
- VMware Fusion installed with vmrun available in PATH

Linux and Windows support for VMware Workstation is planned for future versions.

---

## License

MIT License  
Copyright (c) 2024 pmrsec

---

## Contributions

Issues and pull requests are welcome.
