# Operation

[Reference](https://gitbook.tw/)



## Show status

```
> git status
```



## Show log

```
> git log
```



## Add remote repository

```
> git remote add origin https://github.com/xpire0215/test.git 
```



## Pull files from remote repository

#### Fetch information from remote repository

```
> git fetch
```



#### Pull files

```
> git pull origin master
```



## Push files to remote repository

#### Track the files

```
> git add test.html
```



#### Commit the Staging Area

```
> git commit -m "Initialization"
```



#### Push files to remote repository

```
> git push -u origin master
```



## Branch

#### Show all branch

```
> git branch
```



#### Add a branch

```
> git branch branch-a
```



#### Switch the branch

```
> git checkout branch-a
```



#### Add a branch and switch to the new branch

```
> git checkout -b branch-a
```



#### The current branch with asterisk

```
$ git branch
* branch-a # Current branch
  master
```



#### Change the name branch-a to branch-b

```
> git branch -m branch-a branch-b
```



#### Remove the branch

```
> git branch -d branch-a
```



#### Remove the remote tracking branch (origin/branch)

```
> git branch -d -r origin/branch-a
```



#### Delete the remote branch

```
> git push origin :branch-a
```



## Merge the branch

#### Return to master

```
> git checkout master
```



#### Merge the branch

```
> git merge branch-a
```



## Modify last commit message

```
> git commit --amend
```

