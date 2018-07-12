Workflows
* Centralized: Each developer manages
* Integration Manager:  
    contributer clones and makes changes, then sends pull request
    maintainer merges locally and then pushes
* Dictator and lieutenant:
    lieutenants act as intermediate maintainer.
    A single dictator acts as final maintainer

Commit guidelines
* Should not contain whitespace errors
    `git diff --check`
* Commit logically separate changes
    `git add --patch` for partial staging
* 
```
Short (50 chars or less) summary of changes

More detailed explanatory text, if necessary.  Wrap it to about 72 characters or so.  In some contexts, the first line is treated as the subject of an email and the rest of the text as the body.  The blank line separating the summary from the body is critical (unless you omit the body entirely); tools like rebase can get confused if you run the two together.

Further paragraphs come after blank lines.

    - Bullet points are okay, too

    - Typically a hyphen or asterisk is used for the bullet,preceded by a single space, with blank lines inbetween, but conventions vary here
```

Find out merges
`$ git log --no-merges issue54..origin/master`

Sending pull requests  
`$ git request-pull origin/master myfork`

Create a branch without making a merge(?)
`git merge --squash featureB`

Pushing
`$ git push -u origin featureB:featureBee`

m-box formatted files  
`$ git format-patch -M origin/master`

Apply patches
`git apply --check ...` 
`git  apply ...`

Apply mbox `$ git am 0001-limit-log-function.patch`
`-3` option applies a 3 way merge
`$ git am -3 -i mbox`

Checking remotes
`$ git log contrib --not master`  
`$ git diff master...contrib`

You can keep multiple branches according to stability such as develop and integrated

Add only one commit as rebase
`$ git cherry-pick e43a6`

Tagging  
`$ git tag -s v1.5 -m 'my signed 1.5 tag'`

Signed tag
`$ gpg --list-keys`  
`$ gpg -a --export F721C45A | git hash-object -w --stdin`  
`$ git tag -a maintainer-pgp-pub 659ef797d181633c87ec71ac3f9ba29fe5775b92`
`$ git show maintainer-pgp-pub | gpg --import`

Generate build number  
`$ git describe master`

Releasing  
`` $ git archive master --prefix='project/' | gzip > `git describe master`.tar.g ``  
`` $ git archive master --prefix='project/' --format=zip > `git describe master`.zip ``

Shortlog
`$ git shortlog --no-merges master --not v1.0.1`
