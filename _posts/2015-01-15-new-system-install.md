---
layout: post
title: 'New System Install'
tags: [blog, new-system-install, OS-X, homebrew, homebrew-cask, dev-tools]
---

With the release of OS-X Mavericks, I decided it was time for a clean install of my system. I decided that this time, I would try and automate this as much as possible, without having to resort to being there very much, because, well... time is precious and I have better things to do.

The script and general steps I used can be found in a bash file I have on my [github account](https://github.com/quandrei/new-system-install-script-osx).

### Initial (manual) steps

You will notice that in the script, the first few installs are commented out. I originally did these manually, because they are crucial (i.e. the rest will just fail without the success of those), and hadn't really planned on a script at that point. The tools are as follows:

#### OS-X command line tools
{% highlight bash %}
xcode-select --install
{% endhighlight %}

#### [Oh-my-ZSH](http://ohmyz.sh/)
{% highlight bash %}
curl -L http://install.ohmyz.sh | sh
{% endhighlight %}

#### [homebrew](http://brew.sh/)
{% highlight bash %}
ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
{% endhighlight %}

#### [homebrew-cask](http://caskroom.io/)
{% highlight bash %}
brew install caskroom/cask/brew-cask
{% endhighlight %}

You might also want to specify some defaults for homebrew-cask, e.g. default of where you want your apps installed:

{% highlight bash %}
### Specify your defaults in this environment variable 
### (in .bash_profile or .zshenv) 
export HOMEBREW_CASK_OPTS="--appdir=/Applications"
{% endhighlight %}

More can be found in the [usage docs](https://github.com/caskroom/homebrew-cask/blob/master/USAGE.md).

---

I will not go into explaining why these tools are great and why you should use them. There are many articles out there. Just use the googles or [duck-duck-go](https://duckduckgo.com/), whichever you prefer.

The rest of the script is essentially grabbing what I need/want; specifically, environment-wise via homebrew and gui apps via homebrew-cask. Nice thing about this, is I don't need to deal with downloaders and going to each invidual site. And updating/maintaining everything is a breeze, and achieved with a few simple commands in the terminal. 

If you are too lazy to actually look at my bash script, the following is a list of what I install:

#### homebrew packages
* wget
* git
* git-flow
* tree
* node
* sqlite
* postgresql
* mongodb
* mcrypt
* php56
* php56-mcrypt
* php56-xdebug
* phpunit
* openssl
* gpg2

#### homebrew cask packages
* vagrant
* virtualbox
* alfred
* iterm2
* onepassword
* seil
* divvy
* sourcetree
* dropbox
* firefox
* firefoxdeveloperedition
* google-chrome
* google-chrome-canary
* spotify
* vlc
* sublime-text3
* sequel-pro

I have not linked to any of these, cause I am lazy too. If this irks you, please submit your grievance to the complaints dept.