---
title: "First steps on Git and GitHub"
tags: ["Git"]
published: true
date: '2019-10-10'
---

## First steps on Git 
For a new developer the learning curve could be overwhelming sometimes. It's just too much to learn that you don't know where to start. There are the basic for web development (HTML5/CSS3/Javascript), but there are also a lot of languages for different things: C#, Node.js, Python, Ruby on Rails, React, Angular.js, Vue.js...

So, after a lot of consideration you manage to organize your thoughts, and a bunch of researching (courses, videos, tutorials, ebooks...), and not before you learn a few basic stuff about web development (HTML, CSS and Javascript) you decide to learn a stack like Node.js + React + React Native (like me).

And that happens again: Git, Github, Docker, Netlify, Gatsby.js, AWS, testing, deploy... Ok. You got lost again and decide to skip all that for now. Just focus on the programming language you decided, right?

Not so fast!! Let me tell you how Git and Github can help you!

## The perfect tool to keep track of your progress
This is supposed to be a guide from a new developer to another new developer. As you can see on my github, my last github account was created  in 2016. However I started using it only in 2019.

So what happened? The main reason is that I was focusing on other things on that period, but I still was learning one thing or other during that time. Just not using Github.

Since I didn't use my Github account when studying, I have a lot of projects/repositories on my computer, spread across all the  hard drive, and I have no clue wich one is working, completed, or just started and left before I finished.

Other reason to use github is because most of the job interviews nowadays starts on the github. If anyone needs to know if you are developer, he just needs to start with your github. That is your real curriculum.

### Configuring and setting up a SSH-Key

Are you convinced? Ok. Then let's install it.

It is pretty straightforward to start using Github. You'll need to install Git on your computer and you can use it from your terminal. If you are a Windows user you will also need to install Git Bash.

Just access https://help.github.com/en and you can find the step by step guide on the Getting Started section. Or you can follow these steps:

1- Set up git: https://help.github.com/en/articles/set-up-git
2- Generate a SSH key: https://help.github.com/en/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent
3- Add a new SSH key to your GitHub account: https://help.github.com/en/articles/adding-a-new-ssh-key-to-your-github-account

4- Create your first repository: https://help.github.com/en/articles/create-a-repo

If you did all these steps, you now have a GitHub account, the Git installed locally, a SSH-Key so you can connect to your account over SSH insted of typing your username and password all the time, and a first repository.

### The basic commands to deal with local repositories

Basically you need to understand just a few verbs from git: `init`, `add`, `commit`, `push` and `pull`. The first thing you need to do is to start your local repository:

- `git init`
> start a local repository;

After that, you'll create new files or make changes to them and when you are ready you'll use 2 commands, `add` and `commit`, like this:

- `git add .`
> Add (stage) all files on the folder and subfolders for the next commit;
- `git commit -m 'a message'`
> Like a screenshot of the current state of the repo;

This is the most important part. You'll create new features, fix bugs, and then commit it so if you need to comeback to this point later, you can just go  to that version of the code (*more on that later*).

### Actually using GitHub: dealing with remote repositories

By now you are already keeping track of your code, but it is saved just locally. For being able to share or download the code on any other computer you just need to use your **remote repository** from GitHub.

For that you just need to create and configure your **remote repository**. You will go to your GitHub account and create a new repository, like this:

![](../assets/github-new-repo.gif)

Now you just need to push your local files to your remote repository, and you will do that by using `remote add` and `push -u`, like this:

- `git remote add git@github.com:USER/REPOSITORY.git`
> You will just change the `USER` for your username, and `REPOSITORY` for your repository name (that you just created) - on my case, it is `gusflopes` and `template`;

- `git push -u origin master`
> With this command you will push you local repository *(named 'master')* to your remote repository *(named 'origin')*, and by using the `-u` you basically is using the parameter `--set-upstream`, so now you don't need to type everything anymore.

That's it. Your local and remote repository are already configured and you can just start working.

### What should I do now?

From now on you just need follow this routine:
- `git add .`
- `git commit -m "your  message"`
- `git push`
>By doing so, you basically take snapshots of your code, and eventually it will look something like this:

![](../assets/github-commit.png)

As you can see, for each commit I implemented something new to the code. This repository is basically a REST Api built with Node.js, and on the last commit is basically a boiler plate. So even if I go further and build a lot more features, I can alway download that snapshot and start a new project without needing to go back to scratch.

### Review

**If you don't want that much explanation and just need a quick fix, this section is for you!**

Basically we have three ways of doing the initial setup:

#### Method #1 - Creating the repository on the GitHub
You can create the repository first on GitHub and the you can copy the first option they provide. After that just create a new folder and `Ctrl + V` the commands you just  copied, like on this video:
![](../assets/github-new-repo.gif)

#### Method #2 - Start your repository locally
On this method you can **just start your repository locally**  and when you are ready to make the first commit, you will create your GitHub repository.
So you are going to use `git init`, then `git add .`, and finally `git commit -m 'message'`. After that you will make your repository on  GitHub and just finish pushing the local repository (2nd option on GitHub screen), or the following commands:
- `git remote add origin git@github.com:USER/REPOSITORY.git`
- `git push -u origin master`
> Something like this:

![](../assets/github-pushing-local-repo.gif)

#### Method #3 - Everything from commandline
In my opinion, this is the coolest method, since **you don't need your browser**. Everything will be done on your terminal.

You just need to create a repository using GitHub API, and you can do that  by using the following command:

`curl -u 'USER' https://api.github.com/user/repos -d '{"name":"REPOSITORY"}'`
> You basically will change USER for your username (in my case, i'll replace USER for gusflopes), and REPOSITORY for your repository name (in my case, REPOSITORY for template), and it should look like this:

`curl -u 'gusflopes' https://api.github.com/user/repos -d '{"name":"template3"}'`

![](../assets/github-new-repo-terminal.gif)

After creating the remote repository and your first files, you just need to use the commands of the first method, that is basically this:

```
git init
git add .
git commit -m "first commit"
git remote add origin git@github.com:USER/REPOSITORY.git
git push -u origin master
```
Just remeber to change USER and REPOSITORY like you did when you created the repository.

#### When you already have a repository
After creating your local and remote repository, you will just keep using these commands to commit the updates you make on your code:
```
git add .
git commit -m 'message'
git push
```

###  Thanks!

Thanks for reading and if you liked it, please share!

By the way, Git is so powerful that I'll just save and commit this post on my local repository of this Blog and, when I push it to GitHub, it will just update my Blog, like this:

![](../assets/github-update-blog.gif)

**_Gustavo Lopes_**