---
title: Environment setup scripts
date: 2021-06-21
authors:
 - "[James Thomas](https://github.com/jatonline/) ([Jean Golding Institute](https://www.bristol.ac.uk/golding/))"
layout: resource
---

<div class="lead" markdown="1">
# Help participants use the Group Workspace

Some scripts to help with using the hackathon's Group Workspace on JASMIN, and
a conda environment with pre-installed packages.

See also our [example notebook]({% link resources/create-environment.md %}).
</div>

## Table of contents
{:.no_toc}

* Table of contents
{:toc}

## File system structure

Our hackathon environment exists within two [Group Workspaces](https://help.jasmin.ac.uk/article/199-introduction-to-group-workspaces)
on JASMIN.

These are:

* `/gws/pw/j05/cop26_hackathons/bristol` for project file storage and setup
  scripts (uses a parallel-write filesystem)

  containing:

  * `activate-env` – a bash shell script that can be `source`'d to load Jaspy,
    add the hackathon python environment to the user's PATH, and provide a
    `$GWS` shell variable to helpt he user get quickly to the group workspace

  * `install-kernel` – a bash shell script that will install the hackathon's
    conda environment into the user's Jupyter kernels, so that they can use it
    easily on the JASMIN Notebook Service

  * `env/` – a symlink to the real conda environment location (see below)

  * `project01/`, `project02/`, `project03/` and so on – directories for each of
    the project groups

* `/gws/smf/j04/cop26_hackathons/bristol` for the conda python environment (uses
  a filesystem backed by solid state disks, and works well for many small files,
  which is exactly what we have in a conda environment)

  * `env/` – the actual location of the conda environment
    
    * `environment.yml`
    * `environment_frozen.yml`

      The YAML configuration files for the conda environment, containing
      unpinned and pinned dependency versions, respectively.


## activate-env bash script

<iframe class="template" src="{% link resources/environment/activate-env.txt %}"></iframe>
[Open in a new page]({% link resources/environment/activate-env.txt %})

## install-kernel bash script

<iframe class="template" src="{% link resources/environment/install-kernel.txt %}"></iframe>
[Open in a new page]({% link resources/environment/install-kernel.txt %})

## environment.yml unpinned dependencies

<iframe class="template" src="{% link resources/environment/environment.yml.txt %}"></iframe>
[Open in a new page]({% link resources/environment/environment.yml.txt %})

## environment_frozen.yml pinned dependencies

<iframe class="template" src="{% link resources/environment/environment_frozen.yml.txt %}"></iframe>
[Open in a new page]({% link resources/environment/environment_frozen.yml.txt %})
