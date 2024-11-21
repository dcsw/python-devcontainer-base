# PyMC DevContainer

## Description
This is a devcontainer -- docker image for using in VSCode with the DevContainers extension installed -- for running example python pymc code.

## Getting started in VSCode
Prerequisites: Install and run a docker host, like Docker Desktop or colima, and install the DevContainers extension in VSCode. Then:

1. Open the repo in a container. 

        To do this, simply open this repo in VSCode. On first run, select Run in DevContainer in the popup that shows up in the lower right of VSCode. To exit the DevContainer, click the _Remotes_ icon in the lower left and choose _Reopen Folder Locally. You can reenter the DevContainers from this menu using _Reopen in Container_ as well.

2. Open the __experiments/pymc seasonal.ipynb__.
3. You're done!

From here you can open __experiments/pymc seasonal.ipynb__ in VSCode and work with the notebook.

On your first notebook run, VSCode will ask you to select a python kernel.
Select __VSCode-Python3.11.2__ which is preconfigured to work with the notebook.

## A note about Git
Note that your local machine's git environment will operate, eg. commit/log/revert/merge/rebase, but its connection with any remote repos (such as in GitHub, GitLab, BitBucket, etc.) will __not__ be available from within the container.

To do a push, pull, or pull request, then, exit the container and carry out these git operations from your local machine.
