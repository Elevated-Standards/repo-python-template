# Elevated Standards Python Repository Template

This template repository provides you with the essential initial files needed for an Elevated Standards GitHub Python Repository.

## Included Files

**The repository comes with the following preset files:**

* `.devcontainer`: Directory housing the configuration files for initializing a devcontainer.
  * `devcontainer.json`: File that configures the devcontainer, containing settings for VS Code.
* `.github`: Directory dedicated to GitHub-specific files and configurations.
  * `actions`: Directory containing custom GitHub Actions scripts or reusable workflows for automation within the repository.
  * `workflows`: Directory housing configuration files for GitHub Actions.
    * `python.yaml`: File that configures the GitHub Action responsible for executing tools and running tests.
* `tests`: Folder containing Python tests
  * `main_test.py`: File containing pytest-style test cases for `main.py`.
* `.gitignore`: File specifying file patterns that Git should ignore and never track.
* `.pre-commit-config.yaml`: File enumerating all pre-commit hooks and their associated arguments.
* `main.py`: The primary (and currently sole) Python file for the program.
* `pyproject.toml`: File that configures the majority of Python development tools.
* `README.md`: This is it.
* `requirements-dev.txt`: File containing a list of all PyPI packages required for development.
* `requirements.txt`: File containing a list of all PyPI packages required for production.
* `CODEOWNERS`: File specifying individuals or teams responsible for maintaining specific parts of the codebase, used for automatic review requests in pull requests.
* `LICENSE`: File outlining the legal terms and conditions under which the software is distributed and used.

## Setup Instructions

Once you've created your repository using this template, ensure the following steps:

### Update README

Edit this README.md file to document your project accurately. Take the time to create a clear, engaging, and informative README.md file. Include information like what your project does, how to install and run it, how to contribute, and any other pertinent details.

### Update repository description

After you've created your repository, GitHub provides a brief description field that appears on the top of your repository's main page. This is a summary that gives visitors quick insight into the project. Using this field to provide a succinct overview of your repository is highly recommended.

This description and your README.md will be one of the first things people see when they visit your repository. It's a good place to make a strong, concise first impression. Remember, this is often visible in search results on GitHub and search engines, so it's also an opportunity to help people discover your project.

### Grant Team Permissions

Assign permissions to the appropriate Elevated Standards teams. Ensure at least one team is granted Admin permissions. Whenever possible, assign permissions to teams rather than individual users.

### Read about the GitHub repository standards

Familiarise yourself with the Elevated Standards GitHub Repository Standards. These standards ensure consistency, maintainability, and best practices across all our repositories.

<!--
You can find the standards [here]().
-->

Please read and understand these standards thoroughly and enable them when you feel comfortable.

<!--

### Modify the GitHub Standards Badge

Once you've ensured that all the [GitHub Repository Standards]() have been applied to your repository, it's time to update the Elevated Standards Compliance Badge located in the README file.

The badge demonstrates that your repository is compliant with MoJ's standards. Please follow these [instructions]() to modify the badge URL to reflect the status of your repository correctly.

**Please note** the badge will not function correctly if your repository is internal or private. In this case, you may remove the badge from your README.

-->

### Manage Outside Collaborators

To add an Outside Collaborator to the repository, follow the guidelines detailed <!-- [here](https://github.com/ministryofjustice/github-collaborators). -->

### Update CODEOWNERS

(Optional) Modify the CODEOWNERS file to specify the teams or users authorized to approve pull requests.

### Configure Dependabot

Adapt the dependabot.yml file to match your project's [dependency manager]<!--()--> and to enable <!--[automated pull requests for package updates]().-->

### Dependency Review

If your repository is private with no GitHub Advanced Security license, remove the `.github/workflows/dependency-review.yml` file.

## Development instructions

* `ruff`: identifies many errors and style issues (`flake8`, `isort`, `pyupgrade`)
* `black`: auto-formats code

Those checks are executed as `pre-commit` hooks using the pre-commit library.

The setup includes `pytest` for running tests, along with the `pytest-cov` plugin to measure code coverage.

All checks and tests are automatically run via GitHub Actions on every pull request and merge into the main branch.

This repository is configured for Python 3.11. To switch to a different Python version:

1. Change the `image` argument in `.devcontainer/devcontainer.json` (see [https://github.com/devcontainers/images/tree/main/src/python](https://github.com/devcontainers/images/tree/main/src/python#configuration) for a list of pre-built Docker images)
1. Change the config options in `.precommit-config.yaml`
1. Change the version number in `.github/workflows/python.yaml`


### With devcontainer

This repository includes a devcontainer, which is a Dockerized Python environment. If you open the repository in GitHub Codespaces, the devcontainer will initialize automatically.

For local development, you can open it in VS Code with the Dev Containers extension installed to set up the environment.

### Without devcontainer

If you are unable or prefer not to use the devcontainer, the first step is to create a virtual environment:

```
python3 -m venv .venv
source .venv/bin/activate
```

Then install the dev tools and pre-commit hooks:

```
python3 -m pip install --user -r requirements-dev.txt
pre-commit install
```

### Adding code and tests

This repository begins with a basic `main.py` file and its corresponding test file located at `tests/main_test.py`. You should replace these with your own code, and as your project evolves, you’ll likely need to add more files to accommodate increasing complexity.

When you're ready to run tests, run:

```
python3 -m pytest
```
