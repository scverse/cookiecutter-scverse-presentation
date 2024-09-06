---
marp: true
theme: uncover
paginate: true
#backgroundColor: #fff
backgroundImage: radial-gradient(circle 100vh at bottom 100px right 100px in hsl, rgb(161, 186, 182) 0%, transparent 100%)
style: |
  .columns {
    display: grid;
    grid-template-columns: repeat(2, minmax(0, 1fr));
    gap: 1rem;
  }
---

<!-- _paginate: skip -->

![bg right:33% vertical 70%](https://scverse.org/img/icons/scverse_bw_logo.svg)
![bg right:33% vertical 60%](https://api.qrserver.com/v1/create-qr-code/?format=svg&bgcolor=161-186-182&data=https://scverse.org/cookiecutter-scverse-presentation/)

# [scverse cookiecutter template](https://cookiecutter-scverse-instance.readthedocs.io/en/latest/template_usage.html)

Follow along: [scverse.org/
cookiecutter-scverse-presentation](https://scverse.org/cookiecutter-scverse-presentation/)

---

# tool installs

* Install using a package manager or installer:

  - `code`: [code.visualstudio.com/download](https://code.visualstudio.com/download)
  - `hatch`: [hatch.pypa.io/latest/install](https://hatch.pypa.io/latest/install/)
  - `git`: [github.com/git-guides/install-git](https://github.com/git-guides/install-git)
  - `uv`: [docs.astral.sh/uv/getting-started/installation](https://docs.astral.sh/uv/getting-started/installation/)
    or `pipx`: [pipx.pypa.io/stable/installation](https://pipx.pypa.io/stable/installation/)

* Install using a package manager, `pipx`, or `uv`:

  ```console
  $ pipx/uv install cruft pre-commit
  ```

---

# creating the project

```console
$ cruft create https://github.com/scverse/cookiecutter-scverse
  project_name (project-name): myproj
  […]
$ code myproj
```

<img style="margin-bottom: -450px" src=./img/new-proj.png>

---

# environment management

Hatch envs [basic usage](https://hatch.pypa.io/latest/tutorials/environment/basic-usage/):

```console
$ hatch run [env:]command [...args] # e.g. `… docs:build -T`
$ hatch test [...args]
$ hatch env remove <name> # or `hatch env prune` for all
$ hatch find hatch-test
~/.local/share/hatch/env/virtual/myproj/FsejNibV/hatch-test.py3.12
[…]
```

Tell VS Code:

<kbd>⌘</kbd>|<kbd>^</kbd>+<kbd>⇑</kbd>+<kbd>P</kbd> → <kbd>Python: Select Interpreter</kbd>

---

# running tests

```console
$ hatch test --help
[…]
Options:
  -r, --randomize
  -p, --parallel
  -c, --cover
  -a, --all
  -py, --python=X.Y
  -i, --include=VAR=VAL
  -x, --exclude=VAR=VAL
  -s, --show
```

![bg right:40% contain](https://code.visualstudio.com/assets/docs/python/testing/test-explorer.png)

---

# building docs

```console
$ hatch run docs:build
$ hatch run docs:open
$ hatch run docs:clean
```

![bg right:40% contain](./img/docs.png)

---

# formatting and linting

VS Code:

```json
{
  "[python]": {
    "editor.formatOnSave": true,
    "editor.defaultFormatter": "charliermarsh.ruff",
    "editor.codeActionsOnSave": { ... },
  }, ...
}
```

CLI: `pre-commit` (or `hatch run pre-commit`)

<!-- Installing pre-commit globally is preferred -->

```console
$ pre-commit install # `git commit` hook
$ pre-commit run --all-files
```

---

# Committing code

- Use PRs, don’t push to `main`
- Set up [pre-commit.ci](https://pre-commit.ci/), [codecov.io](https://codecov.io/) on
  [github.com/&lt;you>/&lt;yourpackage>/settings/installations](#)
