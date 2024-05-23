---
number: 4
title: Provider Parameter Mapper Utilities
pis:
  - joe-smithe-glos
contributors:
  - 7yl4r
  - cjolson64
  - Dylan-Pugh
  - MathewBiddle
github: ioos/ioos-code-sprint/issues/33
slack:
  - metadata
breakout:
  - Metadata
year: 
  - 2024
---

**Expected Outcomes:**

A library - GitHub MVP or if there's enough energy, an NPM package - that assists a data provider with mapping the names of the parameters they provide to a standard term in one of the various vocabularies that IOOS implements.

Interfaces to the library may be developed to serve different purposes. For example, originally this project was proposed under the assumption that we'd be talking ocean buoy/coastal platform parameters, but a different form could address biological data parameters, i.e. Darwin Core.

Generally, the goals here are:

- A user fillable form that allows platform/buoy data providers to submit what parameters their platform is going to send in, and the CF standard names those parameters map to + a form to map biological parameters to Darwin Core compatible terms

- When a provider is searching for an appropriate standard name, the standard name's definition pops up someplace to inform the provider what they're looking at. Suggestions may also pop up as well.


**Skills required:**

JavaScript, knows their way around the CF vocabulary: https://cfconventions.org/

Perhaps some Python or R to generate reference files

**Difficulty:**

Hopefully just drudgery towards a useful set of tools.

**Relevant links:**

- https://github.com/ioos/ioos-code-sprint/issues/33
- https://github.com/ioos/ioos-code-sprint/issues/31

**Functioning Prototypes**

- https://github.com/7yl4r/react_component
- https://github.com/joe-smithe-glos/seagull.platform.form.ics2024

**Workflow**

- Started with working on assimilating a standardized JSON parameter vocabulary
  - https://github.com/7yl4r/react_component/tree/main/src/vocabulary_json
- A javascript storybook 'CfParameterField' became the minimum viable product
  - Run this repo: https://github.com/7yl4r/react_component
- Per the topic lead, a metadata form with the parameter mapper integrated was drafted
  - https://github.com/joe-smithe-glos/seagull.platform.form.ics2024
