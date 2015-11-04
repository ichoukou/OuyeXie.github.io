# Command:

https://www.kernel.org/pub/software/scm/git/docs/git-merge.html

```
```
<div>
<code>
git log (show commit history)  
git rev-list --all --pretty=oneline (show commit history,all and output one line per commit)  
git diff-tree -r -c -M -C --no-commit-id <commit-sha> (to get blobs created by commit, recurse to subdirs, show merge commits, detect renames and copies, don't show commit id on first line)  
git reset --hard 0d1d7fc32  
git push origin HEAD --force  
git pull origin other-branch  
git add --all src/mongo-cxx-driver-v2.4/* //for deleted folder and files  
git commit --amend -m "New commit message" If you've already pushed, just force push again:   
git push -f origin branchname http://stackoverflow.com/questions/179123/how-do-i-edit-an-incorrect-commit-message-in-git  
git checkout -b test origin/test  
git checkout better_branch (change master)  
git merge --strategy=ours master # keep the content of this branch, but record a merge # git checkout master  
git merge better_branch # fast-forward master up to the merge  
git push origin develop (push a single branch)  
git pull -Xtheirs  
git merge --strategy-option theirs￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼  
git rebase -s recursive -X theirs ${branch} git fetch origin master  
git log -p master..origin/master  
git merge origin/master git remote show origin  
git push origin --delete ${branch}  
git branch -m release backup20140106 (rename)  
git push origin :release  
git push origin backup20140106  
git branch --set-upstream my_branch origin/my_branch  
git remote prune origin  
git fetch filod  
git merge filod/master  
git push filod ouyexie:migration
git push filod ouyexie:migration
git pull --rebase filod migration //quick way: http://www.yiibai.com/git/git_pull.html
git commit -a -m "test" --no-verify //skip pre-commit hook
git reset --soft asdfasdf //when you mis-commit something (left something for example) (git commit -c ORIG_HEAD )
</code>
</div>


# Tag Command:

```
```
<div>
<code>
git tag -a 6.x-1.0  
git tag -a 6.x-1.0 965e066  
git push origin tag_name  
git push --tags  
git push origin :/refs/tags/tagname  
git ls-remote --tags origin  
git push origin --delete tag <tagname>
</code>
</div>

# SSH Key:
You need to copy your private keys from H1 to H2, if you want to use your private keys to be able to login from H2 to S1. When you at H1 do the commands:

```
H1$ ssh H2 mkdir /.ssh  H1$ scp ~/.ssh/id_rsa ~/.ssh/id_dsa H2:/.ssh/
```

Warning! This will delete and replace any private key you have at H2.

# Reference:

 - http://codeinthehole.com/writing/tips-for-using-a-git-pre-commit-hook/
 - http://stackoverflow.com/questions/927358/how-do-you-undo-the-last-commit
