# Elevated Standards Template Repository


This template repository equips you with the default initial files required for a Elevated Standards GitHub repository.

## Included Files

The repository comes with the following preset files:

* `.devcontainer`: Folder containing files used for setting up a devcontainer
  * `devcontainer.json`: File configuring the devcontainer, includes VS Code settings
* `.github`: Folder for Github-specific files and folders
  * `workflows`: Folder containing Github actions config files
    * `python.yaml`: File configuring Github action that runs tools and tests
* `tests`: Folder containing Python tests
  * `main_test.py`: File with pytest-style tests of main.py
* `.gitignore`: File describing what file patterns Git should never track
* `.pre-commit-config.yaml`: File listing all the pre-commit hooks and args
* `main.py`: The main (and currently only) Python file for the program
* `pyproject.toml`: File configuring most of the Python dev tools
* `README.md`: You're reading it!
* `requirements-dev.txt`: File listing all PyPi packages required for development
* `requirements.txt`: File listing all PyPi packages required for production
* `.github`: Folder for workflows, templates and etc.
  * `dependabot.yml`:
  * `workfows.yml`:
  * `actions`:
* `CODEOWNERS`:
* `LICENSE`:

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

Those checks are run as pre-commit hooks using the `pre-commit` library.

It includes `pytest` for testing plus the `pytest-cov` plugin to measure coverage.

The checks and tests are all run using Github actions on every pull request and merge to main.

This repository is setup for Python 3.11. To change the version:

1. Change the `image` argument in `.devcontainer/devcontainer.json` (see [https://github.com/devcontainers/images/tree/main/src/python](https://github.com/devcontainers/images/tree/main/src/python#configuration) for a list of pre-built Docker images)
1. Change the config options in `.precommit-config.yaml`
1. Change the version number in `.github/workflows/python.yaml`


### With devcontainer

This repository comes with a devcontainer (a Dockerized Python environment). If you open it in Codespaces, it should automatically initialize the devcontainer.

Locally, you can open it in VS Code with the Dev Containers extension installed.

### Without devcontainer

If you can't or don't want to use the devcontainer, then you should first create a virtual environment:

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

This repository starts with a very simple `main.py` and a test for it at `tests/main_test.py`.
You'll want to replace that with your own code, and you'll probably want to add additional files as your code grows in complexity.

When you're ready to run tests, run:

```
python3 -m pytest
```
