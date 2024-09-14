# PR-SnapView Prerequisites

# Requirements tools
- [x] **GitHub CLI (gh)**
- [x] **jq**
- [x] **sed**: Pre-installed on macOS and Linux; requires installation on Windows (available via Git Bash with Git for Windows)
- [x] **Git for Windows** (Windows users only)

## Before using the `PR-SnapView` plugin, ensure that the required tools are installed, and their paths are set correctly:

- **GitHub CLI (gh):** The GitHub CLI must be installed on your system. Installation instructions can be found [here](https://cli.github.com/).
- **jq:** This plugin requires `jq` to process JSON data. Installation instructions can be found at the [jq official site](https://stedolan.github.io/jq/download/).
- **Git for Windows:** For Windows users, install Git for Windows. Installation instructions can be found [here](https://gitforwindows.org/).

You can check the installation and paths by running the following commands:

For Windows use bash from previously installed ```git for windows```
```
command:        path-macOs/Linux:         path-Windows: C:\Program Files\Git
which sed       /usr/bin/sed              \usr\bin\sed.exe
which jq        /usr/local/bin/jq         \usr\bin\jq.exe
which gh        /usr/local/bin/gh         \usr\bin\gh.exe
which bash      /bin/bash                 \bin\bash.exe
```

## Authentication and Authorization

- **GitHub CLI Authentication:** You must be logged into GitHub CLI. This can be done with the following command:
  ```sh
  gh auth login
  ```
- **GitHub Authorization:** Ensure that you are authorized to access the GitHub account you want to use with the plugin.

## Important for Windows Users
- After downloading `jq`, ensure the file name and path are set as follows: 
  - Example installation:
  - Download the binary file (e.g., jq-windows-amd64).
  - Rename it to `jq` and place it in `C:\Program Files\Git\usr\bin\jq.exe`