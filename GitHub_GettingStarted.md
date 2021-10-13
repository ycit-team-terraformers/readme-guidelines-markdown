# Getting started with GitHub

## GitHub useful commands & tips
https://docs.gitlab.com/ee/gitlab-basics/start-using-git.html

## Markdown formatting help
https://www.markdownguide.org/cheat-sheet/

## Create GitHub Organization
To create a GitHub Organization, which can have many repositories and members who can contribute to them: https://docs.github.com/en/organizations/collaborating-with-groups-in-organizations/creating-a-new-organization-from-scratch

## Install & Configure Git for Windows Subsystem for Linux
Extra steps are necessary because Git is disabling password logins as of August 2021.
 
Use one of these options to configure authentication:
- [Use Git Credential Manager with WSL (recommended)](https://github.com/microsoft/Git-Credential-Manager-Core/blob/main/docs/wsl.md)
- [Configure SSH keys with git](https://docs.github.com/en/authentication/connecting-to-github-with-ssh)


## Add the GitHub repository for the team webpage
1. Clone the GitHub repository for the team pages:
```
    git clone https://github.com/ycit-team-terraformers/ycit-team-terraformers.github.io
    git clone https://github.com/ycit-team-terraformers/ycit-team-terraformers-dotfiles
```

2. If all goes well, you should 2 new directories and you can enter them and 'git pull' to see that they're "Already up to date", example:
```
    cd ycit-team-terraformers-dotfiles
    git pull
```

3. To commit changes or new files, follow the usual:
```
    git add .
    git commit -m "my commit message"
    git push origin main
```
**If you get authentication errors:** make sure you've followed all the steps in setting up Git above - including configuring Git Credential Manager Core.