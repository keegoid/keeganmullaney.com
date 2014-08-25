keeganmullaney.com
==================

My personal blog site powered by [Middleman][mm] and [GitHub][gh], hosted by [BitBalloon][bb].

Overview:

As I've taken on more projects, my free time has become somewhat lacking. I wanted to find a workflow for maintaining a personal blog site and creating new blog posts that would be easy to remember and repeat, produce a fast, secure site and be easily transferrable to any host or server. I decided a [static site generator][mm] utilizing [Markdown][md] formatted posts was the way to go. What follows is my ultimate time-saving, static site generating, refreshingly tranquil blog post writing process:

- version control is done with [git][git], and all is right with the world
- changes to code and this readme file are done with [gEdit][ge] on my [CentOS 7.0 x64][centos] workstation
- new posts are written in [GitHub flavored Markdown][gfm] using [Draft][draftin] and saved to my [Dropbox][db] repository
- changes and new posts are committed with [git][git] and pushed to my remote repository on [GitHub][gh]
- [BitBalloon][bb] listens for pushes to [GitHub][gh], then automatically builds and deploys the static site
- I read a book, drink some wine, revel in all my new found free time
- rinse and repeat

If you like this workflow and decide to adopt it, please do let me know: [@keegoid][twitter]

## Usage

##### Fork and clone

1. fork http://github.com/keegoid/middleman-html5-foundation/fork
1. clone your own fork using HTTPS or SSH (recommended)
   - HTTPS: `git clone https://github.com/yourusername/keeganmullaney.com.git`
   -   SSH: `git clone git@github.com:yourusername/keeganmullaney.com.git`

##### BitBalloon setup

To set up the automatic [BitBalloon][bb] deploys, log in as a non-root user.  

```bash
# cd to your Middleman project directory and install run:
bundle install

# optionally, run the local middleman server at http://localhost:4567/
# to confirm that your new site is functional:
bundle exec middleman

# commit your changes with git:
git commit -am 'first commit'

# push commits to your remote repository (GitHub):
git push origin master
```

go to the [BitBalloon][bb] site and:

   1. do an initial manual drag and drop deploy of your new site
   1. go to your site in the BitBalloon UI
   1. click *"Link site to a GitHub repo"* at the bottom right  
      (currently a beta feature so you may need to request access)
   1. choose which branch you want to deploy (typically master)
   1. set the directory to `Other ...` enter `/build`
   1. for the build command, set: `bundle exec middleman build`

Now whenever you push changes to [Github][gh], [BitBalloon][bb] will run middleman and deploy the /build folder to your site automatically. Easy!

## Configuration



## Contributing

I welcome contributions and pull requests. I look forward to learning from you!

##### Getting started

A clear intro to [using git][learngit].  
A good [step-by-step guide][fork] about how to contribute to a GitHub project like this one.

##### Steps

1. Fork http://github.com/keegoid/keeganmullaney.com/fork
1. Clone your own fork using HTTPS or SSH (recommended)
   - HTTPS: `git clone https://github.com/yourusername/keeganmullaney.com.git`
   -   SSH: `git clone git@github.com:yourusername/keeganmullaney.com.git`
1. Optionally create your own feature branch `git checkout -b my-new-feature`
1. Commit your changes `git commit -am 'made some cool changes'`
1. Push your master or branch commits to GitHub
   - `git push origin master`
   - `git push origin my-new-feature`
1. Create a new [Pull request][pull]

## Workflow

##### Markdown

After much tribulation with [Markdown][md] editors and various workflows, I've found what I think is a great way to create/maintain my [Markdown][md] docs.

For blog posts or any long-form writing, [Draft][draftin] is wonderful, especially the `F11` mode. It mostly works with [GitHub flavored Markdown][gfm] except for strikethrough and alignment of table columns. 
I then *Export* my document to the appropriate [git][git] repository in [Dropbox][db] (which then syncs with my various devices).
Finally, I commit the new document with [git][git] and push it to the remote repository (which then gets automatically built and deployed on [BitBalloon][bb]).

For other [Markdown][md] docs like *README.md* or *LICENSE.md* I find [gEdit][ge] to be easy and efficient. I can make some quick edits, commit changes in [git][git] and push them to [GitHub][gh] with just a few commands. It's also easy to repeat commits and pushes with the keyboard up arrow from the [Linux console][lc].  
to commit again: `up up enter`, to push again: `up up enter`

##### Git remote

If you didn't start by cloning your repository on [GitHub][gh], for example if you used `git init` on your workstation, you'll need to add your remote origin URL:

```bash
# HTTPS:
git remote add origin https://github.com/yourusername/keeganmullaney.com.git

# SSH:
git remote add origin git@github.com:yourusername/keeganmullaney.com.git
```

You can also set the upstream repository to fetch changes from this project:

```bash
# HTTPS:
git remote add upstream https://github.com/keegoid/keeganmullaney.com.git

# SSH:
git remote add upstream git@github.com:keegoid/keeganmullaney.com.git
```

Then `git fetch upstream master` and `git merge upstream/master`  
or accomplish both with `git pull upstream master`

##### Git push and pull

```bash
# git config
# author
git config --global user.name 'Keegan Mullaney'
git config --global user.email 'keegan@kmauthorized.com'
# select a text editor, I prefer vi, you can also use vim or something else
git config --global core.editor vi
# add some SVN-like aliases
git config --global alias.st status
git config --global alias.co checkout
git config --global alias.br branch
git config --global alias.up rebase
git config --global alias.ci commit
# set the default push and pull methods for git to "matching"
git config --global push.default matching
git config --global pull.default matching

# commit changes with git
git commit -am 'update README'

# create a new branch and check it out
git checkout -b 'branch-name'

# link the origin/<branch> with your local <branch>
git branch -u origin/branch-name branch-name
```

Now you can simply use `git push` or `git pull` from your current branch, inluding master. It's nice to be able to reduce the length of these commands so you don't have to think about what you're pushing or pulling each time. Just make sure you've got the right branch checked out!

**long versions**

push or pull changes to/from origin (GitHub):  
`git push origin master` or `git push origin branch-name`  
`git pull origin master` or `git pull origin branch-name`

Note, use `git config --list` to view all configured options.

I hope you find this workflow as efficient and effective as I do.


[mm]:       http://middlemanapp.com/
[gh]:       https://github.com/
[bb]:       https://www.bitballoon.com/
[git]:      http://git-scm.com/
[centos]:   http://centos.org/
[lc]:       http://en.wikipedia.org/wiki/Linux_console
[db]:       https://db.tt/T7Pstjg "clicking this affiliate link benefits me at no cost to you"
[gfm]:      https://help.github.com/articles/github-flavored-markdown
[md]:       http://daringfireball.net/projects/markdown/
[ge]:       https://wiki.gnome.org/Apps/Gedit
[draftin]:  https://draftin.com/
[twitter]:  https://twitter.com/intent/tweet?screen_name=keegoid&text=your%20blog%20site%20workflow%20with%20%40middlemanapp%2C%20%40github%20and%20%40BitBalloon%20saved%20my%20life%20https%3A%2F%2Fgithub.com%2Fkeegoid%2Fkeeganmullaney.com
[lp]:       https://lastpass.com/
[learngit]: https://www.atlassian.com/git/tutorial/git-basics#!overview
[fork]:     https://help.github.com/articles/fork-a-repo
[pull]:     https://help.github.com/articles/using-pull-requests

