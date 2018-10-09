# Step-by-Step technical guide for your first open source contribution

## Choose a project and issue to work on
A set of files for a project is called a Repository, and Issues are where people ask for help fixing things.

When you’re new to a project, it’s a good idea to comment on an Issue that you want to help with and ask some questions before doing any major coding work. To see the Issues, click on the tab for it. Many open source projects use tags like “Good for new contributors” or “help wanted” to indicate which Issues might be best to jump in on. Don’t be surprised if it takes days for someone to reply. Most open source maintainers do a little work here and there in their free time, and no one pays them for it (unless they are very, very lucky). “Maintainers” is sometimes a formal title but often it means the people who are most actively contributing or reviewing changes.

![Repo](https://github.com/soulspark666/Hacktoberfest-starter/blob/master/Screenshots/3.png)
<br>

![Issue](https://github.com/soulspark666/Hacktoberfest-starter/blob/master/Screenshots/Issue.png)
<p align="center">
  The list of Issues in a Repository
</p>

## Fork this Repository
To fork a repository, look for the “Fork” button in the top right corner of a project’s GitHub page. A fork is your own personal copy of the project that you control. You can make changes and play around without affecting anyone else’s work.

![Fork](https://github.com/soulspark666/Hacktoberfest-starter/blob/master/Screenshots/2.png)
<p align="center">
    Click “Fork” to get your own personal copy of the project
  <br>
</p>

![Forked](https://github.com/soulspark666/Hacktoberfest-starter/blob/master/Screenshots/5.png)
<p align="center">
  Here’s the fork that’s under my username now.
</p>

## Clone the repository with the command
For this step, you’ll need to have git installed. Git is a program that helps you save the changes you’ll be making on your computer and then share them online. To be clear, git is a program you run on your computer. GitHub is an online website where it’s easy to store and share code.
In the command line, navigate to the folder where you want to save the repository. On a Linux/Mac, ls will list the contents of the folder you’re in. cd foldername will open up a folder you saw in the list. cd .. will take you up one level. mkdir foldername will create a new folder.
Once you are inside the right folder, type

  ```git clone <repository_link>```
 
 Hit enter, and your project will start downloading. cd into the folder you just opened.

![Clone](https://github.com/soulspark666/Hacktoberfest-starter/blob/master/Screenshots/7.png)
<p align="center">
    The url you’ll need to copy in order to clone the repository fork
  <br>
</p>

## After cloning, create a new branch with the command
If you type git status you will see the branch name that you’re on, called master. In most projects, master is a special place where the most stable, reviewed, up-to-date code is. So, you’ll need to make your own branch:

```git branch a-descriptive-name```

Then switch to that branch:

```git checkout name-for-your-branch```

![Branch](https://github.com/soulspark666/Hacktoberfest-starter/blob/master/Screenshots/4.png)

## Install dependencies  
Almost every open source project uses other open source projects within their codebase — tools for running servers, parsing times and dates, animating, etc. These are referred to as dependencies. For example, if you are helping with a JavaScript project, you’ll probably need npm. If you’re working on an Ember app, you need npm and the ember-cli. A good open source project will have detailed instructions on how to install the dependencies in its ```README.md``` and ```CONTRIBUTING.md``` files.

## Make some commits (aka do the work)
When you have some code that you want to keep, you should save it in git by creating a commit. Here’s how:

```git status``` will show you the files you changed.

```git add path-to-your-file``` will allow you to pre-select the files you want to save. Add the files one at a time.

```git status``` again to make sure you added the files you want to keep your work from

```git commit -m "some message here #123"``` will group your changes together into a commit. The message should be short, describe the work that you did, and include the issue number that you are working on.

```git push origin name-for-your-branch``` to save your work online. You’ll be prompted for your git username and password. Up until you type this command, your work has only been saved on your computer. After this, if you look at your Fork on GitHub, you should see your branch and commit.

![Commits](https://github.com/soulspark666/Hacktoberfest-starter/blob/master/Screenshots/1.png)

## Open a Pull Request (aka PR)
A Pull Request is the way to notify the project maintainers that you have some work that they should review and add to the project. You’re requesting that they pull your changes in.

To create one, go to your fork of the project, click on the Pull Requests tab, and click the big green “New Pull Request” button.

![Pull](https://github.com/soulspark666/Hacktoberfest-starter/blob/master/Screenshots/6.png)

- On the next screen, the “base fork” should automatically be the main project and the master branch. Leave them as they are for most projects. The “base fork” will include your name.
- In the “compare” dropdown, choose the branch name you were working on.
- Click the green “Create Pull Request” button.

In the comments section, say a sentence or two summarizing the work you did. Include a link to the Issue you were working on. It might be helpful to mention something like “This is my first PR. Let me know if you have any feedback!” This way the maintainers know to give you more detailed pointers if something should be changed before it’s added to the main codebase.

- Choose the big green “Create Pull Request” again to save your comment and finish making the PR. Leave the box checked that says “allow edits from maintainers.”

## Merge of Pull Request
Congratulations and thank you for giving back to the open source community :) This whole thing only works because of people like you.

## Updating your fork
Ok, so what happens if you were working on a pull request or some time has gone by since you cloned the repository? Possibly the ```master``` code has changed a lot. How do you get those changes into your fork so that you’re working off the latest code? Grab the “clone or download” url from the project (the home repository, not your fork) and do these commands:

```
git checkout master
git remote add upstream the-clone-https-url
git pull upstream master
git push origin master
```
Now you can create new branches to do your work on. ```git checkout master``` switched to the master branch. ```git remote add``` helped you create a label called “upstream” that is connected to the url for the main project. So then when you “pull” the changes down onto your hard drive, you’re pulling the code that lives at the “upstream” url for the main project. ```git push origin master``` makes your fork (the “origin”) be synced up with what’s on your hard drive.

But what if you also have some work that was in progress? You’re working on code that’s out of date, so how do you combine it with the most up to date code? You need to do something called a ```rebase```. A rebase takes your current branch and applies the changes you made to the branch that you specify in the command (in the example below, it’s ```master``` ).

```git checkout your-branch-name
git rebase master
git pull upstream master
git push origin master
```
