# Troubleshooting PR-SnapView Plugin

This document will help you troubleshoot common issues when using PR-SnapView. Below are typical scenarios and suggested solutions.

---

## Table of Contents

1. [Plugin doesn't install correctly](#plugin-doesnt-install-correctly)
2. [Errors when generating the dashboard](#errors-when-generating-the-dashboard)
3. [Dashboard doesn't open automatically](#dashboard-doesnt-open-automatically)
4. [Repository configuration issues](#repository-configuration-issues)
5. [Pull Requests not displaying](#pull-requests-not-displaying)
6. [Reporting issues](#reporting-issues)

---

## Plugin doesn't install correctly

If you encounter issues during plugin installation:

- Ensure you are using a compatible version of your IDE that supports PR-SnapView.
- Check system requirements in the [Prerequisites.md](https://github.com/itRunFenix/PR-SnapView-plugin/blob/master/Prerequisites.md) file.
- If necessary, reinstall the plugin by removing it and installing it again from the JetBrains Marketplace.

**Errors in IDE console**:  
Check the IDE logs by going to `Help` > `Show Log in Explorer/Finder` to see more details about the installation errors.

---

## Errors when generating the dashboard

If the dashboard is not generated properly:

- Ensure that the correct local repository path is set in the plugin configuration.
- Verify that all required tools, such as GitHub CLI and `jq`, are installed (see [Prerequisites.md](https://github.com/itRunFenix/PR-SnapView-plugin/blob/master/Prerequisites.md)).
- If errors occur, try regenerating the dashboard and review the IDE logs for more information.

- **Known Issue:** 
  - [Error after run PR-SnapView for **very first time** on a particular repository](https://github.com/itRunFenix/PR-SnapView-plugin/issues/2)

---

## Dashboard doesn't open automatically

If the dashboard doesn't open in the browser:

- Be aware that clicking "OK" in the `PR-SnapView Settings` window does not generate the dashboard but only saves the settings. To generate the dashboard, click `Generate PR-SnapView`
- Make sure the "Open dashboard in external browser" option is enabled in the plugin settings.
- Verify that the specified browser is correctly configured. If needed, manually set the browser in the settings.
- If you prefer opening the dashboard inside the IDE, ensure that the option is activated.
- Be aware that when opening the file inside the IDE, only the HTML file will be opened. You can use the built-in preview option in the top right corner of the file to view it

---

## Repository configuration issues

If the plugin cannot recognize your repository or displays errors:

- Double-check that the correct **local repository path** is provided in the PR-SnapView configuration.
- Ensure the repository is properly initialized (e.g., contains a `.git` folder).
- Update the configuration if you have changed the repository location or settings.

---

## Pull Requests not displaying

If no pull requests are displayed:

- Ensure there are active open pull requests in the selected repository.
- Verify that the filters (e.g., `author` or `assignee`) are correctly set.
- Try manually generating a report using the GitHub CLI to check whether the issue lies with the plugin or the repository data.
- Ensure you are correctly logged in to the GitHub CLI.
- Please check that you have access to the repository specified in the plugin settings as the repo path.
- Verify the authentication status by running the following command: `gh auth status`. You should see output similar to this:
```
  ✓ Logged in to github.com account itRunFenix (keyring)
  - Active account: true
  - Git operations protocol: https
  - Token: gho_************************************
  - Token scopes: 'gist', 'read:org', 'repo', 'workflow'
```
- Check the output and ensure that you are logged in, and the account is set as active.
- If you see `Active account: false`, it means the user account is logged in, but it is not the currently active account for GitHub CLI (gh) operations.
- To activate the account, log in again by running `gh auth login` and follow the steps provided.


---

## Reporting issues

If you encounter problems you cannot resolve, report them:

- Before reporting an issue, please check for useful information here: [BUG](https://github.com/itRunFenix/PR-SnapView-plugin/blob/master/BUG.md).
- Create an issue on the [Issues](https://github.com/itRunFenix/PR-SnapView-plugin/issues) section of the GitHub repository.
- Include details such as the IDE version, plugin version, OS name and version and steps to reproduce the problem.
- You may also attach IDE logs to help diagnose the issue (logs can be found in `Help` > `Show Log in Explorer/Finder`).

---

## Additional Resources

- [JetBrains Marketplace](https://plugins.jetbrains.com/)
- [GitHub CLI Documentation](https://cli.github.com/)
- [jq Documentation](https://stedolan.github.io/jq/)
