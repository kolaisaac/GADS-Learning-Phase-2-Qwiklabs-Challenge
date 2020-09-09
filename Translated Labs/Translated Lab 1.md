# Building a DevOps Pipeline

## Overview

In this lab, you will build a continuous integration pipeline using Cloud Source Repositories, Cloud Build, build triggers, and Container Registry.

![Cloud Build](/images/CloudBuildCI.png/)

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
2. Note the lab's access time (for example, ![Time Count](/images/TimeCount.png) and make sure you can finish in that time block.
```
There is no pause feature. You can restart if needed, but you have to start at the beginning.
```
3. When ready, click ![Start Lab](/images/StartLabClick.png).
4. Note your lab credentials. You will use them to sign in to Cloud Platform Console.
![Cloud Platform Console](/images/OpenConsole.png)

5. Click **Open Google Console**.

6. Click **Use another account** and copy/paste credentials for **this** lab into the prompts.

```
If you use other credentials, you'll get errors or incur charges.
```
7. Accept the terms and skip the recovery resource page.
```
Do not click End Lab unless you are finished with the lab or want to restart it.
This clears your work and removes the project.
```

## Task 1: Create a Git Repository

First, you will create a Git repository using the Cloud Source Repositories service in Google Cloud. This Git repository will be used to store your source code. Eventually, you will create a build trigger that starts a continuous integration pipeline when code is pushed to it.

1. From the ***google cloud shell***, call:

```
gcloud init
```
   - Type **2** to create a new configuration
   - Give the configuration a name
   - Type **1** to select your account
   - Type **6** to choose your project

2. Create a ***repos source*** with a REPO_NAME
```
gcloud source repos create [REPO_NAME]
```
Where [REPO_NAME] is the name for your repository, in my case it is ***devops-repo*** as shown below.

```
gcloud source repos create devops-repo
```
3. Enter the following command to create a folder called ***gcp-course***:

```
mkdir gcp-course
```
4. Change to the folder you just created:

```
cd gcp-course
```
5. Now clone the empty repository you just created:
```
gcloud source repos clone devops-repo
```
***You will see a warning that you have cloned an empty repository. That is expected at this point***.

6. The previous command created an empty folder called devops-repo. Change to that folder:
```
cd devops-repo
```

## Task 2: Create a Simple Python Application

You need some source code to manage. So, you will create a simple Python Flask web application. The application will be only slightly better than "hello world," but it will be good enough to test the pipeline you will build.

```
from flask import Flask, render_template, request

app = Flask(__name__)

@app.route("/")
def main():
    model = {"title": "Hello DevOps Fans."}
    return render_template('index.html', model=model)

if __name__ == "__main__":
    app.run(host='0.0.0.0', port=8080, debug=True, threaded=True)
```

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
