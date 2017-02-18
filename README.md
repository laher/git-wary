# git-wary

Wary merging - for more predictable releases

Before releasing code to master, you probably want to know that your release has been tested.

Wait, is there anything in master which isn't in your release? If so, your release is untested.

This check ought to be performed twice. Once when you plan the release, and once again when you actually merge it

## What?

1. Warily merge into master

```
git checkout master
git wary merge release/1.2.3
```

_git-wary will fail if master contains any changes not in the release_

2. Warily check if a release is ready for master

```
git wary check release/1.2.3
```

## Setup

`export PATH=path/to/git-wary:$PATH`


## Alternative

This is the equivalent of the following. Note that we can't have 

```
git checkout release/1.2.3
git merge master
#run tests on release/1.2.3
git checkout master
git merge release/1.2.3
```
