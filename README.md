# Run AI Models with Docker in GitHub Actions Example

This repository contains an example of using Docker's Model Runner feature inside GitHub Actions as part of a CI/CD pipeline. The example action does the following:

1. **Checks out your code:**
Uses GitHub's built-in checkout action to retrieve the latest code from your repository.

2. **Installs Docker Desktop with Model Runner:**
* Downloads and installs the specified Docker Desktop build optimized for macOS.
* Starts Docker Desktop in a headless (unattended) mode suitable for CI environments.

3. **Pulls the AI model** from Docker Hub using Docker Model Runner CLI commands.

4. **Validates Pull Request Descriptions:**
* Automatically reviews the pull request description for clarity, completeness, and adherence to your team's specific guidelines (e.g., stating the change clearly, mentioning related issues, and explicitly calling out breaking changes).
* Runs locally, securely, and efficiently without external API dependencies.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.