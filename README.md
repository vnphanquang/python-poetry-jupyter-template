# Python - Poetry - Jupyter Notebook Workflow Template

## Prerequisites

| Dependency | Note |
| --- | --- |
| [Python] | Remember to add Python binary to `PATH` |
| [Poetry] | Dependency management tool |

On windows:

- If using an installer for Python, remember to check the checkbox "Add Python X.X to PATH". [Read detailed instruction here](https://docs.python.org/3/using/windows.html#the-full-installer).
- It's likely that you have to install poetry using the [official installer](https://python-poetry.org/docs/#installing-with-the-official-installer). Make sure `poetry` bin directory is added to `PATH`

## Getting Started

1. Clone this directory into a new one. If you are copying by hand, remember to exclude / remove the `.venv` folder in your new project.
2. Install dependencies, filter groups as necessary:
    ```bash
    poetry install --with dev
    ```

    Groups:
    - `dev`: `numpy`, `plotly`, `polars`
    - `jupyter`: necessary for Jupyter Notebook
    - `legacy`: `pandas`, `seaborn`, `pyarrow`

    Use the cli options `--with <group_name>` or `--without <group_name>` as necessary  (see [Install Options](https://python-poetry.org/docs/cli/#options-2)).

## Activate Jupyter Notebook Kernel in VSCode

If you have your VS Code open, you may need to restart it to see the new kernel.

To activate the kernel, open any `.ipynb` file, click on the kernel name on the top right corner, and select the kernel with the name in the form of ".venv (Python X.XX) .venv/bin/python".

## Manage Package

Whenever you need to add a new package to the project, run

```bash
poetry add <pacakge_name> --group <group_name>
```

For example, `poetry add pandas` will add `pandas` to the project. For more information, consult the [Poetry Documentation](https://python-poetry.org/docs/managing-dependencies/). Remember to add to the correct group if necessary.

## Reproduce the Project Environment

When sharing the project with your colleague, you can safely remove the `.venv` folder. 

Assuming tools specified in [Prerequisites](#prerequisites) are already installed, to reproduce the project environment (install the dependency), run:

```bash
poetry install
```

Then, if using Jupyter Notebook in VSCode, follow [Activate Jupyter Note Kernel in VSCode](#activate-jupyter-note-kernel-in-vscode) to activate the kernel.

[python]: https://www.python.org
[poetry]: https://python-poetry.org

