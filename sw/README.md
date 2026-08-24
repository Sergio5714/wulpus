# WULPUS GUI source files
This directory contains the source files for WULPUS Graphical User Interface (`sw/wulpus`) and an example Jupyter notebook (`sw/wulpus_gui.ipynb`).

# Getting started

The software uses [uv](https://docs.astral.sh/uv/) for Python and dependency
management. From the repository root, install the locked dependencies and open
the example notebook with:

```console
uv sync --project sw
uv run --directory sw jupyter notebook wulpus_gui.ipynb
```

`uv sync` installs the required Python version if necessary, creates `sw/.venv`,
and installs the exact dependency versions recorded in `sw/uv.lock`.

When working from inside `sw`, use the shorter equivalents:

```console
uv sync
uv run jupyter notebook wulpus_gui.ipynb
```

# License
The source files are released under Apache v2.0 (`Apache-2.0`) license unless noted otherwise, please refer to the `sw/LICENSE` file for details.
