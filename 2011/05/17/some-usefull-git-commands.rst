public: yes
tags: [git]

Some usefull Git commands to know
=================================

A list of git commands that I use regularly and which may be useful:

``git diff --cached``
    stage changes

``git add -p``
    Git add in interactive mode (patch per patch)

``git submodule update --init [--recursive]``
    Update and/or install all submodules (recursively)

``git push origin :branch-or-tag-name``
    Delete remote branch or tag

``git log origin/master ^master``
    Show diff beetween remote and local branch

``git br --contains commit``
    Show in which branch is contained a commit (thx MarcW)

``git push origin commit:master``
    Push master to origin remote until a commit

``git co my_file.txt --theirs/--ours``
    In a merge with conflict, checkout local branch (ours) or other branch (theirs) file version

