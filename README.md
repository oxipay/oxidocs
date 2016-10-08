# Oxidocs

## Setting up your environment

To get your mkdocs environment configured; install the following:
* chocolatey
* python:

        cinst python -y
* mkdocs:

        pip install mkdocs

Note: you might need to ensure cinst, python, & pip are all in your path.

## Updating the documentation

The oxidocs repository has all the documentation in markdown format. There is also a submodule to the oxipay.github.io GiHub pages repository, which is basically the oxidocs repository transformed for the web.

To update the documentation the following steps need to be done.

* To make the instructions easy; we've added some useful configurations in the local .gitconfig. To get this in your git include path, run the following:

        git config --local include.path ../.gitconfig
* clone this repository and initialise the submodule:

        git clone git@github.com:oxipay/oxidocs.git
        cd oxidocs
        git sync-build
* Make your changes to the documentation
* Build the documentation:

        mkdocs build
* commit and push both the oxipay.github.io and oxidocs repositories:

        git add-commit-all "message"
        git push-all
