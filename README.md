# PySheets

PySheets is a spreadsheet UI for Python, implemented in Python, running in the browser, using PyScript.
  
# Instructions for PySheets Users



# Instructions for PySheets Developers 

## Setup in VS Code

First install VS Code, Python3, and the Python extension for VS Code.
Follow [this tutorial](https://code.visualstudio.com/docs/python/python-tutorial) for that. As part of the instructions, you will install a Python v3 runtime.

## Setup Venv

To set up local virtual environment for PySheets, open a terminal and run:

```
mkdir pysheets
cd pysheets
python3 -m pip install virtualenv
python3 -m venv env
source env/bin/activate
```

You now have a `pysheets` folder containing a `venv` folder to store all
the Python dependencies and runtimes that PySheets needs.


## Source folders and their meaning

Folders:

 - `static/`: Contains all the UI resources. 
 - `tests/`: Unit tests. See `build.sh` that runs them.
 - `templates/`: Used to hold Jinja templates, used by `main.py`. Contains `index.html`.

Files:
 - `main.py`: Webserver for serving all the static content.

Configuration files:
 - `firestore.json`: Firestore key.
 - `openai.json`: OpenAI key.
 - `package.json`, `package-lock.json`: Node.js packages (not used).
 
All of the PySheet UI is written in Python, with some JS. CSS is used for styling.
# Setup PySheets

PySheets is stored in github. To make a local copy, run:

```
git clone https://github.com/ascend-software-company/pysheets-prod.git
git clone https://github.com/ascend-software-company/pysheets-src.git
cd pysheets-src
pip install -r requirements.txt
cd ../..
ls
```

You should now have the following folder structure:
  - `pysheets`
    - `env`
    - `pysheets-prod`
    - `pysheets-src`

# Accessing PySheets from VS Code

To navigate to the source of PySheets, and make changes to it:
  - Launch VS Code
  - Open the `pysheets/pysheets-src` folder
  - Open a terminal inside VS Code

# Running PySheets during development

To run PySheet locally from VS Code, it its terminal run:

```
source ../env/bin/activate; python3 main.py
```

Then open [the local preview](http://127.0.0.1:8081/). Note that in VS Code, you can `Cmd+Click` any URL or file name that is printed in the terminal to open it.

Note that this will use local Python source files and CSS, but all data still comes from production.

# Making changes and committing them

First add PR request support to VS Code:
 - Install the VS Code extension: [Github Pull Requests Extension](https://marketplace.visualstudio.com/items?itemName=GitHub.vscode-pull-request-github)

From now on, do all your work in a new branch:
 - Create a new branch using the "..." menu in the "Source Control" viewlet. Use a short name that is meaningful to the task.
 - Commit your changes (to the new branch).
 - Publish/Synch your changes to the branch, so that others can see it.

Branches are the mechanism used by Git to allow people to work in parallel and merge their work later.

Once you work is ready for a review, create a new PR request:
 - Select the "Github Pull Requests" viewlet and click the "Create Pull Request" button in the hover bar.
 - Change the "MERGE" branch to the branch you did your work in.
 - Choose an assignee and reviewer(s) for the work in the hover bar.
 - Finish the PR description and send it.

Both the assignee and reviewer now see the changes in their Pull Request viewlet.