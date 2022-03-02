---
title: Participant guide
date: 2021-05-14
authors:
 - "[James Thomas](https://github.com/jatonline/) ([Jean Golding Institute](https://www.bristol.ac.uk/golding/))"
layout: resource
---

<div class="lead" markdown="1">
# Welcome to the CMIP6 Data Hackathon

**Thank you for taking part!**

This guide explains how the hackathon is being organised, from how we will be
communicating, what activities we envisage you will undertake, how we suggest
you access data and store your code/outputs.
</div>

## Overview
{:.no_toc}

In this guide we'll cover:

* Table of contents
{:toc}

You can also [view this guide as a presentation]({% link resources/participant-briefing.html %}).

## Professional standards

We value the input of all our participants and want everyone to have an
enjoyable experience at our hackathon. All participants and organisers are
required to agree with and follow our [code of conduct]({% link code-of-conduct.md %}),
and this will be enforced this throughout the event. We expect everyone to
behave professionally and show each other respect and courtesy to others
throughout the event. This includes social and fringe events, whether officially
part of the hackathon or not.

As this is a virtual event, we recommend that you take full advantage of the
available resources, including video calling on Zoom and text messaging via
Slack. However we recognise that not everyone is able to or comfortable in doing
this, so please don't pressure others to do so.

**If there is a problem,** then please reach out to one of the organisers via
direct message on Slack (if you feel comfortable doing so), or alternatively
[contact us via email](mailto:cmip6moap-hackathonevent2021@bristol.ac.uk). Our
[code of conduct]({% link code-of-conduct.md %}) also provides other means of
reporting incidents.

## How our event is structured

<div class="aside" markdown="1">
We recommend that during your first breakout group session, you **nominate a
group chair** for your project.

This person should be responsible for ensuring that the group works to the
suggested agenda, the group is ready to present their work during their
presentation slot, and that the code/outputs are well organised.

This is an excellent way of getting some team management experience and so we
emphasise that this person **need not be the project lead listed on the
abstract**.
</div>

Over the three-day hackathon, we have organised:

* A series of introductory talks to kick us off at 9:00am each morning
* Followed by 2 hours of breakout work in project groups
* A guided video yoga session before lunch each day
* Further breakout work in the afternoon, with an additional talk on the second
  day
* Short presentations from selected groups to round off each day

Check the [agenda]({% link agenda.md %}) or the announcements channel on Slack
for more detailed information.

## How we are communicating

We are using:

* **Zoom** for the talks and breakout groups (we will use one Zoom call for the
  duration of the event, and you will be able to move between rooms as you need)
* **Slack** for text-based chat, sharing of ideas, announcements and technical
  support (we have a channel for each project group, plus another channel for
  support from our team of data scientists)
* **Word Online** shared documents (one per project), to record notes, ideas
  and work collaboratively

## How we are storing code, data and outputs

Each project has been assigned:

* A **GitHub repository**, which you can use to share you code and the outcomes
  of your work
* A directory in the hackathon's **Group Workspace**, a shared filesystem on JASMIN that every participant will have read and write access to[^1]

<div class="lead" markdown="1">
We ask that by the end of the hackathon:

1. Your project's GitHub repository has a **README** file, identifying what work
   you did, how far you got and what the next steps required are
2. You identify one (or more) **key figures** that could be showcased at COP26
   in Glasgow
3. Any **code**, **notebooks** and other outputs (**figures**, **graphs**, etc.)
   are committed to your GitHub repository
4. Any **data** outputs are stored, clearly identified, in your project's Group
   Workspace (unless they are small enough to fit on GitHub)
5. Potentially every member of your team will make contributions to the GitHub
   repository, or perhaps you will allocate a member of your team who will be
   responsible for committing everyone's work
</div>

## How to make use of JASMIN

