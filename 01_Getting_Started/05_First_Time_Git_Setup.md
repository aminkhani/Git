<h1 id="top">First Time Git Setup</h1>

Git comes with a tool called **git config** that lets you get and set configuration variables that control all aspects of how Git looks and operates. These variables can be stored in three different places:

- `/etc/gitconfig` file: Contains values for every user on the system and all their repositories. If you pass the option `--system` to `git config`, it reads and writes from this file specifically.
  - ```git config --system```
- `~/.gitconfig` or `~/.config/git/config` file: Specific to your user. You can make Git read and write to this file specifically by passing the `--global` option.
  - ```git config --global```
- `config` file in the Git directory (that is, `.git/config`) of whatever repository you’re currently using: Specific to that single repository.
  - ```git config --local```

Each level overrides values in the previous level, so values in .`git/config` trump those in `/etc/gitconfig`.

**Note:** The path to git config file for each level of configuration may be slightly different on your system. To check the path to the config file for global level for example, run `git config --global --edit` and check the opened file path. The same applies for the other levels.

<img src="./images/git-config.png" width="600" />

## Setting Your Username and Email
It’s important to set your user name and email address because every Git commit uses this information, and it’s immutably baked into the commits you start creating:

```bash
git config --global user.name "Your Name"
git config --global user.email email@email.com
```
![git_config](https://user-images.githubusercontent.com/51851950/190846397-c4d6f947-20ae-4aac-991e-ae9e48844eb6.gif)

You can also edit the config file manually using a text editor, such as vim, nano, or VSCode, by running:
```bash 
git config --system --edit
git config --global --edit
git config --local --edit
```
## Checking Your Settings
You can check your settings at any time by running the `git config --list` command:

```bash
$ git config --list
user.name=Amin Khani
user.email=aminkhani2010@gmail.com
```
![git-list](https://user-images.githubusercontent.com/51851950/190849876-d7ee6f59-88ff-4227-ac06-728654a2d5de.gif)

**Note:**
- Your output may include more settings than the ones shown here. The settings shown here are the only settings you need to set up to get started with Git.
- To see the config level of a specific setting, run `git config --list --show-origin`.

![git-show](https://user-images.githubusercontent.com/51851950/190850151-5977b552-7359-4989-b754-d9378821aa3e.gif)

## Setting Your Default Text Editor
If you want to use a text editor other than Vim/Nano or any other default editor you have on your system, you can set your default text editor with the `core.editor` variable. For example, to set the default text editor to VSCode, you can use:

```bash
git config --global core.editor "code --wait"
```
![git-code](https://user-images.githubusercontent.com/51851950/190846888-9ab70b18-f88b-4c7d-b5a1-e923b9b89af4.gif)

**Note:** The `--wait` or `-w` flag is crucial, without this, git won't know the editing has completed and in turn won't finish executing the git command.


## Getting Help
If you ever need help while using Git, there are three equivalent ways to get the comprehensive manual page (manpage) help for any of the Git commands:
```bash 
git help <verb>
git <verb> --help
man git-<verb>
```
For example, you can get the manpage help for the git config command by running this:
```bash 
git help config
```
![hh](https://user-images.githubusercontent.com/51851950/190850951-8a2e2b18-f57c-4bc9-a3e9-74ea132a59f8.gif)

In addition, if you don’t need the full-blown manpage help, but just need a quick refresher on the available options for a Git command, you can ask for the more concise ```help``` output with the ```-h``` option, as in:

![gitt](https://user-images.githubusercontent.com/51851950/190850619-2e8f8912-19c3-45c0-a1d0-df1a25811f94.gif)

<br>
<div align="right"><a href="04_VScode_Setup.md" targert="_blacnk"><img src="https://img.shields.io/badge/Previus-orange?style=for-the-badge&logoColor=white"/></a>
<a href="06_Basics.md" targert="_blacnk"><img src="https://img.shields.io/badge/Next-orange?style=for-the-badge&logoColor=white"/></a>
<a href="#top" targert="_blacnk"><img src="https://img.shields.io/badge/Back to up-orange?style=for-the-badge&logo=expo&logoColor=white" /></a>
</div>
