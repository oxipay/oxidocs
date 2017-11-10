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

  | branch name       |    description     |
  |-------------------|--------------------|
  | **oxidocs**          |    master branch for Oxipay docs (http://docs.oxipay.com.au and http://docs.oxipay.co.nz) |
  | developmnent    |    dev branch for oxidocs |
  | **ezidocs**       |    master branch for Certegy-ezipay docs (http://docs.certegyezipay.com.au and http://docs.certegyezipay.co.nz) |
  | ezidocs_development |  dev branch for ezidocs |

  Each branch contains both AU and NZ version at the same time.  
The differences are contained in the mkdocs config files (mkdocs-au.yml and mkdocs-nz.yml respectively).

* You can to create a branch for your changes.

        git checkout -b new-thing

* Make your changes to the documentation.
* Run the web-application locally:  

        #! for Australia:
        mkdocs serve --config-file mkdocs-au.yml

        #! for New Zealand:
        mkdocs serve --config-file mkdocs-nz.yml

* Commit your changes and push your branch back up to GitHub.
* Submit a PR.
* When the PR is merged into the "oxidocs" branch or the "ezidocs" branch, the Appveyor build will automatically push the generated content up to the associated AWS S3 bucket. This will be effective for both AU and NZ.

* Shared attributes are defined in mkdocs-au.yml and mkdocs-nz.yml. For example, instead of using oxipay.com.au or oxipay.co.nz, please use %domain% instead