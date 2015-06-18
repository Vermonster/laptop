Laptop
======

Laptop is a script to set up an OS X laptop for web development.

It can be run multiple times on the same machine safely.
It installs, upgrades, or skips packages
based on what is already installed on the machine.

Requirements
------------

We support:

* [OS X Mavericks (10.9)](https://itunes.apple.com/us/app/os-x-mavericks/id675248567)
* [OS X Yosemite (10.10)](https://www.apple.com/osx/)

Older versions may work but aren't regularly tested. Bug reports for older
versions are welcome.

Install
-------

Download, review, then execute the script:

```sh
curl --remote-name https://raw.githubusercontent.com/Vermonster/laptop/master/mac
less mac
sh mac 2>&1 | tee ~/laptop.log
```

Optionally, [install thoughtbot/dotfiles][dotfiles].

[dotfiles]: https://github.com/thoughtbot/dotfiles#install

Debugging
---------

Your last Laptop run will be saved to `~/laptop.log`.
Read through it to see if you can debug the issue yourself.
If not, copy the lines where the script failed into a
[new GitHub Issue](https://github.com/thoughtbot/laptop/issues/new) for us.
Or, attach the whole log file as an attachment.

What it sets up
---------------

* [Bundler] for managing Ruby libraries
* [Exuberant Ctags] for indexing files for vim tab completion
* [Firefox]
* [Foreman] for managing web processes
* [hub] for interacting with the GitHub API
* [Git] for version control
* [GitX]
* [Google Chrome]
* [Google Drive]
* [Google Hangouts]
* [Heroku Toolbelt] for interacting with the Heroku API
* [Homebrew] for managing operating system libraries
* [ImageMagick] for cropping and resizing images
* [iTerm2]
* [Node.js] and [NPM], for running apps and installing JavaScript packages
* [Postgres] for storing relational data
* [PhantomJS] for headless JavaScript testing via Poltergeist
* [Rbenv] for managing versions of Ruby
* [RCM] for managing company and personal dotfiles
* [Redis] for storing key-value data
* [Ruby Build] for installing Rubies
* [Ruby] stable for writing general-purpose code
* [Screenhero] for screen sharing
* [The Silver Searcher] for finding things in files
* [Slack] for team communication/messaging
* [Sublime Text]
* [Tmux] for saving project state and switching between projects
* [Vim]
* [Zsh] as your shell

[Bundler]: http://bundler.io/
[Exuberant Ctags]: http://ctags.sourceforge.net/
[Firefox]: https://www.mozilla.org/en-US/firefox/new/
[Foreman]: https://github.com/ddollar/foreman
[hub]: http://hub.github.com/
[Git]: https://git-scm.com/
[GitX]: http://rowanj.github.io/gitx/
[Google Chrome]: http://http://www.google.com/chrome/
[Google Drive]: https://www.google.com/drive/
[Google Hangouts]: https://www.google.com/hangouts/
[Heroku Toolbelt]: https://toolbelt.heroku.com/
[Homebrew]: http://brew.sh/
[ImageMagick]: http://www.imagemagick.org/
[iTerm2]: https://www.iterm2.com/
[Node.js]: http://nodejs.org/
[NPM]: https://www.npmjs.org/
[Postgres]: http://www.postgresql.org/
[PhantomJS]: http://http://phantomjs.org/
[Rbenv]: https://github.com/sstephenson/rbenv
[RCM]: https://github.com/thoughtbot/rcm
[Redis]: http://redis.io/
[Ruby Build]: https://github.com/sstephenson/ruby-build
[Ruby]: https://www.ruby-lang.org/en/
[Screenhero]: https://screenhero.com/
[The Silver Searcher]: https://github.com/ggreer/the_silver_searcher
[Slack]: https://slack.com/
[Sublime Text]: http://www.sublimetext.com/3
[Tmux]: http://tmux.sourceforge.net/
[Vim]: http://www.vim.org/
[Zsh]: http://www.zsh.org/

It should take less than 15 minutes to install (depends on your machine).

Customize in `~/.laptop.local`
------------------------------

Your `~/.laptop.local` is run at the end of the Laptop script.
Put your customizations there.
For example:

```sh
#!/bin/sh

brew_install_or_upgrade 'mongodb'
brew_launchctl_restart 'mongodb'

brew_cask_install 'alfred'
brew_cask_install 'dash'

gem_install_or_update 'parity'

```

Write your customizations such that they can be run safely more than once.
See the `mac` script for examples.

Laptop functions such as `fancy_echo`,
`brew_install_or_upgrade`, and
`gem_install_or_update`
can be used in your `~/.laptop.local`.

See the [wiki](https://github.com/thoughtbot/laptop/wiki)
for more customization examples.

Contributing
------------

Edit the `mac` file.
Document in the `README.md` file.
Follow shell style guidelines by using [ShellCheck] and [Syntastic].

```sh
brew install shellcheck
```

[ShellCheck]: http://www.shellcheck.net/about.html
[Syntastic]: https://github.com/scrooloose/syntastic

Thank you, [contributors]!

[contributors]: https://github.com/thoughtbot/laptop/graphs/contributors

By participating in this project,
you agree to abide by the thoughtbot [code of conduct].

[code of conduct]: https://thoughtbot.com/open-source-code-of-conduct

License
-------

Laptop is © 2011-2015 thoughtbot, inc.
It is free software,
and may be redistributed under the terms specified in the [LICENSE] file.

[LICENSE]: LICENSE

About thoughtbot
----------------

![thoughtbot](https://thoughtbot.com/logo.png)

Laptop is maintained and funded by thoughtbot, inc.
The names and logos for thoughtbot are trademarks of thoughtbot, inc.

We are passionate about open source software.
See [our other projects][community].
We are [available for hire][hire].

[community]: https://thoughtbot.com/community?utm_source=github
[hire]: https://thoughtbot.com?utm_source=github
