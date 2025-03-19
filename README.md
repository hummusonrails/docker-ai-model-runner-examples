# Using Docker AI Model Runner

## GitHub Actions CI/CD Workflow

> [!CAUTION]
> This is **unsupported** currently in GitHub Actions until the MacOS runner uses M3 chips running MacOS 15 or later.

Use Docker's Model Runner feature inside GitHub Actions as part of a CI/CD pipeline. The [example action workflow](.github/workflows/pr_description_validation.yaml) does the following:

1. **Checks out your code:**
Uses GitHub's built-in checkout action to retrieve the latest code from your repository.

2. **Installs Docker Desktop with Model Runner:**
* Downloads and installs the specified Docker Desktop build optimized for macOS.
* Starts Docker Desktop in a headless (unattended) mode suitable for CI environments.

3. **Pulls the AI model** from Docker Hub using Docker Model Runner CLI commands.

4. **Validates Pull Request Descriptions:**
* Automatically reviews the pull request description for clarity, completeness, and adherence to your team's specific guidelines (e.g., stating the change clearly, mentioning related issues, and explicitly calling out breaking changes).
* Runs locally, securely, and efficiently without external API dependencies.

## Real Time Git Commit Message Generator

Create a Git hook that generates commit messages in real-time using Docker's Model Runner. This is a simple example of how to set up a Git hook that generates commit messages using Docker's Model Runner.

Ensure you have Docker installed and you have already pulled the AI model using `docker model pull [model_name]` before running the script.

1. **Create a Git Hook:**
Use the provided [prepare-commit-msg](prepare-commit-msg) script to create a Git hook that generates commit messages in real-time by adding it to the `.git/hooks` directory on your local machine.

2. **Make the Script Executable:**
Make the script executable by running the following command in your terminal:

```bash
chmod +x .git/hooks/prepare-commit-msg
```

Now whenever you run `git commit`, the script will automatically generate a commit message using Docker's Model Runner, for example:

```bash
git add .
git commit
# Output: "feat: Add new feature to improve user experience"
```

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.