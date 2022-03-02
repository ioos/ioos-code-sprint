---
title: Running a Hackathon on JASMIN
date: 2021-05-06
authors:
 - "[James Thomas](https://github.com/jatonline/) ([Jean Golding Institute](https://www.bristol.ac.uk/golding/))"
layout: resource
---

<div class="lead" markdown="1">
# A guide to running an event on the JASMIN data analysis facility

This guide is based on the experiences of the University of Bristol in
organising a CMIP6 Hackathon in association with the Met Office Academic
Partners. It describes how we used the JASMIN platform, the decisions we took
and why, and advice for others running similar events.
</div>

## Overview
{:.no_toc}

In this guide we'll cover:

* Table of contents
{:toc}

## Common usage of JASMIN

As a service providing support to NERC and the environmental science community,
including access to the CEDA archive, JASMIN is typically used in one of two
ways:

1. Interactive compute e.g. running scripts from command line using the
   scientific analysis servers – they come with a lot of software and packages
   pre-installed, have read access to the CEDA archive and read/write to group
   workspaces and personal home directories
2. Batch compute using the LOTUS job system – there are both CPU and GPU nodes
   available and are best suited to group workspaces where processing of 100s of
   TBs of data is required Getting access to JASMIN if you are not an existing
   account holder is traditionally a process that takes some time, involving
   getting approval for your account, setting up two-factor authentication, SSH
   public key authentication etc. These can be a barrier to some users,
   especially with a short timescale.

## Accelerating access for event users

### JASMIN Notebook Service

We decided to use [JASMIN Notebook Service](https://notebooks.jasmin.ac.uk/), a
relatively new service called which allows Python 3 to be run through the
browser. When a user logs into the JASMIN Notebook Service, a new notebook server (a
customised JupyterLab) is started specifically for them.

At time of writing, the JASMIN Notebook Service runs on a Kubernetes cluster
with:

* Three nodes
* 72 CPUs
* 1.1 TB RAM

Using the JASMIN Notebook Service has the following advantages:

* Notebooks are best suited to basic data manipulation, data visualisation,
  storytelling and writing up results with code and outputs inline – these are
  exactly the kinds of activities that we envisage to make up most of the
  hackathon
* Users **do not need to log in via SSH** and can use their JASMIN username and
  password to log in plus email two-factor authentication
* Users **do not need to log in from an academic network**
* Users who are not familiar with the command line will likely be more
  comfortable using JupyterLab
* Graphical outputs can be viewed immediately via the user's web browser and
  they don't need to either download images or set up a graphical session in
  advance

However, you should also consider the following:

* Each user's notebook server is guaranteed 1 CPU and 4 GB RAM, although can
  use up to 4 CPUs and 16 GB RAM if the resources are available in the cluster.
  There are no specific limits on the number of concurrent users (we will be
  working with up to about 100), however if there are no resources available in
  the cluster then the user’s notebook server will fail to start
* Only **Python 3** can be used on the JASMIN Notebook Service, and not other
  languages such as R. Currently, versions of Python packages on the Notebook
  Service may also differ slightly from the rest of the JASMIN infrastructure,
  however different packages can be fairly easily installed using conda
* The Notebook Service provides read-write access to user home directories, 
  however **read-only access to Group Workspaces** (if users want to write data
  to a Group Workspace then either they will need to do this via SSH, or the
  hackathon organisers should talk to JASMIN staff about other potential
  workarounds)
* JupyterLab plugins (e.g. Git) and JupyterLab terminal access are not
  available. Commands *can* be run via the notebook *magic* syntax, but users
  will not be able to interact with programs (e.g. type in passwords). This
  means that **for pushing to GitHub, users will likely need to log in via SSH**
* There is no Dask back-end for parallel tasks, because long running or parallel
  jobs are intended to be run through the LOTUS job system

### Training accounts

We also opted to offer every participant a “training account” on JASMIN,
although those with existing accounts can use them instead. This is a simpler
and faster way for new users to get onto JASMIN for the event, because:

* Training accounts are assigned to a user for the length of the hackathon and
  then switched off afterwards, or if users have JASMIN accounts then they can
  apply to have the Notebook Service added to their account
* Users are sent credentials via email for the Notebook Service and (optionally)
  can download an SSH key pair if they want to have SSH access
* Each user gets read access to the public parts of the CEDA archive (inc.
  CMIP6) and read/write to 100 GB of home directory and (optionally) a few TBs
  of shared Group Workspace

However, remember that:

* At the end of the hackathon, users will need to have copied the code that they
  need off the training account, or committed it to Git (preferred), because it
  will later be removed[^1]
* For promising projects, users could be issued with proper JASMIN accounts
  created at the end of the hackathon, to allow them to continue working

#### Notes

[^1]: It is anticipated the code will be the most important thing, as the data
      can be regenerated. There is also the option of making all the code and
      data public for a period of time (e.g. a month) in case users need longer
      to download their code/data.
