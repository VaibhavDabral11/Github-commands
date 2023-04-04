# Github-commands (**Important git commands)

command 1. ```touch .gitignore```

command 2. ```git config --global user.name vaibhav```
 
command 3. ```git config --global user.email youremail@example.com```
 
command 4. ``` git config --list```

command 5. ```git init```
 
command 6. ```git add .```
 
command 7. ```$ git commit -m "Initial Commit"```
 
command 8. ```$ git status``` # Just to see
 
command 9. ```$ ssh-keygen -t rsa -b 4096 -C "youremail@example.com"```
 
command 10.``` $ cat <path to id_rsa.pub>``` # Add this key to your GitHub account 
 
command 11. ```$ git remote add orign <ssh url.git>```
 
command 12. ```$ git push origin master```
 
command 13.  ```$ cloc $(git ls-files)```(for counting lines)
 
command 14. ```$ git remote -v```

```
orign https://github.com/VaibhavDabral11/Gym-website.git (fetch)
orign https://github.com/VaibhavDabral11/Gym-website.git (push)
 ```
command 15. ```$ git remote add origin git@github.com:VaibhavDabral11/Gym-website.git``` (add git remote shh repo)
  
command 16. ```$ git remote remove orign ```( for remove orign)

command 17 ```$ git rebase --continue ```

command 18. ``` $ git push -u origin master ``` (for push)

command 19. ``` $ git pull --rebase origin master``` (for rebased and update branch)
 
command 20.  ```$  git checkout master```  ( for switching branch )

command 21.

``` interactive rebase in progress; onto d8cf59a
Last command done (1 command done):
   pick c1ff652 developing routes
No commands remaining.
You are currently editing a commit while rebasing branch 'master' on 'd8cf59a'.
  (use "git commit --amend" to amend the current commit)
  (use "git rebase --continue" once you are satisfied with your changes)

nothing to commit, working tree clean
 ```
command 22:
### code Backup

 ### UPDATE: A better way! (August 2015)

As pointed out by @johntyree in the comments, using [git reflog](http://git-scm.com/docs/git-reflog) is easier and more reliable. Thanks for the suggestion!

```
 $ git reflog
1ed7510 HEAD@{1}: checkout: moving from develop to 1ed7510
3970d09 HEAD@{2}: checkout: moving from b-fix-build to develop
1ed7510 HEAD@{3}: commit: got everything working the way I want
70b3696 HEAD@{4}: commit: upgrade rails, do some refactoring
98f2fc2 HEAD@{5}: commit: a couple code cleanups
d09f35e HEAD@{6}: commit: remove test method - it served it's purpose and now it must go
d586a93 HEAD@{10}: commit: aha! that is why I'm so fail
4644046 HEAD@{11}: commit: cleaning up the initial migration for dev/test environments
323df37 HEAD@{15}: commit: bump ruby version
eab861c HEAD@{16}: commit: bundle update EVERYTHING
2b544c4 HEAD@{17}: commit: fixing what few tests actually exist - a.k.a., wow! does this app even work?
3970d09 HEAD@{18}: checkout: moving from develop to b-fix-build
3970d09 HEAD@{19}: pull: Fast-forward
```

Once you find the commit you're looking for, create a new branch from it and you're done!

```sh
$ git checkout -b branch-name 70b3696
Switched to a new branch 'branch-name'
```


### Original post

Oops! I accidentally deleted a local git branch, and I haven't pushed it to a remote server yet. The branch has several important commits, and it hasn't been merged with any other branches yet. How do I find the missing branch?

### 1. Create a list of all dangling or unreachable commits.

```sh
$ git fsck --full --no-reflogs --unreachable --lost-found
unreachable tree 4a407b1b09e0d8a16be70aa1547332432a698e18
unreachable tree 5040d8cf08c78119e66b9a3f8c4b61a240229259
unreachable tree 60c0ce61b040f5e604850f747f525e88043dae12
unreachable tree f080522d06b9853a2f18eeeb898724da4af7aed9
unreachable blob bf01f514add2ada00a7ae5c666493d30d639018c
...
```

These commits are copied into `.git/lost-found/commit/`, and non-commit objects are copied into `.git/lost-found/other/`.

### 2. Print a list of commit messages for all commits in the lost and found.

```sh
$ ls -1 .git/lost-found/commit/ | xargs -n 1 git log -n 1 --pretty=oneline
63b65d3784b16f92bb370ad6a2c1091a05824ecc Call #to_s on value before calling some string methods, like gsub
6ed99e63db69ca04f0cc78081a1fd471289551b2 On master: search and reset page
973d9be3e2cefcd0c5801ad9cd1b2e18774b4bee Rename decorator proxy to decorator context
9ae38fc6b0548cab08ccee1178db0ba0edeafdb2 foo
9e994ca0c0c4785ab45bf64b367fdacccc4575a9 foo [#12345]
9efa6b28b3b0a89c312484f28cf589385d613dfd On master: mysql db config
c57a67c7e1c21fa0c32f152e73d8c3376cad19a0 bar
cb3d67e1aa2226ab9d816fc541f36ff698bfda41 WIP on master: 40a4453 Use #website_url instead of #template_url or #url
def0a251bd29b7fc54a5622e364711f60097b826 Example tabs for export show page (no styles)w
```

### 3. Find your missing commit through the process of manual inspection (i.e. reading).

If you need more information on a commit, you can always use a more detailed log command, such as `git log -p --stat --color 9ae38fc`.

### 4. Create a new branch with the missing commit as the branch head.

```sh
$ git checkout -b branch-name 9ae38fc
Switched to a new branch 'branch-name'
```

## Commands
command 23:  This commands is use to changing the name of the branch . 

```@ruby  
$  git branch -m old_branch_name new_branch_name

$  git push origin -u new_branch_name
```
