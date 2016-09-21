spike-git-github
================

A simple spike activity for getting started with git and GitHub.

## A Simple Git and GitHub Spike designed for K CS classes  (Draft -- Under construction!!!) #

Make sure everyone has a GitHub account.  (Does one need an account just to download?  Probably not. Probably just need one if planning to fork or create new repositories on GitHub.)

Download git and go through setup instructions.  (See, for example, <http://git-scm.com/book/en/Getting-Started-First-Time-Git-Setup>.)

Have someone (preferably not a git/github guru) work on a projected computer.

What is the best way for people to collaborate together?  Have everyone fork?  Have 2 or 3 out of 5 fork and the others contribute to others' forks?  (Do forking via GitHub web page.)

In a Terminal window (or your OS-equivalent):
 - Make a directory where you want to play with this spike under your personal web space
   (e.g., `~/Sites` in my case); `cd` there.
 - `git clone git://github.com/AlyceBrady/spike-git-github.git`  (or whatever)
     OR `git clone git://github.com/AlyceBrady/spike-git-github.git spike` (new name)
 - If you do a `git status` you should see nothing interesting.
 - View page & click Run Test.
 - Edit `git_github_spike.html` and just do STEP 1 (add your name to expected results).
 - View page & click Run Test.
 - Pretend you're thinking of committing it at this point.
  - Do a `git status`.  The file is modified but not staged to be part of next commit.
	- Add it to the "staging area":  `git add git_github_spike.html`
 - Horrors!  Just realized that that is NOT the full modification!
 - Edit the file again and do STEP 2.  View page & click Run Test.
 - Do another `git status`.  STEP 1 version is staged, but STEP 2 version is not.
 - Do another `git add` to stage current version.
 - Do another `git status`.
 - If everything has been staged correctly, you are ready to commit:
	`git commit -m "Add my name to class members list in spike"`
   (Note: for more involved changes, just say `git commit` which will put you in an editor to write the commit message.)

What's the right process to contribute it back?  Does it matter whether you own the fork or not?  Push if a contributor and request a pull if not?

Follow-up activities:
 - Merge all the changes made by members of the class.
 - Move the JavaScript code to a new file, `xxx.js`.  How does the new file get added?
 - Put an existing project into git on your own computer (can use git for local source code control without needing to push it to a remote server).

Additional (better) resources:
  - <http://sixrevisions.com/resources/git-tutorials-beginners/>
  - <http://gitready.com/>
  - <http://git-scm.com/book/en/Getting-Started-First-Time-Git-Setup>
  - <https://github.com/rapid7/metasploit-framework/wiki/Git-cheatsheet>
