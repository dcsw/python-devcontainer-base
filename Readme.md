# Jupyter Anaconda DevContainer

## Description
This is a devcontainer -- docker image for using in VSCode with the DevContainers extension installed -- for running Anaconda with Jupyter notebook support in VSCode and via localhost webserver (port 8888).

## Getting started in VSCode
1. Open the repo in a container
Simply open this repo in VSCode. On first run, select Run in DevContainer. On subsequent opens, choose the repo with the container in its title.
2. Open a .pynb file. An example is available under data/codewars.
3. You're done!

From here you can run or rerun the notebook element in VSCode.

## Bonus Browser Session!
Doing the steps above __also__ starts a webserver session at http://localhost:8888.
As usual for jupyter, you will need a token to access any notebooks.
Run the following in a VSCode integrated terminal (or in a docker attach session) to retrieve a direct-click URL with the token.
```
egrep -e 'http://.*tree' nohup.out | tail -n 1
```
Control-clicking [Command-clicking on MacOS) on the URL will navigate directly to a notebook directory session in your default browser.

## Saving Notebooks
Any notebooks created under the ____data____ directory will be preserved in the repo (other directories will not be preserved).

## A note about Git
Note that your local machine's git environment will operate, but its connection with any remote repos (such as in GitHub, GitLab, BitBucket, etc.) will __not__ be available from within the container.

To do a push, pull, or pull request, then, exit the container and carry out these git operations from your local machine.
