# Windows installation notes

## Must use Windows Subsystem for Linux (WSL)

click [here](https://docs.microsoft.com/en-us/windows/wsl/install-win10) to install WSL

## Installation

- Run the install scripts on whichever repo you are on. Should work if running through wsl.
  - If not update this document so future Windows users have an easier time!
- After running install_prerequisites follow the node setup instructions: [node setup](https://github.com/bcgov/eagle-dev-guides/blob/master/dev_guides/node_npm_requirements.md) before running setup project.


### Known Issues

- Line Endings LF vs CRLF, should be handled by git but opening sh files will be converted to CRLF automatically by vscode
- Developer Install helper functions were not working. Looks like it is to do with the scope. Will need to revisit to get those working properly in WSL
- Mongodb has problems with WSL. Check [here](https://github.com/Microsoft/WSL/issues/3286) for more information about that
  - This [this](https://github.com/Microsoft/WSL/issues/3286#issuecomment-402594992) answer explains the manual process of adding in the mongodb keys to apt
  - Also [this](https://github.com/Microsoft/WSL/issues/796#issuecomment-255451470) is needed to get mongodb setup as a service
- Minio will fail with error `Invalid endPoint : undefined`
  - Need to set the Environment Variables in the eagle-api readme (use setx for cmd or $env for powershell)
### ASDF Problems

- Couldn't use asdf to install java openjdk 11 so just apt-install
- Needed unzip to install gradle using asdf so make sure to install that 
- If asdf did not install correctly follow manual process at:  [asdf](https://asdf-vm.com/#/core-manage-asdf-vm)

### If not using wsl

- The scripts will not work without using wsl, you will need to install the dependecies manually
- Use chocolately and check the scripts for the proper versions
