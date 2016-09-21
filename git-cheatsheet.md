## Getting Help #

Three alternatives to getting the manual page (manpage) for any Git command:

    $ git help <verb>  
    $ git <verb> --help  
    $ man git-<verb>  

## Updating Git: #

If you already have Git installed, you can get the latest development
version via Git itself:

    git clone https://github.com/git/git.git

## Creating a repository: #

For an existing project, go to the project's directory:

    git init  [then do add's and commit]
    
For an existing repository:

    git clone git://github.com/schacon/grit.git  [or whatever]  

OR  

    git clone git://github.com/schacon/grit.git mygrit [new name]  

If not a collaborator for the original repository, fork it first:
-   Use Fork button on GitHub web page. [now have own copy on GitHub]  
-    `git clone git://github.com/myUserName/ramp.git` [or whatever]

## Renaming files:  Do this using Git, not the UNIX `mv` command! #

To rename or move a file:

    git mv filename newFilename
    
If the file has been moved outside of Git, just do a `git rm` and
`git add`; Git figures out this is a rename (according to SCM):

    git rm README.txt
    git add README

## Recording changes: #

To see what is new, modified, untracked, etc:

    git status
    
To stage files (new or modified) for commit:

    git add <file>
    
To see what has been staged:

    git diff --staged
    
To see what has been changed BUT NOT STAGED:

    git diff
    
To commit:

    git commit [will put in editor for commit message]  

OR  

    git commit -m  "Story 182: Fix benchmarks for speed"
    
  (See
  <http://tbaggery.com/2008/04/19/a-note-about-git-commit-messages.html>
  for best practices on commit messages.  See below for executive summary.)
  [CHECK: Probably should NOT remove the comments that Git
  inserts, since it helps Git track what happened in each commit???]

If all files to include in a commit are being tracked (i.e., there
are files that have been "Changed but not updated" but no files that
are untracked), then can wrap the add phase for modified files into
the commit:

    git commit -a -m 'Modify a few files"
    
To "fix" a commit:
-   Make additional changes that should have been made before commit  
-   `git commit --amend` [now have single, changed commit]

(See git-scm book for additional Recording Changes topics, like
skipping the staging area, removing files, and moving/renaming
files and additional Undoing Things topics, like unstaging and
unmodifying files.)

__Executive summary of Tim Pope's (tbaggery) recommendations:__  
>>   Short (<=50 char, preferably) capitalized summary on 1st line followed
>>   by blank line; use present tense imperative in summary ('Fix bug' not
>>   'Fixed bug'); wrap lines at around 72 chars.

## Forking -- Creating your own version of someone else's project: #

If a GitHub project, use Fork button on GitHub web page.

## Creating a branch: #

To create the branch and switch to it:

    git branch myBranch
    git checkout myBranch  [or git checkout -b myBranch to do both]

To clear the staging area to switch to another branch; then get stashed stuff back:

    git stash
    git stash apply   [to get stashed stuff back]

To switch back and forth between myBranch and the master:

    git checkout master
    git checkout myBranch

To merge the branch into the master (and then delete the branch):

    git checkout master
    git merge myBranch
    git branch -d myBranch

## Dealing with merge conflicts: #

Git reports "CONFLICT (content): ...  Automatic merge failed; ..."
and `git status` shows what files need to be merged.  The conflicts
are marked in the files themselves with diff-like comparisons.  Edit
the files to resolve the conflicts in whatever is the best way,
removing the diff-like meta-information ("<<<" etc.) at the same
time.  Finish by doing a `git add` for each resolved file.

## Being the admin: #

- Need lots of stuff here to do with `pull`, `push`, `fetch`, etc.
   (including pushing with a tag).
- To create an annotated tag (e.g., for a new version):  
    `git tag -a v1.4 -m 'my version 1.4'` [or leave out the `-m` and Git will launch the editor]
- To create a signed annotated tag (need a private key):  
    `git tag -s v1.5 -m 'my signed 1.5 tag'`

## When ready #

Check out useful Tips and Tricks (bash completion, aliases):
-  <http://git-scm.com/book/en/Git-Basics-Tips-and-Trick>

## Sources: #

-  <http://git-scm.com/book/en/Getting-Started-First-Time-Git-Setup>
-  <http://git-scm.com/book/en/Git-Basics-Getting-a-Git-Repository>
-  <http://git-scm.com/book/en/Git-Basics-Recording-Changes-to-the-Repository>
-  <http://tbaggery.com/2008/04/19/a-note-about-git-commit-messages.html>
-  <https://help.github.com/articles/fork-a-repo>
-  <http://git-scm.com/book/en/Git-Branching-What-a-Branch-Is>
-  <https://github.com/rapid7/metasploit-framework/wiki/Git-cheatsheet> (for git stash)
