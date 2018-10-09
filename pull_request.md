# Pull Request Template

## Fork this Repository
To fork a repository, look for the “Fork” button in the top right corner of a project’s GitHub page. A fork is your own personal copy of the project that you control. You can make changes and play around without affecting anyone else’s work.

## Clone the repository with the command
For this step, you’ll need to have git installed. Git is a program that helps you save the changes you’ll be making on your computer and then share them online. To be clear, git is a program you run on your computer. GitHub is an online website where it’s easy to store and share code.
In the command line, navigate to the folder where you want to save the repository. On a Linux/Mac, ls will list the contents of the folder you’re in. cd foldername will open up a folder you saw in the list. cd .. will take you up one level. mkdir foldername will create a new folder.
Once you are inside the right folder, type
  ```git clone <repository_link>```.
 Hit enter, and your project will start downloading. cd into the folder you just opened.
  
## After cloning, create a new branch with the command
If you type git status you will see the branch name that you’re on, called master. In most projects, master is a special place where the most stable, reviewed, up-to-date code is. So, you’ll need to make your own branch:

```git branch a-descriptive-name```

Then switch to that branch:

```git checkout name-for-your-branch```

## Install dependencies  
Almost every open source project uses other open source projects within their codebase — tools for running servers, parsing times and dates, animating, etc. These are referred to as dependencies. For example, if you are helping with a JavaScript project, you’ll probably need npm. If you’re working on an Ember app, you need npm and the ember-cli. A good open source project will have detailed instructions on how to install the dependencies in its ```README.md``` and ```CONTRIBUTING.md``` files.

## Make some commits (aka do the work)
When you have some code that you want to keep, you should save it in git by creating a commit. Here’s how:

```git status``` will show you the files you changed.

```git add path-to-your-file``` will allow you to pre-select the files you want to save. Add the files one at a time.

```git status``` again to make sure you added the files you want to keep your work from

```git commit -m "some message here #123"``` will group your changes together into a commit. The message should be short, describe the work that you did, and include the issue number that you are working on.

```git push origin name-for-your-branch``` to save your work online. You’ll be prompted for your git username and password. Up until you type this command, your work has only been saved on your computer. After this, if you look at your Fork on GitHub, you should see your branch and commit.

## Open a Pull Request (aka PR)
A Pull Request is the way to notify the project maintainers that you have some work that they should review and add to the project. You’re requesting that they pull your changes in.

To create one, go to your fork of the project, click on the Pull Requests tab, and click the big green “New Pull Request” button.

  
- Then a new "Create Pull request" button appears on the github screen.
- Click the button to create a new Pull request. 