[JASMIN](https://www.jasmin.ac.uk/about/) is the UK's data analysis facility for
environmental science and includes access to the [CEDA Archive](https://www.ceda.ac.uk/).
It is operated by [STFC](https://stfc.ukri.org/) on behalf of [NERC](https://stfc.ukri.org/).

To access JASMIN [you need an account]({% link resources/creating-jasmin-account.md %}).
If you don't already have an account then we will allocate you a temporary
account that you can use for the duration of the hackathon. Bear in mind that
all data in temporary accounts will be removed at the end of the hackathon, so
you must have [saved your data elsewhere](#how-we-are-storing-code-data-and-outputs).

JASMIN provides a large number of services, but we anticipate that most team
members will be using:

* The **[Notebook Service](https://notebooks.jasmin.ac.uk/)**, a service that
  allows users to build and execute Jupyter Notebooks which allows Python 3 to
  be run through a web browser.

  For those of you unfamiliar with Notebooks, we suggest you take a look at some
  [example notebooks](https://github.com/jupyter/jupyter/wiki/A-gallery-of-interesting-Jupyter-Notebooks).
  In essence, Notebooks are an interactive computing environment allowing you to
  combine narrative text (written in [Markdown](https://jupyter-notebook.readthedocs.io/en/stable/examples/Notebook/Working%20With%20Markdown%20Cells.html))
  with code and the output of that code.

  This means they can be made into a complete and self-contained record of a
  computation. They are **well-suited to data visualisation and teaching**. You
  can [recreate an entire journal article](https://nbviewer.ipython.org/github/cossatot/lanf_earthquake_likelihood/blob/master/notebooks/lanf_manuscript_notebook.ipynb),
  [compare different models](https://nbviewer.ipython.org/github/carljv/Will_it_Python/blob/master/ARM/ch5/arsenic_wells_switching.ipynb)
  or [demonstrate a method](https://nbviewer.ipython.org/github/robertodealmeida/notebooks/blob/master/earth_day_data_challenge/Analyzing%20whale%20tracks.ipynb).

However for tasks other than data visualisation, team members more familiar with
JASMIN may also wish to use:

* The **[Scientific analysis servers](https://help.jasmin.ac.uk/article/121-sci-servers)**,
  to run scripts from the command line ([using SSH](https://github.com/cedadev/jasmin-workshop/blob/master/exercises/ex00/))
  or push/pull changes to/from GitHub[^2]
* The **[LOTUS job system](https://help.jasmin.ac.uk/article/4880-batch-scheduler-slurm-overview)**,
  to execute batch jobs for long-running jobs processing large amounts of data

## Where to go for help

<div class="aside" markdown="1">
The best way to contact us during the hackathon is to use the
**[#help channel](https://cmip6moap.slack.com/archives/help) on Slack**, but in
case you have problems with this then you can also our [email mailbox](mailto:cmip6moap-hackathonevent2021@bristol.ac.uk).

We will also have a dedicated help breakout room on Zoom, which we will direct
you to in case we need to talk about your question or share screens.
</div>

The JASMIN website has an excellent set of [documentation](https://help.jasmin.ac.uk/) and [workshop examples](https://github.com/cedadev/jasmin-workshop). If you have
a query about JASMIN then we recommend you take a quick look there first.

Otherwise, we have a team of Data Scientists from the University of Bristol's
[Jean Golding Institute](https://www.bristol.ac.uk/golding/) in addition to a
pool of climate researchers from the universities of Bristol and Exeter, that
will be available throughout the hackathon to offer support and assistance.

Among other things, they can offer help with:

* Hackathon organisation questions
* Using JASMIN
* Using Jupyter Notebooks
* Python technical queries, e.g. pandas, matplotlib, xarray, etc.
* Best practices for reproducibility
* Best practices in data visualisation

## Feedback

We really appreciate your feedback on this hackathon, in the hope that we can
improve future events for yourself and others. Near the end of the hackathon we
will send round a link to a feedback form for you to complete.

#### Notes

[^1]: Note that when using the JASMIN Notebook Service, you only have read-only
      access to Group Workspaces, however when logged in via SSH you will have
      full read/write access.

[^2]: All the Scientific analysis servers will allow you to communicate with
      GitHub using HTTPS, however if you wish to use SSH then you [will need to
      use](https://help.jasmin.ac.uk/article/121-sci-servers) `sci1`, `sci2`,
      `sci4` or `sci5`.
