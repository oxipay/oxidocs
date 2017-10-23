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

The oxidocs repository has all the documentation in markdown format. There is also a submodule to the oxipay.github.io GiHub pages repository, which is basically the oxidocs repository transformed into static HTML for the web.

To update the documentation the following steps need to be done.

* clone the repository and cd into it:

        git clone git@github.com:oxipay/oxidocs.git
        cd oxidocs

* Docs for Oxipay is in branch "oxidocs"; Docs for EPCart is in branch "ezidocs"

* You'll need to create a branch for your changes as master is protected.

        git checkout -b new-thing
* Make your changes to the documentation.
* Run the web-application locally:

        mkdocs serve
* Commit your changes and push your branch back up to GitHub.
* Submit a PR.
* When the PR is merged into the "oxidocs" branch or the "ezidocs" branch, the Appveyor build will automatically push the generated content up to the associated AWS S3 bucket.
