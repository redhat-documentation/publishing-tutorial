# publishing-tutorial-sample-repo
A sample repo to be used in conjunction with the tutorial "Getting started publishing with Pantheon 2"

[![Build Status](https://travis-ci.org/redhataccess/pantheon.png)](https://travis-ci.org/redhataccess/pantheon)
[![Code Coverage](https://codecov.io/gh/redhataccess/pantheon/branch/master/graph/badge.svg)](https://codecov.io/github/redhataccess/pantheon?branch=master)

Pantheon 2 is a modular documentation management and publication system based on asciidoc
and built on top of Apache sling.
* [Contributing to Pantheon](#contributing-to-pantheon)
* [Installing Pantheon](#installing-pantheon)
 * [Prerequisites](#prerequisites)
 * [Environment Variables](#environment-variables)
 * [Building the application](#building-the-application)
 * [Unit tests](#unit-tests)
 * [Running the application](#running-the-application)
 * [Live deploy of code](#live-deploy-of-code)
 * [Using the application](#using-the-application)
 * [Other use cases](#other-use-cases)
 * [Developing the frontend code](#developing-the-frontend-code)
* [End user documentation](#end-user-documentation)

## Contributing to Pantheon

### Filing a bug for Pantheon 2 end-user documentation

If you have any suggestions to improve or extend the end-user documentation, create a new issue and tag @pantheon-doc-authors.

### Prerequisites

* You must have an account on GitHub.
  [Signing up for a new GitHub account](https://help.github.com/en/github/getting-started-with-github/signing-up-for-a-new-github-account)
* You must have registered SSH keys in your GitHub account.
[Adding a new SSH key to your GitHub account](https://help.github.com/en/github/authenticating-to-github/adding-a-new-ssh-key-to-your-github-account)
* You must be a member of the `pantheon-developers` or `pantheon-doc-authors` team in the `redhataccess` group in GitHub.
* You must be logged in to your account on GitHub.

### Forking the repository

Fork the repository so that you can create and work with branches independently of the `redhataccess/pantheon` repository.

1. In a web browser, navigate to https://github.com/redhataccess/pantheon
1. Click **Fork**.
1. Click your user space in GitHub.

### Cloning the repository

After you have forked the repository, you must clone it to your local machine and add the original `redhataccess/pantheon` repository as an upstream remote.

1. From a terminal, clone the repository:

    ```sh
    $ git clone git@github.com:<user-space>/pantheon.git
    ```
1. Set up `redhataccess/pantheon` as the upstream:

    ```sh
    $ cd pantheon
    $ git remote add upstream git@github.com:redhataccess/pantheon.git
    ```

### Creating a working branch

Whenever you work on a new issue, you must create a new working branch based on the latest version of the upstream master branch.

1. Ensure you are on master

    ```sh
    $ git checkout master
    ```
1. Ensure your fork is up to date

    ```sh
    $ git pull upstream master
    ```
1. Create a working branch based on the issue in JIRA. For example:


    ```sh
    $ git checkout -b FCCEUD-<ID#>
    ```       

### Creating a pull request and completing review

When your work is ready to be reviewed and merged, create a pull request.

1. Push your working branch to your fork:

    ```sh
    $ git push -u origin <branch_name>
    ```
1. From the repository page in GitHub, click **New pull request**.
1. Select your working branch from the compare list.
1. Add `WIP:` to the title of the pull request. This automatically converts the pull request to a draft pull request.
1. Click **Create new pull request**.
1. Add the **awaiting tech review** label to the pull request.
1. In the pull request comment field, enter `@redhataccess/eud-tech-review Please review for technical completeness and accuracy`.


### The review process

Both the technical review and peer review processes take place in pull requests in GitHub.

#### Documentation review
After creating and labeling a pull request as outlined above, the developers review the pull request and add comments regarding technical accuracy. Writers receive a notification that comments have been added via email, and when all comments have been addressed, the developers change the label from **awaiting tech review** to **tech review complete**.

When technical review is complete, writers click the **Reviewers** gear icon and select the name of a team member to request peer review. The peer writer reviews the pull request for clarity, consistency, and compliance with necessary standards.
Writers receive a notification that comments have been added via email, and when all comments have been addressed, the reviewer clicks **Review changes > Approve** from the **Files changed** tab of the pull request to approve the changes and the pull request.

#### Code review

For code pull requests, one or more developers review the pull request. A contributor submits a PR and uses Github's **Reviewers** gear icon to tag `@redhataccess/pantheon-developers`. A developer comments on the code, and discusses it with the submitter, before ultimately deciding to accept or reject the PR.

### Merging a pull request

When you have addressed all technical review and peer review comments, notify the developers to accept the pull request.

1. Remove `WIP` from the title of the pull request.
1. Click **Request Review** and enter `@redhataccess/pantheon-developers`.

The developers check that the **Tech review complete** label has been added to the pull request and peer pull request approval provided, then accept it.
