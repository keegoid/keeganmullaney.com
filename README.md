keeganmullaney.com
==================

My personal blog site powered by [Middleman][mm] and [GitHub][gh], hosted by [BitBalloon][bb].

Overview:

As I've taken on more projects, my free time has become somewhat lacking. I wanted to find a workflow for maintaining a personal blog site and creating new blog posts that would be easy to remember and repeat, produce a fast, secure site and be easily transferable to any host or server. I decided a [static site generator][mm] utilizing posts formatted in [Markdown][md] was the way to go. What follows is my ultimate time-saving, static site generating, refreshingly tranquil blog post writing process:

- version control is done with [git][git] and all is right with the world
- changes to code and this readme file are done with [gEdit][ge] on my [CentOS 7.0 x64][centos] workstation
- new posts are written in [GitHub flavored Markdown][gfm] using [Draft][draftin] and saved to my [Dropbox][db] repository
- changes and new posts are committed with [git][git] and pushed to my remote repository on [GitHub][gh]
- [BitBalloon][bb] listens for pushes to [GitHub][gh], then automatically builds and deploys the static site
- read a book, drink some wine, revel in new-found free time
- rinse and repeat

If you like this workflow and decide to adopt it, please do let me know: [@keegoid][twitter]

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**  *generated with [DocToc](http://doctoc.herokuapp.com/)*

- [Usage](#usage)
      - [Config.rb](#configrb)
      - [BitBalloon Setup](#bitballoon-setup)
- [Contributing](#contributing)
      - [Getting Started](#getting-started)
      - [Steps](#steps)
- [License](#license)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

## Usage

There are a few settings that need to be changed before this site can work for you.

##### Config.rb



##### BitBalloon Setup

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

## Contributing

Contributions are totally welcome.

##### Getting Started

A clear intro to [using git][learngit].  
A good [step-by-step guide][fork] about how to contribute to a GitHub project like this one.

##### Steps

1. fork http://github.com/keegoid/kmullaney.com/fork
1. clone your own fork using HTTPS or SSH (recommended)
   - HTTPS: `git clone https://github.com/yourusername/kmullaney.com.git`
   -   SSH: `git clone git@github.com:yourusername/kmullaney.com.git`
1. optionally create your own feature branch `git checkout -b my-new-feature`
1. commit your changes `git commit -am 'made some cool changes'`
1. push your master or branch commits to GitHub
   - `git push origin master`
   - `git push -u origin my-new-feature`
1. create a new [Pull request][pull]

## License

Author : Keegan Mullaney  
Company: KM Authorized LLC  
Website: http://kmauthorized.com

MIT: http://kma.mit-license.org


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

