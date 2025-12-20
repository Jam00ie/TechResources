<h1> Getting Started with Python</h1>

<h2> Install Python (version 3.9 - 3.11)</h2>

* Currently, Mediapipe is only supported on python versions 3.9 to 3.12.
* You can download a compatible version of python [here](https://www.python.org/downloads/).

<h2> Creating Virtual Environments</h2>

A Python virtual environment (venv) is a self-contained directory that allows you to install packages and dependencies for a specific project without affecting the global Python installation or other projects.

1. Open a terminal in VS Code and use `cd [directory]` to navigate to the directory where you want to store your project files.
2. Create a venv:
    - Enter `python -m venv [name-of-your-venv]` in the same terminal. 
    This should create a new folder with the name of your venv under your directory
3. Activate the venv:
    - You might get a prompt in VSCode after creating the venv, asking if you want to use the new venv for your project. If you select yes, you don't need to do the following.
    - For Mac/Linux users: `source ./name-of-your-venv/bin/activate `
    - For Windows users: `name-of-your-venv/Scripts/activate`
    - When prompted, type R and then enter to run once
    - You should now see `(name-of-your-venv)` being appended to your input prompt, indicating that you have activated your venv
