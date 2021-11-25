## Goal:
Use GitHub action to create Pipeline to check Terraform files for the modules created and published in Terraform Cloud

## What to do:
On commit - Check files  (lintint) if passes, Create a new release for the current repo (automatically increase Release tag  ex. from v.1.0.2 to v 1.0.3

### Modules already published in TF Cloud, we need to create new version when change is applied. 

Because the module is already published
Once release is created in GitHub,  the Terraform Cloud will see the new release avaialble for the module. 

### Approach: Read about Github actions + create test actions and Run

Reviewed notes from  internet, link below includes some examples:
https://github.com/actions/create-release
 
Maintained Actions:

elgohr/Github-Release-Action
marvinpinto/action-automatic-releases
softprops/action-gh-release
ncipollo/release-action

### References

Searched in internet for :
 - "github action semver tag"
 - A Github Action to automatically bump and tag 
 
  candidate examples:
  
  https://github.com/marketplace/actions/github-tag-with-semantic-versioning
  
  https://github.com/anothrNick/github-tag-action
 
After testing and reviewing documenation, selected the following examples to follow: 

 - anothrNick/github-tag-action@1.36.0
 - ncipollo/release-action@v1

