# Shidochain Tera Upgrade

A comprehensive upgrade script for migrating Shido blockchain nodes to the Tera version.

## Table of Contents

- [Shidochain Tera Upgrade](#shidochain-tera-upgrade)
  - [Table of Contents](#table-of-contents)
  - [Overview](#overview)
  - [Prerequisites](#prerequisites)
    - [System Requirements](#system-requirements)
    - [Software Requirements](#software-requirements)
  - [Installation](#installation)
  - [Usage](#usage)
    - [Running the Upgrade](#running-the-upgrade)
    - [What the Script Does](#what-the-script-does)
  - [Monitoring](#monitoring)
    - [Verify Binary Version](#verify-binary-version)
    - [Check Service Status](#check-service-status)
    - [View Live Logs](#view-live-logs)
    - [View Historical Logs](#view-historical-logs)
  - [Troubleshooting](#troubleshooting)
    - [Common Issues](#common-issues)
    - [Getting Help](#getting-help)
  - [Contributing](#contributing)
  - [License](#license)

## Overview

This repository provides an automated upgrade script for Shido blockchain nodes, facilitating the migration to the Tera version. The script handles the upgrade process while maintaining node integrity and minimizing downtime.

## Prerequisites

### System Requirements

- **CPU**: 4 or more physical CPU cores
- **Storage**: At least 200GB available disk space
- **Memory**: Minimum 16GB RAM
- **Network**: At least 100 Mbps bandwidth
- **OS**: Linux-based system with systemd support

### Software Requirements

- Git
- Bash shell
- Sudo privileges
- Existing Shido blockchain node installation

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/ShidoGlobal/shido-upgrade-v3.3.1.git
   cd shido-upgrade-v3.3.1
   ```

2. Make the upgrade script executable:
   ```bash
   chmod +x upgrade_shido_node.sh
   ```

## Usage

### Running the Upgrade

Execute the upgrade script with appropriate permissions:

```bash
./upgrade_shido_node.sh
```

> **Important**: The script will create an upgrade version folder inside your existing node directory. Ensure you have sufficient disk space and proper backup before proceeding.

### What the Script Does

- Creates backup of current node configuration
- Downloads and installs Tera version components
- Updates node configuration files
- Restarts the blockchain service
- Validates the upgrade process

## Monitoring

### Verify Binary Version

After the upgrade, verify that the binary version is correct:
```bash
./shidod version
```

This should return version `3.3.1`.

### Check Service Status

Monitor the blockchain service status:
```bash
systemctl status shidochain.service
```

### View Live Logs

Follow real-time logs during and after the upgrade:
```bash
journalctl -u shidochain.service -f
```

### View Historical Logs

Check previous log entries:
```bash
journalctl -u shidochain.service --since "1 hour ago"
```

## Troubleshooting

### Common Issues

- **Permission Denied**: Ensure the script has execute permissions (`chmod +x upgrade_shido_node.sh`)
- **Insufficient Space**: Verify available disk space meets requirements
- **Service Fails to Start**: Check logs using `journalctl -u shidochain.service`

### Getting Help

If you encounter issues:
1. Check the logs for error messages
2. Verify system requirements are met
3. Create an issue in this repository with detailed error information

## Contributing

We welcome contributions! Please:
1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Submit a pull request

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---



