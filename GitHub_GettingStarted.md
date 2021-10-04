# Getting started with GitHub

## GitHub useful commands & tips
https://docs.gitlab.com/ee/gitlab-basics/start-using-git.html

## Create GitHub Organization
To create a GitHub Organization, which can have many repositories and members who can contribute to them: https://docs.github.com/en/organizations/collaborating-with-groups-in-organizations/creating-a-new-organization-from-scratch

## Create a personal access token for GitHub
This step is necessary because Git is disabling password logins as of August 2021.
 
If you have the `gh` GitHub CLI tool installed, you can alternatively run `gh auth login` to be guided through a web authentication method.
 
1. Authenticate at https://github.com
2. Click on your **GitHub username** in the top right corner
3. Navigate to Settings > Developer Settings > Personal Access Tokens
4. Click **Generate new token**
5. Pick a suitable name and expiration date (your login will stop working after the expiration date)
6. Set permissions for the token - for normal operations it's enough to select **Repo** permissions only
7. Click **Generate Token**
8. Use this token instead of your password for logging in to GitHub the CLI

**Treat your token like a password, keep it safe!**

## Add the GitHub repository for the team webpage
1. Clone the GitHub repository for the team page:
    `git clone https://github.com/ycit-team-terraformers/ycit-team-terraformers.github.io`
