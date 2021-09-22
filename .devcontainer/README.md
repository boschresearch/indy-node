# Developing inside a container

The VSCode Remote - Containers extension allows to develop inside a docker container. We can use this to initialize a full indy-node development environment and run tests inside this environment
The files in this folder contain all the necessary settings.

## How to

* It not already installed, install the Remote - [Containers extension](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers)
* Click on the `><` symbol in the footer of VSCode and select `Open folder in container`
* The container will be built and set up
* On the left side the testing section should be visible (an erlenmeyer flask). If not, run the `Python > Discover Tests` command in VScode
