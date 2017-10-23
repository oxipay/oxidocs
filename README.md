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

* There are 4 branches:
  
  | oxidocs:          |    docs for Oxipay |
  ------------------------------------------
  | developmnent:     |    dev branch for oxidocs |
  ------------------------------------------
  | ezidocs:          |    docs for EPCart |
  ------------------------------------------
  | ezidocs_development |  dev branch for oxidocs |

  Each branch contains contents for both AU and NZ.

* You can to create a branch for your changes.

        git checkout -b new-thing

* Make your changes to the documentation.
* Run the web-application locally:

  for AU:

        mkdocs serve --config-file mkdocs-au.yml
  or for NZ:

        mkdocs serve --config-file mkdocs-nz.yml

* Commit your changes and push your branch back up to GitHub.

* Commit your changes and push your branch back up to GitHub.
* Submit a PR.
* When the PR is merged into the "oxidocs" branch or the "ezidocs" branch, the Appveyor build will automatically push the generated content up to the associated AWS S3 bucket. This will be effective for both AU and NZ.

* Shared attributes are defined in mkdocs-au.yml and mkdocs-nz.yml. For example, instead of using oxipay.com.au or oxipay.co.nz, please use %domain% instead