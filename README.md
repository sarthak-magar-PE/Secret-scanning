**Infosec Team Secret Scanner**

**Secret scanning** is the process of automatically identifying and detecting sensitive information (such as API keys, passwords, tokens, private keys, or other credentials) that may have been accidentally committed or exposed in a codebase or version control system like GitHub. It aims to prevent security vulnerabilities by ensuring that secrets are not inadvertently shared with unauthorized parties. 
Approach in Pharmeasy for Github Secret Scanning: We have implemented a Secret Scanning solution using an open-source project to automatically detect secrets in Pharmeasy's GitHub repositories. This solution leverages GitHub self-hosted runners, which will be deployed on a VM managed by Infosec team. The open-source tool will be installed on this VM, allowing us to set up workflows that are triggered when a new pull request is created or when a PR is merged. These workflows will scan for any secrets and, if any are found, automatically create an issue in their Github repository.

We have a few steps in Secret Scanning that is developed by the Infosec team. 

1. Activating Github Actions whenever a pull request event is happening. 
3. Running Trufflehog when a pull request event (opened, reopened, synchronized, closed) has happened and scanning the repo for secrets using Trufflehog. 
4. If secrets are found creating an issue in the repository where the secrets are identified and providing necessary information like, commit id, file where the secret is identified and the user who pushed the code, sending an alert via webhook to infosec channel.
