`$ git branch testing`  
`git checkout testing`

Check branching  
`$ git log --oneline --decorate --graph --all`

Branch and checkout
`git checkout -b iss53`

Merge
`$ git merge hotfix`

Delete branch
`$ git branch -d iss53`

List branches  
`git branch`

Commits on each branch
`git branch -v`

Merged and unmerged
`git branch [--merged / --unmerged]`

Workflows

* Long Running branches
    * master only contains stable builds
    * develop contains beta
* topic used for shortlived feature

List remote references  
`git ls-remote [remote]`  
For more info `git remote show [remote]`

Pushing to remote
`$ git push origin serverfix`, if branch names are the same  
`git push origin serverfix:serverfix` if different branch names

Merge to current branch
`git merge origin/serverfix`

Create a new branch off remote branch
`$ git checkout -b serverfix origin/serverfix`

Set up local branch to track remote (upstream)  
`$ git branch -u origin/serverfix`

Check tracking branches
`$ git branch -vv`

Pull from all the branches
`$ git fetch --all`
You can do pull which results in fetch + merge but not recommended as it can be more confusing

To delete remote branches  
`$ git push origin --delete serverfix`

Rebasing (Linear merge)  
```
    $ git checkout experiment
    $ git rebase master
    $ git checkout master
    $ git merge experiment
```

Rebasing offshoot(client) of branch(server) to master  
`$ git rebase --onto master server client`
Only do rebasing on your local repository


