# *Pushing to a Repository*
Please follow this steps when pushing a new change to a repository:

1. Create a local branch
    `git checkout -b [name_of_your_new_branch]`
2. Make changes on your new branch and commit them 
3. Push branch to github 
    `git push origin [name_of_your_new_branch]`

# *Git Commit Style*

### Introduction
As projects drag on git commits get more messy and less descriptive, so we should keep an eye if this is happening to us.
Well-crafted Git commit message is the best way to communicate context about a change to fellow developers, A diff will tell you what changed, but only the commit message can properly tell you why.

### Style 
Message shoud start with upper case with out punctuation at the end of the message
### Content
 task#number, task name followed by : then a detailed description of what was done
### Extra
We should have one commit per task
### Example
```
"Task#8, Propose a git commit style & document: Proposition for git commit Style, Content and guide lines"
```

### References
We can follow the seven rules of a great Git commit message on this blog [this link](https://chris.beams.io/posts/git-commit/). 