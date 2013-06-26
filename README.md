---
layout: post
title:  "Git Info"
date:   2013-06-26 14:49:56
categories: git meteoritecloud
---


*   Being able to dig out a version of a file from a previous state, particularly useful for solving discrepancies;
*	The ability to see who last made a change to something that may be causing trouble;
*	The capability to regress the whole of a project back to a previous state.
*	At the committed stage, data is saved locally; 
*	At the modified stage, the file has been altered but it is not yet committed to the database;
*	When changes are staged, an adapted file is earmarked in its present version to transfer into a commit snapshot.
*	The Git directory is where the metadata and database of the project is kept. If a repository is cloned from another computer, it is stored here.
*	The working directory is a checkout of a certain version of the project. These files can be extracted from the compressed database in the Git directory and put on to disk if needs.
*	The staging area acts as a workspace that stores information about what will transfer into the proceeding commit.
    $ git init
    $ git add *.c
    $ git add README
    $ git comit –m ‘initial project version’
    git clone
    $ git clone git://github.com/schacan/grit.git
    $ git clone git://git hub.com/schacan/grit.git mygrit
    $ git status
    # On branch master
    nothing to commit (working directory clean)
    $ vim README 
    $ git status 
    # On branch master 
    # Untracked files: 
    #   (use "git add <file>..." to include in what will be committed) 
    # 
    #   README nothing added to commit but untracked files present (use "git add" to track)
    $ git add README
    $ git status 
    # On branch master 
    # Changes to be committed: 
    #   (use "git reset HEAD <file>..." to unstage) 
    # 
    #   new file:   README 
    # 
    # Changes not staged for commit: 
    #   (use "git add <file>..." to update what will be committed) 
    # 
    #   modified:   benchmarks.rb 
    #
    $ git add benchmarks.rb 
    $ git status 
    # On branch master 
    # Changes to be committed: 
    #   (use "git reset HEAD <file>..." to unstage) 
    # 
    #   new file:   README 
    #   modified:   benchmarks.rb 
    #
    $ vim benchmarks.rb 
    $ git status 
    # On branch master 
    # Changes to be committed: 
    #   (use "git reset HEAD <file>..." to unstage) 
    # 
    #   new file:   README 
    #   modified:   benchmarks.rb 
    # 
    # Changes not staged for commit: 
    #   (use "git add <file>..." to update what will be committed) 
    # 
    #   modified:   benchmarks.rb 
    #
    $ git add benchmarks.rb 
    $ git status 
    # On branch master 
    # Changes to be committed: 
    #   (use "git reset HEAD <file>..." to unstage) 
    # 
    #   new file:   README 
    #   modified:   benchmarks.rb 
    #
    $ git status 
    # On branch master 
    # Changes to be committed: 
    #   (use "git reset HEAD <file>..." to unstage) 
    # 
    #   new file:   README 
    # 
    # Changes not staged for commit: 
    #   (use "git add <file>..." to update what will be committed) 
    # 
    #   modified:   benchmarks.rb 
    #
    $ git diff 
    diff --git a/benchmarks.rb b/benchmarks.rb 
    index 3cb747f..da65585 100644
     --- a/benchmarks.rb
     +++ b/benchmarks.rb 
    @@ -36,6 +36,10 @@ def main            	
        @commit.parents[0].parents[0].parents[0]          
      	end  
 
     +        run_code(x, 'commits 1') do 
     +          git.commits.size 
     +        end 

    +          run_code(x, 'commits 2') do
    $ git diff --cached 
    diff --git a/README b/README 
    new file mode 100644 
    index 0000000..03902a1 
    --- /dev/null 
    +++ b/README2 
    @@ -0,0 +1,5 @@ 
    +grit 
    + by Tom Preston-Werner, Chris Wanstrath 
    + http://github.com/mojombo/grit 
    + 
    +Grit is a Ruby library for extracting information from a Git repository
    $ git commit
    git config—global core.editor 
    # Please enter the commit message for your changes. Lines starting 
    # with '#' will be ignored, and an empty message aborts the commit. 
    # On branch master # Changes to be committed: 
    #   (use "git reset HEAD <file>..." to unstage) 
    # 
    #       new file:   README 
    #       modified:   benchmarks.rb 
    ~ 
    ~ 
    ~ 
    ".git/COMMIT_EDITMSG" 10L, 283C
    $ git commit -m "Story 182: Fix benchmarks for speed" 
    [master]: created 463dc4f: "Fix benchmarks for speed"  
    2 files changed, 3 insertions(+), 0 deletions(-)  
    create mode 100644 README 
