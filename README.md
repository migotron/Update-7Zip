# Update 7-Zip

This PowerShell script automatically updates 7-Zip to the latest version available. It downloads the installer from the official 7-Zip website, removes the old version (if present), and installs the latest version silently.

## Features

- **Checks for existing installation**: The script verifies if 7-Zip is already installed.
- **Uninstalls old versions**: If an older version is found, it is uninstalled automatically.
- **Silent installation**: The script installs the latest version of 7-Zip without requiring user interaction.
- **Cleans up**: The script deletes the installer after the installation is complete.

## Prerequisites

- Windows operating system.
- PowerShell (any recent version should work).
- Administrative privileges to install/uninstall software.

## How to Use

1. **Download the Script**:  
   Download the `Update-7Zip.ps1` file from this repository to your local machine.

2. **Run the Script**:  
   - Right-click on the script and select **Run with PowerShell**, or open a PowerShell window and run the script manually:
     ```powershell
     .\Update-7Zip.ps1
     ```
   - Ensure you run the script as an administrator to allow for software installation/uninstallation.

3. **Wait for Completion**:  
   The script will:
   - Download the latest version of 7-Zip from the official website.
   - Uninstall any previous version of 7-Zip if it is already installed.
   - Install the latest version silently.
   - Clean up the installer file once the installation is complete.

## Script Breakdown

### 1. Check for Existing Installation:
   The script first checks if 7-Zip is already installed by looking for its executable (`7zFM.exe`) in the default installation directory (`C:\Program Files\7-Zip`).

### 2. Uninstall Old Version:
   If an older version of 7-Zip is found, the script uses Windows Management Instrumentation (WMI) to uninstall the software.

### 3. Download the Latest Version:
   The script fetches the latest version of 7-Zip from the official website (`https://www.7-zip.org/a/7z2408-x64.exe`).

### 4. Silent Installation:
   The script installs the latest version of 7-Zip silently using the `/S` argument, meaning no user interaction is needed during installation.

### 5. Cleanup:
   After the installation is complete, the script removes the installer file to avoid clutter.

## Example Output

When you run the script, you should see output similar to the following:

```console
7-Zip is already installed. Removing the old version...
Uninstalling old version of 7-Zip...
Downloading the latest version of 7-Zip...
Installing the latest version of 7-Zip...
Cleaning up the installer file...
7-Zip has been successfully updated to the latest version!
```


## Troubleshooting

- **Permission Issues**: Ensure that you are running the script with administrative privileges.
- **Download Issues**: If the script fails to download the installer, ensure that your system has internet access and that there are no network restrictions blocking the download.

## License

This script is licensed under the **GNU General Public License (GPL) Version 3**. See the [LICENSE](LICENSE) file for more information.

## Acknowledgments

- The script uses the official 7-Zip installer from [7-zip.org](https://www.7-zip.org).
