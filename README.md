# Publishing tutorial sample repo
A sample repository that you can use during the "Getting started publishing with Pantheon 2" tutorial.

* [Contributing to this repository](#contributing-to-this-repository)

## Contributing to this repository

### Filing a bug

If you have any suggestions to improve or extend this repository, open a [new issue](https://github.com/redhat-documentation/publishing-tutorial-sample-repo/issues) in the repository.

### Prerequisites

* Have a GitHub account.
  [Signing up for a new GitHub account](https://help.github.com/en/github/getting-started-with-github/signing-up-for-a-new-github-account)
* Have your SSH key added to your GitHub account.
[Adding a new SSH key to your GitHub account](https://help.github.com/en/github/authenticating-to-github/adding-a-new-ssh-key-to-your-github-account)
* You must be a member of the `pantheon-developers` or `pantheon-doc-authors` team in the `redhataccess` group in GitHub.
* You must be logged in to your account on GitHub.

### Forking the repository

Fork the repository so that you can create and work with branches independently of the `redhataccess/pantheon` repository.

1. In a web browser, navigate to https://github.com/redhat-documentation/publishing-tutorial-sample-repo
1. Click **Fork**.
1. Click your user space in GitHub.

### Cloning the repository

After you have forked the repository, you must clone it to your local machine and add the original `redhat-documentation/publishing-tutorial-sample-repo` repository as an upstream remote.

1. From a terminal, clone the repository:

    ```sh
    $ git clone git@github.com:<user-space>/publishing-tutorial-sample-repo.git
    ```
1. Set up `redhat-documentation/publishing-tutorial-sample-repo` as the upstream:

    ```sh
    $ cd publishing-tutorial-sample-repo
    $ git remote add upstream git@github.com:redhat-documentation/publishing-tutorial-sample-repo.git
    ```

### Creating a working branch

Pull requests should have a corresponing issue in the repo. Whenever you work on a new issue, you must create a new working branch based on the latest version of the upstream main branch.

1. Ensure you are on main

    ```sh
    $ git checkout main
    ```
1. Ensure your fork is up to date

    ```sh
    $ git pull upstream main
    ```
1. Create a working branch based on the issue ID. For example for issue #2, you can use "2" or "02" for the branch name:

    ```sh
    $ git checkout -b 02
    ```       

### Creating a pull request and requesting a review

When your work is ready to be reviewed and merged, create a pull request.

1. Push your working branch to your fork:

    ```sh
    $ git push -u origin <branch_name>
    ```
1. From the repository page in GitHub, click **New pull request**.
1. Select your working branch from the compare list.
1. Add the `WIP:` prefix to the title of the pull request. This automatically converts the pull request to a draft pull request, preventing it from being merged.
1. Click **Create new pull request**.
1. Add the **awaiting tech review** label to the pull request.
1. In the pull request comment field, enter `@redhat-documentation/publishing-tutorial-team Please review for technical completeness and accuracy`.

### The review process

At least one person on the project team reviews the merge request and adds comments in GitHub. This review process will be open for one week from the day the merge request was submitted. If the merge request is still being actively discussed beyond the one week timeframe, then the merge request will stay open. Once the merge request discussion is resolved, the merge request will be NACK'd or ACK'd based on the comments given. If no comments are given after a week, then a project administrator will ACK the merge request.

### Merging a pull request

After you have implemented all reviewer comments and received an ACK from an administrator, the pull request is ready to be merged.

1. Remove `WIP` from the title of the pull request.
1. Request that an Administrator merge the pull request.
