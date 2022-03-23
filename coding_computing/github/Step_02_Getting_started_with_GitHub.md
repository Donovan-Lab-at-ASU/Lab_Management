Getting started with GitHub
================
Written by: Juliette Verstaen \| Last updated on:
March 23, 2022

## Description:

This is a short tutorial created to help people at the very start of
their GitHub journey. At this point everyone should have already
downloaded Git, created a GitHub account, and have successfully
connected RStudio to their GitHub account.

A little background, Git is a version control system which gives you the
ability to go back to a previous version of a file, or code, or whatever
you have saved or committed in the past. There are a couple different
hosting systems that you can use. We’re going to use GitHub, but some
people use GitLab or BitBucket. I’ve definitely had to go back in GitHub
time to find an old version of a file, or a file that had been deleted
by accident, or when I’ve accidentally dumped my entire full HydroFlask
onto my laptop.

Let me preface this by saying that I am not a Git or GitHub master! I’ve
had issues in the past that took me forever to figure out or I had to
ask someone for help. There are a lot of ways and reasons to do things,
but I’ll just share what I’ve learned to do at NCEAS and incorporate it
into my own workflow!

## Topics covered

1.  Creating a github folder for all your repos
2.  Create and Clone a repo
3.  Creating and using access token
4.  Pulling and pushing

## Pre-tutorial readings:

