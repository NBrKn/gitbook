Short Status: `git  status -s`


## Gitignore

Can use general regex syntax for file specification plus:
```
    # ignore all .a files   
    *.a

    # but do track lib.a, even though you're ignoring .a files above
    !lib.a

    # only ignore the TODO file in the current directory, not subdir/TODO
    /TODO

    # ignore all files in the build/ directory
    build/

    # ignore doc/notes.txt, but not doc/server/arch.txt
    doc/*.txt

    # ignore all .pdf files in the doc/ directory and any of its subdirectories
    doc/**/*.pdf
```

Modifications
`git diff`

Staged
`git diff --staged`

Direct commit
`git commit -am ".."`

Remove and stage
`git rm filename`. Need to put `-f` for staged files

Untrack file
`git rm --cached filename`

View history
`git log`
Limit # of entries `-2`  
Differences (patches) shown `-p`  
Abbr. diffs `--stat`

```
    $ git log --pretty=format:"%h - %an, %ar : %s"
    ca82a6d - Scott Chacon, 6 years ago : changed the version number
    085bb3b - Scott Chacon, 6 years ago : removed unnecessary test
    a11bef0 - Scott Chacon, 6 years ago : first commit
```

` git log --pretty=format:"%h %s" --graph`  

`$ git log --since=2.weeks`  

`$ git log -S function_name`

Redoing previous commit (use only for small changes)
`git commit --amend`

Unstaging  
`git reset HEAD filename`

Unmodifying (Forever undo the changes)
`$ git checkout -- CONTRIBUTING.md`

List all remotes
`$ git remote -v`

Get data from remote  
`$ git fetch <remote>`. It does not issue a merge
`git pull origin`does

Pushing changes
`git push <remote> <branch>`

Inspecting remotes
` git remote show origin`

Renaming remotes
`git remote rename pb paul`

Removing remotes
`git remote remove paul`


### Tags
Git tag
`git tag`

Anotated tags
`git tag -a v1.4 -m "my version 1.4"`

Lightweight tags
`git tag v1.4-lw`

Adding tags after commit
`git tag -a v1.2 9fceb02`

Note git does not push tags automatically
`git push origin v1.5` `git push origin --tags`

To checkout
`$ git checkout 2.0.0`  
`$ git checkout -b version2 v2.0.0`

### Aliases
Common
```bash
    $ git config --global alias.co checkout
    $ git config --global alias.br branch
    $ git config --global alias.ci commit
    $ git config --global alias.st status
    $ git config --global alias.unstage 'reset HEAD --'
    $ git config --global alias.last 'log -1 HEAD'
```

External command
`$ git config --global alias.visual '!gitk'`  

