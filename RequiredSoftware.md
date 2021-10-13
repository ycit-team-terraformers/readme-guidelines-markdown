# Required Software
Here is the minimum recommended software you'll need to interface with the products and scripts used by the team

## Workstation software
This should be installed on your Windows workstation for maximum compatibility with Linux tooling and scripts. 
If you can't install software on your workstation (corporate or otherwise controlled environment), one possible substitute is [Google Cloud Shell](https://cloud.google.com/shell), though you should be aware that you may run into limitations in the Cloud Shell environment.
- [Windows Subsystem for Linux (WSL) with Ubuntu Linux](https://ubuntu.com/wsl)
- [Microsoft Visual Studio Code](https://code.visualstudio.com/download)
- [Tutorial: Get started using Visual Studio Code with Windows Subsystem for Linux](https://docs.microsoft.com/en-us/windows/wsl/tutorials/wsl-vscode)

## Linux software
This should be installed where you run Linux (inside your WSL Ubuntu VM).
- [Google Cloud SDK components](https://cloud.google.com/sdk/docs/install#linux)
- [git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)
- [Terraform](https://learn.hashicorp.com/tutorials/terraform/install-cli)
- [kubectl](https://kubernetes.io/docs/tasks/tools/install-kubectl-linux/)
- (optional - if you want to beautify and customize your shell prompt) [powerline-go](https://github.com/justjanne/powerline-go)

## Helpful scripts
See the **scripts** directory inside the **ycit-team-terraformers-dotfiles** repository for some helpful scripts.
- [backup_wsl.bash](https://github.com/ycit-team-terraformers/ycit-team-terraformers-dotfiles/blob/main/scripts/backup_wsl.bash): Can be used to configure a backup of your HOME inside the WSL virtual machine, to a location on your physical host PC (including OneDrive, which may serve as a quick disaster recovery method).