Please read chapter 15, chapter 16, and chapter 17 in
[happygitr](https://happygitwithr.com/) written by Jenny Bryant about
creating repositories (repos) and pulling/pushing. It is honestly
probably gonna be a little confusing, but I hope with the tutorial it
will make more sense. Also it’s a great resource to have in general.
When there are sections for GitHub, GitLab, and GitBucket you only need
to read the GitHub sections.

## Let’s Git it started!!

### Step 1: Create a GitHub folder for all your repos

You will need a folder on your local computer dedicated soley for the
GitHub project repositories you are going to be working with. The
standard convention is to create this folder in your home directory, not
your desktop. So my directory path on my Mac is
Users/julietteverstaen/git_projects/all_my_repos_here, and on my PC it’s
C:\\github_projects\\all_my_repos_here.

## Step 2: Create and clone a repo

Creating a repository or repo on GitHub is very straightforward. Once
it’s created you can clone it and connect it to your RStudio to start
working on your project, or if you’ve already started a project, copy
over the project files onto the repository.

### a. Creating a repo on GitHub

Go to the Donovan Lab repository tab (or the repo tab on your personal
page if it’s not a lab project) and click on the green “New” button.

![create
1](https://github.com/Donovan-Lab-at-ASU/Lab_Management/blob/main/coding_computing/github/pngs/create_repo_1.png)

Now you’ll fill out all the things about your repo.

-   **Repository Name:** For the name choose something specific without
    being too lenghty, and without space. To get around no spaces I use
    “\_” but some people use camelcase (ie: MyRepo) or “-”.
-   **Description:** self explainatory
-   **Public or Private:** Theoretically we should aim to make
    everything we do public, because opendata science is cool!
    Personally I usually start out with my repos on private and then
    switch it over to public once I’m happy with the shape of my code
    and everything. Even on private you can have collaborators on it.
-   **Add a README file:** This is a .md file in the main folder of your
    repo. I always have one and I use it to write up a little
    description of what can be found in the folder. If you go on the lab
    GitHub pages you can see all the README info displayed below the
    list of folders.
-   **.gitignore:** This is something I’ve only recently started to
    incorporate into my workflow. You can add file names here that you
    don’t want on GitHub but that you still want on our local project.
    Basically a list of things you’re telling Git to ignore!
-   **license:** never used this. Maybe one day I will.

![create
2](https://github.com/Donovan-Lab-at-ASU/Lab_Management/blob/main/coding_computing/github/pngs/create_repo_2.png)

### b. Cloning a repo

Cloning a repo is basically just connecting the GitHub repo you’ve just
created to your to local RStudio. We are going to clone the
Lab_Management repository that lives in the Donovan-Lab-at-ASU
organization, but the steps would be exactly the same if you were
cloning a personal repo.

Click on the green “Code” button and a little window will pop up
underneath. There are a couple options under the “Clone” tab but we will
stick tiwht HTTPS. I’ve never used any of the other options, from what I
can tell they’re for more advanced developer type coders (not me!). Copy
the link you see by clicking hte overlapping rectangle icon you see to
the right.

![clone
1](https://github.com/Donovan-Lab-at-ASU/Lab_Management/blob/main/coding_computing/github/pngs/clone_repo_1.png)

Now go and open RStudio and click File-> New Project and a window
labeled “New Project Wizard” will show up. Choose the third option
“Version Control”

![clone
3](https://github.com/Donovan-Lab-at-ASU/Lab_Management/blob/main/coding_computing/github/pngs/clone_repo_3.png)

Choose the option “Git”

![clone
4](https://github.com/Donovan-Lab-at-ASU/Lab_Management/blob/main/coding_computing/github/pngs/clone_repo_4.png)
Paste the link to the repo you copied into the “Repository URL” box. If
you hit tab it will automatically fill out the repo name in the “Project
Directory Name” box. For the last box “Create project as directory” you
will browse and choose the folder you create in step one that is to
house all your github projects/repos. This is going to be your first
one! Yay!! When it’s all filled click “Create Project” and everything
from GitHub will download.

![clone
5](https://github.com/Donovan-Lab-at-ASU/Lab_Management/blob/main/coding_computing/github/pngs/clone_repo_5.png)

**When you’ve already started work on a project and want it on GitHub**
You will go through all of the same steps. Once there is an empty
project living in your github_projects folder you will just copy over
all the files into it. It may be helpful to double check paths that
you’ve explicitly written out in your code, in case there is anything
calling to “Desktop”. If that’s the case I also recommend looking into
the {here} package for workflow ease.

## Step 3: Creating a personal access token

This part is copied and pasted from an issue I wrote on this found
[here](https://github.com/Donovan-Lab-at-ASU/Lab_Management/issues/1).

The new update in August 2021 made it so that we can’t push/pull (which
we will learn about after this!) without authentication which we can do
with a personal access token.

How to create a personal access token:

1.  Go to your Github settings and scroll to “Developer settings” in the
    list on the left
2.  Choose “Personal access tokens”
3.  Click on “Generate new token”
4.  Pick a name for your token and a length of time for it to work. I
    use 90 days, or sometimes a custom time since “no expiration” is not
    recommended. But it’s still an option you can pick! You can always
    delete a token whenever you want and make a new one.
5.  Check whichever boxes you want the token to be used for. I just pick
    the repo ones since I only use it for pushing/pulling at the moment.
    I don’t see what the issue would be with clicking all the boxes
    though. Maybe someone that knows more about this would be able to
    explain it better! Screen shot below of what I click.
6.  Generate token!
7.  It gives you this crazy long string of numbers and letters. I have
    it copied and pasted onto a sticky, not very high security. You can
    always check on the token password whenever in the personal access
    tokens tab.
8.  When pushing and pulling you will now need to use this token instead
    of your Github log in password.

![pat
checkboxes](https://github.com/Donovan-Lab-at-ASU/Lab_Management/blob/main/coding_computing/github/pngs/PAT_checkboxes.png)

## Step 4: Pulling, commiting, and pushing

When you use Github you will become very familiar with pulling and
pushing. Pulling is when you update your local computer repo code with
the updated version that is on Github. Changes to the GitHub version can
be made by other collaborators of if you choose to edit files directly
via GitHub. If there are no changes it will say that you are “Up to
date”. If you are working with collaborators you should always pull when
you first open the repo. Working on an a non updated version and hten
trying to push will cause “Fatal Errors”. These are usually easily fixed
but sometimes it can be a little bit of a nightmare so I try to always
pull when I first open a project to work on, even if I’m the only one
working on it. I need to instill those good habits!

### Pulling

PAT

### Commiting and pushing

### Now you try!
try adding in a line with your name and date on the push_pull_practice and pushing it. Make sure to pull first in case someone has recently added to it
