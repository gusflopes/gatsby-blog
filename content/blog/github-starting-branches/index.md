---
title: "Git Series: Making your first branch"
tags: ["Git"]
published: true
date: '2019-10-21'
---

This tutorial is the second part of a series of posts about Git and Github.
If you missed the first, just checkout: https://blog.gusflopes.dev/github-getting-started/


## What will we do?
This time we will create a new branch on an existing repository, push a update to Github and, after that, create a Pull Request and merge the branches.

## First Step: Creating a new branch and change working branch
For this we want to create a new branch that we will call `newbranch`, and switch to work on that branch. We can do this the long way:

```
git branch newbranch
git checkout newbranch
```

Or we can just use: `git checkout -b newbranch`

The result should be the same. On this last one we are doing both things at the same time.

![](../assets/git-new-repo.gif)

## Second Step: Working on the new branch
Now we are currently on the `newbranch` branch and everything we do here will not reflect on the branch `master` that we were a few seconds ago.

Here we can just make our changes and use the commands we already are used to from the last post: `git add .`, `git commit -m "message"` and ... WAIT!

Ok. Since we just changed branches, we need to use the full `push` comand, setting our upstream, just like when we have a new repository.

So, for the Push, we should use `git push -u origin newbranch`

Notice that we used `newbranch` instead of `master`? Using this command we automatically created a new Branch on Github.

From now on we can use the regular `git push` whenever we need.

![](../assets/git-new-branch.gif)

## Step 3: The Pull Request

Now we are going to create a new file on this branch, `commit` and `push` like explained on the previous item and after that we are going to make a Pull Request.

For the Pull Request I'll prefer to do that directly on the Github website.

For that we can click the button `Compare & pull request`, put a title and description an clikc `Create pull request`.

Github will make a verification for conflitcts and if there is no conflict, it will just show that we are ready to Merge.

So we just need to click `Merge Pull Request`, click on the `Confirm` button and we are ready to go. We can also just delete this branch if we are not going to use anymore by clicking `Delete branch`.

![](../assets/git-pull-request.gif)

## Step 4: Deleting the local branch
Now we can switch back to the `master branch` that will be outdated, because we have a new version on the Github. So we can use these commands to go back to the `master branch` and pull the latest version of our code:

```
git checkout master
git pull
```

That's it. we can just delete the branch that we are not using anymore by typing: 

`git branch -d newbranch`

![](../assets/git-delete-branch.gif)

## Thanks for reading

That's it guys. Thanks for reading. If you guys need any assistance, reach me out on the social medias.

If you want to see the repository, just click this link: https://github.com/gusflopes/gitpost
