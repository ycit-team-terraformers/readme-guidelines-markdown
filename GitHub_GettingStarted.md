# Getting started with GitHub

## GitHub useful commands & tips
https://docs.gitlab.com/ee/gitlab-basics/start-using-git.html

## Markdown formatting help
https://www.markdownguide.org/cheat-sheet/

## Create GitHub Organization
To create a GitHub Organization, which can have many repositories and members who can contribute to them: https://docs.github.com/en/organizations/collaborating-with-groups-in-organizations/creating-a-new-organization-from-scratch

## Configure automated authentication to Git
This step is necessary because Git is disabling password logins as of August 2021.
 
https://docs.github.com/en/authentication/connecting-to-github-with-ssh
 
or (less secure): https://stackoverflow.com/a/35942890

## Add the GitHub repository for the team webpage
1. Clone the GitHub repository for the team pages:
    `git clone https://github.com/ycit-team-terraformers/ycit-team-terraformers.github.io`
    `git clone https://github.com/ycit-team-terraformers/ycit-team-terraformers-dotfiles`

2. If all goes well, you should 2 new directories and you can enter them and 'git pull' to see that they're "Already up to date", example:
    `cd ycit-team-terraformers-dotfiles`
    `git pull`
    
3. To commit changes or new files, follow the usual:
    `git add .`
    `git commit -m "my commit message"`
    `git push origin main`
    * If you get prompted for authentication, follow the steps 