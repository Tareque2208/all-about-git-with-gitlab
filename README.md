# Git-CheatSheet

## Getting  Started

### Installation
Download `git` and install from [https://git-scm.com/downloads](https://git-scm.com/downloads)
### Configuring the user information
```sh
git config --global user.name "[name]"
git config --global user.email "[email address]"
git config --global color.ui auto
```
### Stage & Snapshot

  ```sh
  git clone https_url

# Checking the list of remote and local branchs
  git branch -a
      
# Checking the list of Only remote branchs
  git branch -r
    
# Checking the list of Only local branchs
  git branch
  
# Creating and check out in a local branch
  git checkout -b local_branch_name_1
  
# After making changes and checking updates in my current branch
  git status
  
# See the difference here and press 'q' to get out
  git diff

# Add all changes in the commit history
  git add .

# Or we can Add specific changed files in the commit history
  git add <file_url.type>

# We can reset back to Head of a specific file
  git reset <file_url.type>
  
# commiting updates for the local branch
  git commit -m "updates"
  
# pushing local branch
  git push
  
# pushing local branch and set the remote as upstream
  git push --set-upstream origin local_dev1

# Or to checkout a remote branch
  git checkout remote_branch_name

# Now pushing to another remote branch
  git push origin remote_branch_where_I_want_to_push

# fetching is prefereable
  git fetch

# Now pull from another remote branch
  git pull origin remote_branch_where_I_want_to_pull

# Now resolve the conflicts and do merge in the local_branch then add all and commit as merging conflict resolve and then just push
  git add .
  git commit -m "merge conflict resolve"
  git push

  ```

  ### Stashing/ Temporary Commits

  ```sh
# Stashing is basically used while we got to pull from a branch but we don't want to lose our changes and don't want to commit and push them. So by saving the changes locally in a stack and popping them we can get them back again.

#check the changes
  git status

#don't want to lose the changes but have to pull from a branch. So, lets just stash them with a message
  git stash push -m "my_new_stash"
  git pull origin another_remote_branch

#checking the list of stashs
  git stash list

#popping stash@{0} to commit 
  git stash pop

#clearing all the stashes
  git stash clear
  ```

  ### Multiple Stashing

  ```sh
  git stash push -m "my_new_stash"
  git pull origin another_remote_branch
  
  #after resolving the conflicts, push to merge locally
  git push
  
  #make changes without popping the stash and need to pull again
  git stash push -m "another_new_stash"
  
  #check your list of stashs, we will have 2 stashs
  #shash@{0}: on local_dev_branch : my_new_stash
  #shash@{1}: on local_dev_branch : another_new_stash
  git stash list
  
  #now pull, resolve conflict, push again and then pop a specific stash. But stash pop will apply exactly stash@{0}.
  git stash apply stash@{n}
  
  #now drop specific stash
  git stash drop stash@{n}

  ```
