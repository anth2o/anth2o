---
title: "Jimmy - Software engineer"
type: page
---

![Jimmy logo](https://cdn.prod.website-files.com/63497bb96fe7a9a8fa88990d/6352bfaf482c556de506e26e_Jimmy-logo.svg?h=20)


I worked as a Software Engineer in the pyjimmy team.

pyjimmy is an internal python library that is used by almost all the employees at Jimmy. The idea behind this library is to use Python and Git to store, connect, and use technical data about our nuclear reactor.



The main motivations behind this strong choice is to have a **single source of truth** for all the technical data.

## Summary of Work

During my time at Jimmy, I contributed to several key areas:

- **[Document Generation System](#writing-document-as-python-files)** - Developed methods to write documents as Python files with automatic updates and PDF compilation
- **[Technical Data Visualization](#visualization-of-the-technical-data-with-a-web-app)** - Built a full-stack web application for visualizing technical data stored as Python code
- **[GitHub Actions Integration](#implementation-of-github-actions-workflows-to-study-the-impact-of-any-modifications)** - Implemented workflows to track and report the impact of parameter changes across documents and simulations
- **[Team Support](#support)** - Provided guidance to non-engineering colleagues on using the library, Git, and Python

# Projects

The main features I developed, documented and maintained in pyjimmy were:

## Writing document as python files

The idea of this feature of pyjimmy is to be able to write documents as python files. The huge advantage of writing documents as python files instead of Word or markdown is to be able to import any data as a python variable and to display it in the document. 

Let's take an example:

```python
# document.py
from project_data import engine_dimensions
from internal_library import write

write(f"The engine is {engine_dimensions.length} long and {engine_dimensions.width} wide".)
```

This very basic document has a strong advantage compared to a static document: if the engine dimensions are modified by anyone because the design evolved, this document is automatically up to date so that there is no need for manual modifications.

To make this feature usable by everyone at Jimmy, I developed python methods with a CLI to launch:

- the visualization of this document in a web browser with auto reload
- the compilation of this document to a PDF with a predefined latex template

## Visualization of the technical data with a web app

There is a lot of technical structured data stored in our repository. Writing it as python code and versioning it with Git is very efficient, but it can be very cumbersome to visualize it.

To tackle this issue, I developed a web app to visualize the technical data stored as python code.

On this feature I worked on every aspect:

- the backend using FastAPI
- the frontend using React / TypeScript
- the containerization using Docker
- the deployment using Github Actions and AWS App Runner

## Implementation of GitHub Actions workflows to study the impact of any modifications

Having a single source of truth is very useful: if you change the value of a parameter, all the simulations and documents based on this parameter will be automatically updated.

Nonetheless, it can be very difficult to estimate the impact of the modification of a parameter. 

To visualize the impact of such modification on all our simulations and documents, I implemented Github Actions workflows that displayed a report with all the modifications to all our documents and simulations.

Using once again the example of `document.py` in [this section](#writing-document-as-python-files), if someone changes the value of `engine_dimensions.width` in a Pull Request, they will see a report on the PR comments:

- alerting them that the document `document.py` has been modified
- with a link to a detailed report of all the modifications to the documents

## Support

Another aspect of my role was also to help my colleagues that were not software engineers to use the library we were developing, and also more generally using git and python.