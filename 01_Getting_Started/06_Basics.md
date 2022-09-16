  - <a href="#git_diff">`git diff`</a>
<h2 id="git_diff">Viewing Your Staged and Unstaged Changes</h2>

If the **`git status`** command is too vague for you — you want to know exactly what you changed, not just which files were changed — you can use the **`git diff`** command., you’ll probably use it most often to answer these two questions: 
1. What have you changed but not yet staged? 
2. what have you staged that you are about to commit(snapshot)? 

Although **`git status`** answers those questions very generally by listing the file names, **`git diff`** shows you the exact lines added and removed — the patch, as it were.

Let’s say you edit and stage the **`README.md`** file again and then edit the **`CONTRIBUTING.md`** file without staging it. If you run your **`git status`** command, you once again see something like this:
```bash
$ git status
On branch master
Your branch is up-to-date with 'origin/master'.
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

    modified:   README.md
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)
    modified:   CONTRIBUTING.md
To see what you’ve changed but not yet staged, type **`git diff`** with no other arguments:
```bash
$ git diff
diff --git a/CONTRIBUTING.md b/CONTRIBUTING.md
index 8ebb991..643e24f 100644
--- a/CONTRIBUTING.md
+++ b/CONTRIBUTING.md
@@ -65,7 +65,8 @@ branch directly, things can get messy.
 Please include a nice description of your changes when you submit your PR;
 if we have to read the whole diff to figure out why you're contributing
 in the first place, you're less likely to get feedback and have your change
-merged in.
+merged in. Also, split your changes into comprehensive chunks if your patch is
+longer than a dozen lines.
```
That command compares what is in your **working directory** with what is in your **staging area**. The result tells you the changes you’ve made that you haven’t yet staged.
If you want to see what you’ve **staged** that will go into your next **commit**, you can use **`git diff --staged`** or **`git diff --cached`**(**`--staged`** and **`--cached`** are synonyms). This command compares your **staged** changes to your **last commit**:
```bash
$ git diff --staged
diff --git a/README.md b/README.md
new file mode 100644
index 0000000..03902a1
--- /dev/null
+++ b/README
@@ -0,0 +1 @@
+My Project
```
It’s important to note that **`git diff`** by itself doesn’t show all changes made since your last commit — only changes that are still unstaged. If you’ve staged all of your changes, **`git diff`** will give you no output.

**Note**
**Git Diff in an External Tool**
We will continue to use the **`git diff`** command in various ways throughout the rest of the book. There is another way to look at these diffs if you prefer a graphical or external diff viewing program instead. If you run **`git difftool`** instead of **`git diff`**, you can view any of these diffs in software like emerge, vimdiff and many more (including commercial products). 
<h3 id="VSCode_difftool">VScode as difftool</h3>

Run the command **`git config --global --edit`** to edit the global config, and add the following:
```bash


If you already have **`[core]`** section, just add the **`[diff]`** and **`[difftool]`** sections to it.