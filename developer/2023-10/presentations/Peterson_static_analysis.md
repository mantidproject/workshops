layout: presentation
title: Static analysis in mantid
template: inverse
class: center, middle
background-image: url(whiteboard.jpg)
background-position: center
background-size: cover

# Static analysis in mantid

![grumpy cat](https://www.gravatar.com/avatar/0e5fe117c937b1fab5cb88e3d8ef59e4.jpg)

Pete Peterson

???

Render online with https://remarkjs.com/remarkise
Markdown cheatsheet https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet
font awesome        http://fontawesome.io/icons/
Emoji unicode table http://apps.timwhitlock.info/emoji/tables/unicode

---
class: left, top
background-position: 50% 98%
background-size: contain

# pre-commit


[pre-commit](https://pre-commit.com/) contains the majority of the static analysis ([mantid's configuration](https://github.com/mantidproject/mantid/blob/main/.pre-commit-config.yaml))

* pre-commit core hooks
  * trailing-whitespace
  * check-added-large-files
  * check-xml
  * check-yaml
* [mantid custom hooks](https://github.com/mantidproject/pre-commit-hooks.git)
  * clang-format *
  * cmake-missing-pytest-files
* [cmake format](https://github.com/cheshirekow/cmake-format-precommit)
  * cmake-format
  * cmake-lint (not enabled)
* [ruff](https://github.com/astral-sh/ruff-pre-commit)
* [black](https://github.com/psf/black) *

???

background-image: url(https://pre-commit.com/logo.svg)

---
# ruff

* [ruff](https://docs.astral.sh/ruff/) takes the place of flake8, pylint, etc
* nomalizes differences between tools (no more tweaking configuration)
* will autofix some things
* [mantid configuration](https://github.com/mantidproject/mantid/blob/main/pyproject.toml)
* [list of ruff rules](https://docs.astral.sh/ruff/rules/)

---
# coverity

* commercial c++ static analysis tool
* [builds on even number days](https://builds.mantidproject.org/view/Static%20Analysis/job/coverity_build_and_submit/)
* [mantid scan results](https://scan.coverity.com/projects/mantidproject-mantid?tab=overview)
