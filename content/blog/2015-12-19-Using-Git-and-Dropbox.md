---
title: "Using Git and Dropbox"  
date: "2015-12-19"
slug: "using-git-and-dropbox"
---



I have been using [Git](https://git-scm.com/) and [Github](https://github.com/) for a little while and I think both of them are great. However, there are a few Git projects that I either don't want to put on Github or can't but I want to work on them on multiple computers. I might also add that I don't (at the moment) want to pay for private repositories and instead of using an alternative online service I found out I could use Dropbox. To clarify, these are for projects only I am working on.

To start with let us assume we already have a git repository on one machine. The first step is to create a bare git repository in [Dropbox](https://www.dropbox.com). I have decided to have a specific folder in my main Dropbox folder for all my Git repositories, so we put the new bare respository in there.

``` shell
git init --bare ~Dropbox/Git/New_repos
```

Then we need to add that as a remote in the repository we're working on.

``` shell
git remote add dropbox ~Dropbox/Git/New_repos
```

Finally we push to the remote.

``` shell
git push -u master dropbox
```

The "-u" flag comes from this [blog](http://blog.shvetsov.com/2013/04/using-git-with-dropbox.html) which I followed and it tells Git to track the bare dropbox repository as [upstream](http://stackoverflow.com/questions/2739376/definition-of-downstream-and-upstream).

Now if I am working on my other machine I can `clone` the repository with

``` shell
git clone ~/Dropbox/Git/New_repos
```
	
and I like to rename the remote.

``` shell
git remote rename origin dropbox
```
	
I know that I could do it all in one step as

``` shell
git clone -o dropbox ~/Dropbox/Git/New_repos
```

but I keep forgetting. The `-o` controls the name of the remote and we can check everything looks ok by looking at the remotes

``` shell
git remote -v
```

which should return something along the lines of

``` shell
dropbox ~/Dropbox/Git/New_repos (fetch)
dropbox ~/Dropbox/Git/New_repos (push)
```

to finish. Once that is done I can push/pull as normal to ensure everything is up to date.