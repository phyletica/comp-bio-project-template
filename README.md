# Comp Bio project template

This repository is a starting point for your own computational biology
project.
It sets you up with a ***codespace***: A Linux computer in the cloud that you
use through your web browser.
Your codespace comes with:

-   [git](https://git-scm.com/), for keeping track of changes to your files
    (version control), and
-   [pixi](https://pixi.prefix.dev/latest/), for installing Python, marimo,
    and other software into a project environment that anyone can recreate
    exactly.

You don't need to install anything on your own computer.

## Make your own copy of this repository

You will work in ***your own copy*** of this repository, not this one.

1.  Make sure you are signed in to GitHub.
2.  Near the top of this page, click the green **"Use this template"** button
    and choose **"Create a new repository."**
3.  Under **"Owner,"** choose your GitHub username.
4.  For **"Repository name,"** type `comp-bio-project`.
5.  Click **"Create repository."**

GitHub will take you to your new repository.
Check that the name at the top of the page is `your-username/comp-bio-project`.
***Bookmark this page***; this is where you will come back to work on your
project.

## Open your codespace

1.  On ***your*** repository's page, click the green **"Code"** button.
2.  Click the **"Codespaces"** tab, and then click
    **"Create codespace on main."**

A new browser tab will open with an editor called VS Code.
The first time, it takes a couple of minutes to set everything up.
When it's ready, you will see your files on the left and a ***terminal*** at
the bottom of the window.
The terminal is where you will type commands.

To check that everything is installed, type each of these commands in the
terminal and press Enter:

```bash
git --version
pixi --version
```

Each one should print a version number.

> [!TIP]
> Next time, you don't need to create a new codespace.
> Go to your repository, click **"Code"** → **"Codespaces,"** and click the
> name of the codespace you already have.
> Everything will be just as you left it.

## Set up your project environment (first time only)

In the terminal, run:

```bash
pixi init
pixi add "python=3.14.*" marimo
```

The first command creates a file named `pixi.toml`, which lists the software
your project needs.
The second command adds Python and marimo to that list and installs them.
The `"python=3.14.*"` part asks for Python version 3.14 (any 3.14.x
release), rather than whatever version is newest on the day you run the
command.
It also creates a file named `pixi.lock`, which records the ***exact***
version of every package that was installed, so the same environment can be
recreated later on any computer.

## Start marimo

In the terminal, run:

```bash
pixi run marimo edit --headless --port 2718 --no-token
```

After a few seconds, marimo will open in a new browser tab.
If it doesn't (your browser may have blocked the pop-up):

1.  Click the **"Ports"** tab next to **"Terminal"** at the bottom of VS Code.
2.  Find the row labeled **"marimo"** and click the globe icon
    (**"Open in Browser"**).

When you are done with marimo, go back to the terminal and press
**Ctrl + C** to stop it.

> [!NOTE]
> The `--no-token` option turns off marimo's password.
> That's OK here, because only you can open your codespace's marimo page;
> GitHub makes you sign in first.

## Save your work to GitHub

Your codespace is ***temporary***.
GitHub deletes codespaces that haven't been used for 30 days, ***even if they
contain work you haven't saved to GitHub***.
Your work is only safe once you have ***committed*** it with git and
***pushed*** it to your repository on GitHub.

To save a snapshot of your work and send it to GitHub:

```bash
git status
git add pixi.toml pixi.lock .gitignore .gitattributes
git commit -m "Describe what you changed"
git push
```

`git status` lists the files that are new or have changed.
In the `git add` line, list the files you want to save (the ones above are
the files `pixi init` and `pixi add` created), and in the `git commit` line,
write a short message that describes what you changed.
You don't need to sign in to push; your codespace is already allowed to push
to your repository.

## Stop your codespace when you're done

Codespaces use up your free monthly hours while they are running.
A codespace stops on its own after 30 minutes of inactivity, but it's best to
stop it yourself when you're done:

-   In VS Code, press **F1**, type `stop current codespace`, and press Enter.
-   Or go to <https://github.com/codespaces>, click the **"..."** next to your
    codespace, and choose **"Stop codespace."**

Stopping a codespace does ***not*** delete your files.

## Quick reference

| Command | What it does |
|---|---|
| `git status` | Show which files have changed since your last commit |
| `git add <file>` | Choose a file to include in your next commit |
| `git commit -m "message"` | Save a snapshot of the chosen files, with a message |
| `git log --oneline` | List your commits, newest first |
| `git diff` | Show exactly what changed since your last commit |
| `git push` | Send your commits to GitHub |
| `pixi add <package>` | Add a package to your project environment |
| `pixi install` | Recreate the environment from `pixi.toml` and `pixi.lock` |
| `pixi list` | List the packages in your environment |
| `pixi run <command>` | Run a command inside your project environment |

## Working on your own computer instead

Everything above also works on your own computer.
Once git and pixi are installed, the commands are the same.
See the
[instructions for running marimo on your own computer](https://phyletica.org/intro-to-comp-bio/marimo-local.html)
on the class website.

## What's in this repository

-   `README.md`: This file.
-   `.devcontainer/devcontainer.json`: Tells GitHub how to set up your
    codespace (which operating system to use and what to install).
-   LICENSE: Text file of the CC0 license.

# License

This work is marked <a href="https://creativecommons.org/publicdomain/zero/1.0/">CC0 1.0</a><img src="https://mirrors.creativecommons.org/presskit/icons/cc.svg" alt="" style="max-width: 1em;max-height:1em;margin-left: .2em;"><img src="https://mirrors.creativecommons.org/presskit/icons/zero.svg" alt="" style="max-width: 1em;max-height:1em;margin-left: .2em;">
