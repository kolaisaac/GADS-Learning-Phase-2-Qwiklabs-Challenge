# Building a DevOps Pipeline

## Overview

In this lab, you will build a continuous integration pipeline using Cloud Source Repositories, Cloud Build, build triggers, and Container Registry.
![Cloud Build](images/CloudBuildCI.png)

## Objectives

In this lab, you will learn how to perform the following tasks:
- Create a Git repository
- Create a simple Python application
- Test Your web application in Cloud Shell
- Define a Docker build
- Manage Docker images with Cloud Build and Container Registry
- Automate builds with triggers
- Test your build changes

## Set up your lab environment

For each lab, you get a new GCP project and set of resources for a fixed time at no cost.

1. Make sure you signed into Qwiklabs using an incognito window.
2. Note the lab's access time (for example, images/TimeCount.png and make sure you can finish in that time block.
```bash
There is no pause feature. You can restart if needed, but you have to start at the beginning.
```
3. When ready, click images/StartLabClick.png.
4. Note your lab credentials. You will use them to sign in to Cloud Platform Console.
![Cloud Platform Console](images/OpenConsole.png)

## Installation

Use the package manager [pip](https://pip.pypa.io/en/stable/) to install foobar.

```bash
pip install foobar
```

## Usage

```python
import foobar

foobar.pluralize('word') # returns 'words'
foobar.pluralize('goose') # returns 'geese'
foobar.singularize('phenomena') # returns 'phenomenon'
```

##  This Lab solution is  &copy; 2020