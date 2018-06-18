# InstallFest

![GA Logo B&W](https://avatars.git.generalassemb.ly/u/5700?s=400&u=c547245df786bf7c05713279d31e7671c9f7374b)

The following walks through the installation of the software necessary for General Assembly's NYC Web Development Immersive Program (as of 2018-06-18).

## Homebrew

[Homebrew](https://brew.sh/) is an extremely popular and easy to use package manager for macOS. This is the tool we will use to install all of the software we need for this course.

Install homebrew from the command line with the command:

```shell
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

This install script will tell you the files it will create and ask for your password.

After the install, brew will print an output describing where to find more information on how to use it.

Open a new terminal window to begin using your newly installed tools.

### Bash Git Prompt

After running the Homebrew install, we want to configure our bash prompt to display helpful Git information.

From the command line, open your `~/.bash_profile` file with VS Code using the command:

```shell
code ~/.bash_profile
```

Paste the following into `~/.bash_profile`:

```shell
if [ -f "$(brew --prefix)/opt/bash-git-prompt/share/gitprompt.sh" ]; then
  __GIT_PROMPT_DIR=$(brew --prefix)/opt/bash-git-prompt/share
  source "$(brew --prefix)/opt/bash-git-prompt/share/gitprompt.sh"
fi
```

Save the file and quit VS Code.

### Brew Reference

- [Brew Docs](https://docs.brew.sh/)
- [Brew Cask](https://caskroom.github.io/)
- [Bash Git Prompt Install](https://github.com/magicmonty/bash-git-prompt#via-homebrew-on-mac-os-x)
- [Bonus: Brew Fonts](https://github.com/Homebrew/homebrew-cask-fonts)

## Configure Git

We want to set a default name an email address that Git will use to identify our commits. We want to be sure to use the same email as the one we created our GitHub (and GitHub Enterprise) account with.

```shell
git config --global user.name "YOUR NAME HERE"
git config --global user.email YOUR_EMAIL@DOMAIN.COM
```

We will also tell Git to use VS Code as our default editor:

```shell
git config --global core.editor "code --wait"
```

### Git Config Reference

- [Git First Time Set Up](https://git-scm.com/book/en/v2/Getting-Started-First-Time-Git-Setup)
- [GitHub Setting username](https://help.github.com/articles/setting-your-username-in-git/#setting-your-git-username-for-every-repository-on-your-computer)
- [GitHub Setting email](https://help.github.com/articles/setting-your-commit-email-address-in-git/)
- [GitHub about commit email](https://help.github.com/articles/setting-your-commit-email-address-in-git/)
- [VS Code as Git Editor](https://code.visualstudio.com/docs/editor/versioncontrol#_vs-code-as-git-editor)

## Postgres

Try running the PostgreSQL command line client:

```shell
psql
```

You may get an error `psql: FATAL:  database "YOUR-USER-NAME" does not exist`.

To fix this run:

```shell
createdb jsm
```

### Postgres Reference

- [Postgres Troubleshooting](https://postgresapp.com/documentation/troubleshooting.html#errors-when-connecting-to-the-postgresql-server)
