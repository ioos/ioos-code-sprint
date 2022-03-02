---
title: Using Git during the hackathon
date: 2021-05-27
authors:
 - "[James Thomas](https://github.com/jatonline/) ([Jean Golding Institute](https://www.bristol.ac.uk/golding/))"
layout: resource
---

<div class="lead" markdown="1">
# A guide using Git to collaborate during the hackathon

This guide gives some suggestions on how to use your project's GitHub repository
during the hackathon, with some links to training material for Git and GitHub,
if you'd like to learn more.

In summary:
* Each project has a [GitHub repo](https://github.com/cmip6moap) – use this for
  code, outputs and small amounts of data
* Each project also has a directory in our shared Group Workspace:
  `/gws/pw/j05/cop26_hackathons/bristol`
* Don't worry if this is new to you!
* Working as a team, decide what you're going to use and who will be responsible
  for saving outputs
* We ask each project to structure their work clearly, and give some guidance
  below on how you might do that
</div>

## Overview
{:.no_toc}

In this guide we'll cover:

* Table of contents
{:toc}

## Finding your project's GitHub repository

Each project has its own repository (or *repo*) within our [GitHub organisation](https://github.com/cmip6moap):

1. [What is the transient sea level sensitivity in CMIP6 models?](https://github.com/cmip6moap/project01)
2. [How well do the CMIP6 models represent the tropical rainfall belt over Africa?](https://github.com/cmip6moap/project02)
3. [Characterising the marine carbon cycle in CMIP6](https://github.com/cmip6moap/project03)
4. [Testing proxies of AMOC variability in CMIP6](https://github.com/cmip6moap/project04)
5. [The atmospheric response to sea-ice loss in the PAMIP experiments and its sensitivity to model biases](https://github.com/cmip6moap/project05)
6. [Differences between 'turning down the sun' and stratospheric sulfate injection](https://github.com/cmip6moap/project06)
7. [Uncertainty in sea-ice-cloud feedbacks across the CMIP6 ensemble](https://github.com/cmip6moap/project07)
8. [Interactive graphics of key CMIP6-based IPCC figures](https://github.com/cmip6moap/project08)
9. [Impacts of changing wind regimes and sea ice on the world's longest migrant](https://github.com/cmip6moap/project09)
10. [Human heat stress in a warming world](https://github.com/cmip6moap/project10)
11. [Rainfall extremes and groundwater recharge in the tropics](https://github.com/cmip6moap/project11)

## Getting access to your project's repo

All the repos are public which means anyone can read their contents, but you
will need to have supplied us with your [GitHub username](https://github.com/join)
to be able to make changes to them (we sent round a spreadsheet for you to fill
in, but during the event you can use the **#help channel** on Slack if you don't
have access).

All repos are licensed under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/)
which means that anyone can share and adapt anything in the repository as long
as they give appropriate credit, link to the CC BY 4.0 license and indicate if
they themselves made changes. If you commit work to the repo then you are
indicating that you (or the members of your team for whom you are committing),
are happy with this.

Other than cloning a public repo, most of the commands you will need to run to
work with Git and GitHub will require you to use the command line – for JASMIN
you will need to connect via SSH. The default text editor on JASMIN is Vim, so
you may need to take a look at this [Vim command reference](https://vim.rtorr.com/).

## How to work collaboratively

Each project has been assigned:

* A **GitHub repository**, which you can use to share you code and the outcomes
  of your work
* A directory in the hackathon's **Group Workspace**, a shared filesystem on
  JASMIN that every participant will have read and write access to (write access
  requires SSH)

Git and GitHub are both extremely powerful, however we recognise that many
participants may have **little or no experience** in using them before the
event. Whilst we want to promote best practice and will be using GitHub to share
the outputs of the hackathon, please don't feel you can't contribute if you're
not familiar with using either Git or GitHub.

We encourage you to make use of the expertise in your project team. It is likely
that at least one of you is confident enough to use Git, and if this is the case
then we recommend you allocate them to work with Git on your behalf. Within your
team, you can share code and outputs using you project's **Group Workspace**
directory on JASMIN (for example `/gws/pw/j05/cop26_hackathons/bristol/project01`
for project 1). Then at the end of each day, that person can commit all the
changes to Git and push them to GitHub.

If you are all proficient users, then feel free to make feature branches, raise
issues, fork the repository and make pull requests. However please agree as a
team how you're going to work and ensure that **everyone is able to follow your
agreed way of working**.

## What we ask of you

<div class="lead" markdown="1">
We ask that by the end of the hackathon:

1. Your project's GitHub repository has a [**README** file](#suggested-readme-contents),
   identifying what work you did, how far you got and what the next steps are
2. You identify one (or more) **key figures** that could be showcased at COP26
   in Glasgow
3. Any **notebooks**, **code** and other outputs (**figures**, **graphs**, etc.)
   are committed to your GitHub repository
4. Any **data** outputs are stored, clearly identified, in your project's Group
   Workspace (unless they are small enough to fit on GitHub)
5. Potentially every member of your team will make contributions to the GitHub
   repository, or perhaps you will allocate a member of your team who will be
   responsible for committing everyone's work
</div>

### Suggested repo structure

    .
    ├── notebooks
    │   ├── 01_Data_exploration.ipynb
    │   │── 02_Data_analysis.ipynb
    │   └── 03_Data_visualisation.ipynb
    │           The Jupyter Notebooks that you created, making sure to structure
    │           them clearly (see below) – add a README to explain them
    │
    ├── code
    │   ├── data_cleaning.py
    │   └── extra_data_download.py
    │           Any code (Python or otherwise) that you created that doesn't
    │           sit within a Notebook (for example, larger data processing tasks
    │           that ran on the Scientific Analysis Servers, or batch processing
    │           performed on LOTUS) – add a README to explain them
    │
    ├── results
    │   ├── figure1.pdf
    │   └── figure2.png
    │           The key figures that you produced (possibly extracted from your
    │           notebooks) – add a README to explain them
    │
    ├── data
    │   ├── raw_data
    │   │       Any data you used that didn't come from JASMIN (if the data is
    │   │       too large to commit, then you might just provide a README
    │   │       explaining how to obtain it)
    │   │
    │   └── processed_data
    │           Any output data that you produced (if the data is too large to
    │           commit, then you might just provide a README explaining where it
    │           is stored on the Group Workspace)
    │
    ├── .gitignore
    │       Keep some local files abd directories out of the repo (such as
    │       __pycache__/ and .ipynb_checkpoints/)
    │
    ├── environment.yml
    ├── environment_frozen.yml
    │       The libraries and versions that you used (if these were different
    │       from those that were pre-installed for the hackathon)
    │
    ├── LICENCE
    │       CC BY 4.0
    │
    └── README.md
            See below

### Suggested README contents

* Project information
  * Title
  * Summary
  * Contributors list (with links to GitHub profiles / institution pages, etc.)
* Overview of what was done
  * How did you approach the problem and why?
  * What data did you use and how can this be obtained?
  * What work did you complete during the hackathon?
  * What were the outcomes?
* Navigating the repo
  * Where to find the notebooks, data, code in the repo
  * An explanation of what key files are
  * How to reproduce the outputs of the hackathon
* What the next steps are for the project

### Suggested Notebook structure

* Notebook title
* Short summary
* Contributors
* Mix of subtitles, Markdown and code cells

Try to use [Markdown cells](https://jupyter-notebook.readthedocs.io/en/stable/examples/Notebook/Working%20With%20Markdown%20Cells.html)
so that your notebook reads as if it were an article that someone would read.
With the Markdown cells, you should aim to describe what analysis you're doing
and why, along with any observations. This is slightly different to how you
would (and should!) use `# comments` in code to describe the buts and bolts of
what is going on in greater detail.

Here are some polished notebooks as inspiration:

* [Recreating an entire journal article](https://nbviewer.ipython.org/github/cossatot/lanf_earthquake_likelihood/blob/master/notebooks/lanf_manuscript_notebook.ipynb)
* [Comparing different models](https://nbviewer.ipython.org/github/carljv/Will_it_Python/blob/master/ARM/ch5/arsenic_wells_switching.ipynb)
* [Demonstrating a method](https://nbviewer.ipython.org/github/robertodealmeida/notebooks/blob/master/earth_day_data_challenge/Analyzing%20whale%20tracks.ipynb)

## Some common Git commands

Adapted from the excellent ACRC [Introducing Version Control with Git](https://chryswoods.com/git_collaboration/summary.html)
course ([CC BY 4.0](https://creativecommons.org/licenses/by/4.0/)):

Command | Explanation
------- | -----------
`git clone URL` | Clone (download) a local copy of the remote repository that is available at the specified URL. You will only be allowed to push to that repository if you have permission
`git status` | Tell git to print the status of the files in the version controlled directory
`git diff` | Tell git to show the differences between the files in the working directory and the last saved version in the git repository. This will show the differences for all tracked files. Use `git diff FILENAME` to limit to only the file `FILENAME`
`git add` | Tell git to start monitoring (tracking) the versions of a new file, for example `git add README.md` will tell git to track `README.md`
`git commit -a` | Tell git to save a new snapshot version of all of the tracked files in the directory. The `-a` means "all tracked files". You can commit new versions of individual files if you want, but this is not recommended.
`git log` | Print a log of the versions in the repository. Use `git log -n N` to limit to the last `N` versions. You may need to use `q` to exit from the text viewer if there are a lot of versions to print.
`git push` | Push versions that are saved in the local repository (.git folder) so they are backed up to a remote repository (.git folder)
`git pull` | Pull changes from the remote repository into the local repository. This is the opposite of git push
{:.command-ref}

<style> .command-ref tr td:first-child { white-space: nowrap; } </style>

## Finding out more about Git and GitHub

If you'd like to find out more about version control, Git and GitHub, then the
University of Bristol [Advanced Computing Research Centre](https://www.bristol.ac.uk/acrc/)
has made some of their course material free available:

* [Introducing Version Control with Git](https://chryswoods.com/introducing_git/)
  course, also available as a [YouTube video](https://youtu.be/OqiZu-xFvPw)
* [Git for Collaboration](https://chryswoods.com/git_collaboration/) course,
  also available as a [YouTube video](https://youtu.be/ZPaanySK9h0)
