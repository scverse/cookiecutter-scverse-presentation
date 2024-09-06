---
marp: true
theme: uncover
paginate: true
#backgroundColor: #fff
#backgroundImage: url('https://marp.app/assets/hero-background.svg')
---

<!-- _paginate: skip -->

![bg right:33% vertical 70%](https://scverse.org/img/icons/scverse_bw_logo.svg)
![bg right:33% vertical 60%](https://api.qrserver.com/v1/create-qr-code/?format=svg&data=https://github.com/scverse/cookiecutter-scverse)

# scverse cookiecutter template

[github.com/scverse/
cookiecutter-scverse](https://github.com/scverse/cookiecutter-scverse)

<!-- Only QR code: follow the tutorial there if you access this presentation offline -->
<!-- Ask us if you follow live -->

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

Hatch [tutorials/environment/basic-usage](https://hatch.pypa.io/latest/tutorials/environment/basic-usage/)

```console
$ hatch run [env:]command [...args]
$ hatch test [...args]
$ hatch env remove <name> # or `hatch env prune` for all
$ hatch find hatch-test
~/.local/share/hatch/env/virtual/myproj/FsejNibV/hatch-test.py3.12
[…]
```

Tell VS Code to use this interpreter:

<kbd>⌘</kbd>|<kbd>^</kbd>+<kbd>⇑</kbd>+<kbd>P</kbd> → “Python: Select Interpreter”

---

# VS Code




---

# Committing code

- Use PRs, don’t push to `main`
- Set up [pre-commit.ci](https://pre-commit.ci/), [codecov.io](https://codecov.io/) on
  [github.com/&lt;you>/&lt;yourpackage>/settings/installations](#)
