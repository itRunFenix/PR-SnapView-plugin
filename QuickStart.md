# gh-pr-dashboard
### Dashboard for displaying information about Pull Requests for a given author

> **_Please note that any actions or decisions related to pull requests should be taken after reviewing the pull requests directly on GitHub._**
> **_The PR dashboard is intended for informational purposes only and provides an overview of pull requests._**

![pr-dash](docs/images/pr_dash.png)
![pr-dash](docs/images/pr_dash3.png)



`gh-pr-dashboard` is a GitHub CLI extension that generates an HTML dashboard with information about **open** Pull Requests for a given author.


## Requirements

Before using the `gh-pr-dashboard` extension, make sure you have the following installed and follow these steps:

- **GitHub CLI (gh):** The GitHub CLI must be installed on your system. Installation instructions can be found [here](https://cli.github.com/).
- **jq:** This script requires `jq` to process JSON data. You can install `jq` by following the instructions at [jq official site](https://stedolan.github.io/jq/download/).

  Example for macOS using Homebrew:
  ```sh
  brew install jq
  ```
- **GitHub CLI Authentication:** You must be logged into GitHub CLI. This can be done with the following command:
  ```sh
  gh auth login
- **GitHub Authorization:** Ensure that you are authorized to access the GitHub account you want to use with the extension.


## Installation
To install the `gh-pr-dashboard` extension, follow these steps:

### 1. Install the Extension:
```sh
gh extension install <repo-url>
```
#### To install the `gh-pr-dashboard` extension, use the following command:
```sh
gh extension install https://github.com/pzadora-appfire/gh-pr-dashboard.git
```
You should see a response like this:

```
⣷Cloning into '/Users/piotr.zadora/.local/share/gh/extensions/gh-pr-dashboard'...
⣻remote: Enumerating objects: 6, done.
remote: Counting objects: 100% (6/6), done.
remote: Compressing objects: 100% (5/5), done.
remote: Total 6 (delta 0), reused 3 (delta 0), pack-reused 0
Receiving objects: 100% (6/6), done.
✓ Installed extension https://github.com/pzadora-appfire/gh-pr-dashboard.git
```

### 2. Ensure the `gh-pr-dashboard` script is executable:

To make sure the `gh-pr-dashboard` script is executable, you need to specify the full path where the `gh-pr-dashboard` extension is installed.

Find it by running `gh-pr-dashboard` without any arguments.
```sh
gh pr-dashboard
```

Next use the `chmod` command as follows:
```sh
chmod +x /full/path/to/gh/extensions/gh-pr-dashboard/gh-pr-dashboard
```

### 3. Ensure the `gh-pr-dashboard` extension has been installed:
```sh
gh ext ls
```
You should see a response like this:

```
NAME             REPO                             VERSION
gh pr-dashboard  pzadora-appfire/gh-pr-dashboard  9cc337d3
```

## Usage
Once installed, you can use the extension to generate a dashboard for PRs of a specific author. Example usage:
```sh
gh pr-dashboard <author>
```
For your own PRs, you can enter your GitHub login or simply use @me.
```sh
gh pr-dashboard @me
```
### Example
To generate a dashboard for PRs by the author john-doe, you would run:
```sh
gh pr-dashboard john-doe
```
The result of this command will be a file named **dashboard.html** containing information about open Pull Requests by the author john-doe.

### Example HTML file
The dashboard generates an HTML file containing information such as: