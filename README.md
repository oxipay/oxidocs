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

* add the the following alias to your global .gitconfig:

        submodule-trackbranch = "!git submodule foreach -q --recursive 'branch=\"$(git config -f $toplevel/.gitmodules submodule.$name.branch)\"; git checkout $branch'"
        upsub = !git submodule update --init --recursive --remote && git submodule-trackbranch
* clone this repository and initialise the submodule:

        git clone git@github.com:oxipay/oxidocs.git
        cd oxidocs
        git upsub
* Make your changes to the documentation
* Build the documentation:

        mkdocs build
* commit and push both the oxipay.github.io and oxidocs repositories:

        cd site
        git add --all
        git commit -m "message"
        git push
        cd ..
        git add --all
        git commit -m "message"
        git push
