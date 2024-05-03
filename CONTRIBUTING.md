# Contributors Guide

Interested in helping out the IOOS community?
Have a few minutes to tackle an issue? Or improve the documentation?
In this guide we will get you setup and integrated into contributing to IOOS Software and Docs!

## Introduction

First off, thank you for considering contributing to IOOS.

To get started, let's describe the different branches on this repository. 
Below is a table with the branch name and description to help you identify which branch to contribute to.

Branch | Description
-------|------------
`main` | Where the IOOS Code Sprint Coordination team will document the sprint topics.
`gh-pages` | Where the source materials are for generating the IOOS Code Sprint website. https://ioos.github.io/ioos-code-sprint/

The purpose of this repository is for planning and executing an IOOS Code Sprint event. 

So, please take a few minutes to read through this guide.

## Issues

* Issues are mainly used for proposing potential IOOS Code Sprint Topics.
* Please use the GitHub issue template [Code Sprint Project Proposal](https://github.com/ioos/ioos-code-sprint/issues/new?assignees=mathewbiddle%2Cmwengren&labels=code+sprint+topic&projects=&template=code-sprint-project-proposal.yml&title=%5BProject+Proposal%5D%3A+) to propose a topic.

## Ground Rules

The goal is to maintain a diverse community that's pleasant for everyone. Please
be considerate and respectful of others by following our
[code of conduct](https://github.com/ioos/.github/blob/main/CODE_OF_CONDUCT.md).

## Process for selecting a Code Sprint Topic

1. Propose the topic using the [Code Sprint Project Proposal Template](https://github.com/ioos/ioos-code-sprint/issues/new?assignees=mathewbiddle%2Cmwengren&labels=code+sprint+topic&projects=&template=code-sprint-project-proposal.yml&title=%5BProject+Proposal%5D%3A+).
1. Discuss and refine the topic with community members in the GitHub issue.
1. Determine how many potential participants would like to contribute during the Code Sprint. (_for 2024 we did this via Google Forms_)
1. Determine who will lead the topic during the sprint by assigning a person as `assignee` in the GitHub issue.
   1. A Code Sprint coordinator will update the ticket identifying a potential topic lead by setting them as `assignee`.
1. The issue `assignee` will [create a Sprint Topic webpage](#creating-sprint-topic-webpages).

## Creating Sprint Topic Webpages

1. Fork the `gh-pages` branch of this repository and start a new branch for your contributions.
1. Make a copy of https://github.com/ioos/ioos-code-sprint/blob/gh-pages/_topics/2024-05-01-01-test_something.md?plain=1 to a new markdown file in the `_topics/` directory.
   1. The filename convention is as follows: 
       2024-05-01-`<incrementor>`-`<title>`.md
1. Adjust the filename to increase the `<incrementor>` by 1 and adjust the `<title>` text to something descriptive about the topic (For example, `2024-05-01-01-test_something.md` -> `2024-05-01-02-ERDDAP_mobile_application.md`).
   1. Note, keep the date consistent with the dates for the event (For example, the 2024 event will use the date `2024-05-01`) as this is used to build the pages.
1. In the markdown topic page, adjust the header content, indicating the incrementor in the filename (`number`), topic title (`title`), who will lead the topic (`pis`), the participants (`contributors`), and the GitHub issue (`github`). 
The coordinators will update the remaining fields in the header.
    ```
    ---
    number: <incrementor>
    title: <title>
    pis:
      - <pis>
    contributors:
      - <contributors>
    github: <github>
    slack:
      - python
    breakout:
      - General Python
    year: 
      - 2024
    ---
    ``` 
1. Update the various sections of the webpage from the information in the GitHub issue. The formatting follows [markdown formatting](https://www.markdownguide.org/cheat-sheet/).
1. Submit your sprint topic page addition as a [Pull Request](#pull-requests) to the `gh-pages` branch.

## Pull Requests

### Website
The changes to the code source (and documentation)
should be made via GitHub pull requests against ``gh-pages``,
even for those with administration rights.
While it's tempting to make changes directly to ``gh-pages`` and push them up,
it is better to make a pull request so that others can give feedback.
If nothing else,
this gives a chance for the automated tests to run on the PR.
This can eliminate "brown paper bag" moments with buggy commits on the main branch.


**Working on your first Pull Request?** You can learn how from this *free* video series
[How to Contribute to an Open Source Project on GitHub](https://egghead.io/courses/how-to-contribute-to-an-open-source-project-on-github),
Aaron Meurer's [tutorial on the git workflow](https://www.asmeurer.com/git-workflow/), or the
guide [“How to Contribute to Open Source"](https://opensource.guide/how-to-contribute/).

Commit the changes you made. Chris Beams has written a [guide](https://cbea.ms/git-commit/)
on how to write good commit messages.

Push to your fork and submit a pull request.

## What happens after the pull request

You've made your changes, documented them, added some tests, and submitted a pull request.
What now?

## Further Reading

There are a ton of great resources out there on contributing to open source and on the
importance of writing tested and maintainable software.

* [How to Contribute to Open Source Guide](https://opensource.guide/how-to-contribute/)
* [Zen of Scientific Software Maintenance](https://jrleeman.github.io/ScientificSoftwareMaintenance/)
