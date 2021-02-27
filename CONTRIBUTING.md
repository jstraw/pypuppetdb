# Contribution guide

We welcome contributions to this library. However, there are a few
ground rules contributors should be aware of.

## Commit messages

Write decent commit messages. Don't use swear words and refrain from
uninformative commit messages as 'fixed typo'.

The preferred format of a commit message:

    docs/quickstart: Fixed a typo in the Nodes section.
    
    If needed, elaborate further on this commit. Feel free to write a
    complete blog post here if that helps us understand what this is
    all about.
    
    Fixes #4 and resolves #2.

If you'd like a more elaborate guide on how to write and format your
commit messages have a look at this post by [Tim
Pope](https://tbaggery.com/2008/04/19/a-note-about-git-commit-messages.html).

## Preparing local development environment

```bash
# Create a Python 3 virtualenv and activate it
virtualenv -p python3 .venv
. .venv/bin/activate
# Install the module in a development mode
python setup.py develop
# Install test dependencies
pip install -r requirements-test.txt
```

## Tests

Commits are expected to contain tests or updates to the tests if they add to
or modify the current behavior.

Assuming you have prepared the development environment as explained above,
do this to run the tests:

```bash
# Unit tests
py.test
# Security linter
bandit -r pypuppetdb
```

If the tests pass, you're golden. If not we'll have to figure out why
and fix that. Feel free to ask for help on this.

## Building documentation

API documentation is automatically generated from the docstrings using
Sphinx's autodoc feature.

Documentation will automatically be rebuilt on every push thanks to the
Read The Docs webhook. You can [find it
here](https://pypuppetdb.readthedocs.org/en/latest/).

You can build the documentation manually by doing:

```bash
# Activate the virtualenv and install sphinx + the theme we are using
pip install sphinx sphinx-rtd-theme
cd docs
make html
```