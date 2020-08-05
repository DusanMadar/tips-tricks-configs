# Tips-Tricks-Configs
Things which I want to have the same on all machines and I use often but cannot remember or find interesting (worth noting).

* [Docker](#docker)
* [Git](#git)
* [Python](#python)
  * [Async](#async)
  * [Debugging](#debugging)
  * [Django](#django)
  * [Environment](#environment)
  * [Generators](#generators)
  * [Testing](#testing)
* [Resources](#resources)
  * [SW Development](#sw-development)
* [Ubuntu](#ubuntu)
  * [Fresh install](#fresh-install)
  * [Gnome shortcuts](#gnome-shortcuts)
  
  
## Docker
* [Remove dangling images](https://gist.github.com/anildigital/862675ec1b7bccabc311)
  ```
  docker rmi $(docker images -q -f dangling=true)
  ```
* https://medium.com/@tonistiigi/advanced-multi-stage-build-patterns-6f741b852fae
  * Multi stage build patterns
* https://medium.com/better-programming/about-var-run-docker-sock-3bfd276e12fd
  * Intro to `/var/run/docker.sock`
* https://nickjanetakis.com/blog/best-practices-when-it-comes-to-writing-docker-related-files
  * Best Practices When It Comes to Writing Docker Related Files
* https://jtreminio.com/blog/traefik-on-docker-for-web-developers/
  * Intro to [Traefik](https://traefik.io/) (+explanation)

## Git
* [4 branching workflows for Git](https://medium.com/@patrickporto/4-branching-workflows-for-git-30d0aaee7bf)
  * [What is the difference between `git merge` and `git merge --no-ff`?](https://stackoverflow.com/q/9069061/4183498)
* [Show the git branch with colours in Bash prompt](https://askubuntu.com/q/730754/355551)
* [Temporarily switch to a different commit](http://stackoverflow.com/a/4114122/4183498)
  ```
  git checkout -b {branch name} {commit hash}
  ```
* [Delete branch both locally and remotely](http://stackoverflow.com/q/2003505/4183498)
  ```
  git branch -D {local branch}
  git push {remote} --delete {branch name}
  ```
* [Reset local changes to match remote branch](http://stackoverflow.com/q/1628088/4183498)
  ```
  git fetch origin
  git reset --hard origin/{branch name}
  ```
* Date ordered log for a given author
  ```
  git log --date-order --author="{author name}"
  ```
* [Point local branch to a remote branch](http://stackoverflow.com/q/1184518/4183498)
  ```
  git checkout {local branch}
  git branch -u {remote}/{remote branch}
  ```
  
  There are two options when pushing local branch to the remote's master branch
  * [Specify branch mapping](http://stackoverflow.com/a/5423655/4183498)
    ```
    git push {remote} {local branch name}:master
    ```
  * [Change the default _git push_ behavior](http://stackoverflow.com/q/948354/4183498)
    ```
    git config push.default upstream
    ```


## Python

### Async
* [Python & Async Simplified](https://www.aeracode.org/2018/02/19/python-async-simplified/)

### Debugging
* [Execute multi-line statements within PDB](http://stackoverflow.com/q/5967241/4183498)
  ```python
  (pdb) !import code; code.interact(local=vars())
  ```
### Django
* [Part V – Internationalization and Localization. Languages and Time zones](http://www.marinamele.com/taskbuster-django-tutorial/internationalization-localization-languages-time-zones)
* [Django translation tutorial](http://joaoventura.net/blog/2016/django-translation/)
* [Django site with 2 languages](https://stackoverflow.com/q/10280881/4183498)
* [Getting started with translating a Django Application](https://blog.braham.biz/getting-started-with-translating-a-django-application-d85ec34e505)
* [Solving Performance Problems in the Django ORM](https://medium.com/@hansonkd/performance-problems-in-the-django-orm-1f62b3d04785)
* [Avoid Django’s GenericForeignKey](https://lukeplant.me.uk/blog/posts/avoid-django-genericforeignkey/)
* [Django migrations without downtimes](https://pankrat.github.io/2015/django-migrations-without-downtimes/)

### Environment
* [How do you set your pythonpath in an already-created virtualenv?](https://stackoverflow.com/q/4757178/4183498)
  ```
  add2virtualenv /path/to/target/dir
  ```
* [How do I find the location of my Python site-packages directory?](https://stackoverflow.com/q/122327/4183498)
  ```bash
  python -m site
  ```
 
### Generators
* https://rickardlindberg.me/writing/bitten-by-python-generators/

### Testing
* [Mocking a context manager](http://stackoverflow.com/q/28850070/4183498)
* [Mock yourself, not your tests](http://hernantz.github.io/mock-yourself-not-your-tests.html)
* [Fast Test, Slow Test](https://www.youtube.com/watch?v=RAxiiRPHS9k)
* [Boundaries](https://www.youtube.com/watch?v=eOYal8elnZk)

* [How to automatically run tests when there's any change in my project (Django)?](https://stackoverflow.com/q/15166532/4183498])
  ```bash
  find . -name "*.py" | entr python -m unittest discover
  ```
  * https://github.com/clibs/entr

* Coverage report
  ```bash
  python -m unittest discover -s tests/
  coverage run -m unittest discover -s tests/
  coverage report -m --include="*{your_app_name}*"
  ```


## Resources

Links to resources (tutorials, books, blog posts, repositories, ...).

### SW Development

* https://github.com/jamiebuilds/the-super-tiny-compiler
  * Reading through the guided code will help you learn about how most compilers work from end to end
  
* https://github.com/karan/Projects
  * A list of practical projects that anyone can solve in any programming language


## Ubuntu

### Gnome shortcuts
https://help.gnome.org/users/gnome-help/stable/shell-keyboard-shortcuts.html

| Action                                            | Shortcut                            |
| :------------------------------------------------ |:----------------------------------- |
| Switch between workspaces                         | Super + Page Up / Page Down         |
| Move the current window to a different workspace  | Shift + Super + Page Up / Page Down |
| Move the current window one monitor to the left   | Shift + Super + ←                   |
| Move the current window one monitor to the right  | Shift + Super + →                   |


### Fresh install

#### Interface
* 
  ```
  sudo apt update
  sudo apt upgrade
  sudo apt install gnome-tweaks gnome-shell-extensions chrome-gnome-shell
  sudo apt install gir1.2-gtop-2.0 gir1.2-networkmanager-1.0 gir1.2-clutter-1.0
  gnome-session-quit
  ```

* window buttons to left
	 * gnome-tweaks -> windows -> bottom most "Placement" (under "Titlebar Buttons")

* don't suspend on lid closed
	 * gnome-tweaks -> power -> switch off

* minimize on icon click
	 * gsettings set org.gnome.shell.extensions.dash-to-dock click-action 'minimize'
  
* add keyboard layout
	 * settings -> Region & Language	
  
* change keyboard layut switch shortcut to alt + shift
	 * gnome-tweaks -> keyboard and mouse -> Additional Layout Options -> Switching to another layout

* install gnome shell integration browser extension (to firefox, preferably)
	 * https://extensions.gnome.org/

* move panel time to right
	 * https://extensions.gnome.org/extension/2/move-clock/

* system monitor shell extension
	 * https://extensions.gnome.org/extension/120/system-monitor/

* suspend button shell extension
	 * https://extensions.gnome.org/extension/826/suspend-button/

* center new window
	 * `sudo apt install dconf-editor`
	 * set center-new-windows" in /org/gnome/mutter/ to "true"
  

#### Common
```
sudo apt install curl git python3-pip tmux xclip meld
```

#### virtualenvwrapper
Credits: https://medium.com/@gitudaniel/installing-virtualenvwrapper-for-python3-ad3dfea7c717\
```
pip3 install virtualenvwrapper
```

Add to `~/.bashrc`
```
export WORKON_HOME=$HOME/.virtualenvs
export VIRTUALENVWRAPPER_PYTHON=/usr/bin/python3
export VIRTUALENVWRAPPER_VIRTUALENV=~/.local/bin/virtualenv
source ~/.local/bin/virtualenvwrapper.sh
```
then run `source ~/.bashrc`

#### Golang
Download installer (not source!), e.g. `go1.11.1.linux-amd64.tar.gz` from https://golang.org/dl/
```
cd ~/Downloads/
sudo tar -C /usr/local -xzf go$VERSION.$OS-$ARCH.tar.gz
```

Add to `~/.bashrc`
```
export PATH=$PATH:/usr/local/go/bin
export GOPATH=$HOME/code/go
export PATH=$PATH:/usr/local/go/bin:$(go env GOPATH)/bin
```
then run `source ~/.bashrc`

##### Delve
```
go get -u github.com/derekparker/delve/cmd/dlv
```

#### Docker
Credits: https://medium.com/devgorilla/how-to-install-docker-on-ubuntu-18-04-495216a16092
```
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable edge"
apt-cache policy docker-ce
sudo apt install -y docker-ce
sudo usermod -aG docker ${USER}
```

##### Docker Compose
Credits: https://www.digitalocean.com/community/tutorials/how-to-install-docker-compose-on-ubuntu-18-04

#### Media
```
sudo apt install vlc clementine
```

#### VirtualBox
```
sudo apt install virtualbox
sudo apt install virtualbox-guest-additions-iso
sudo apt install virtualbox-ext-pack
sudo adduser $USER vboxusers
```

#### Laptop specific
```
sudo apt install tlp tlp-rdw
```
