`preamble |priːˈamb(ə)l, ˈpriː-| - a preliminary or preparatory statement`

My current playbook to setting up a new Mac, it uses [Ansible](http://www.ansible.com/home) because it's easy to read and write and I hope it helps me avoid [this](http://xkcd.com/1319/).

I realise automating setting up a new machine probably isn't worth my time, [here's a handy graph to see why](http://xkcd.com/1205/). However, automating setting up a new machine wasn't the real goal, it was a headfake. By writing this I have an easy way to show others (and future me) what applications I'm using and how I installed them. An added bonus is the glee in feeling like I'm doing HIGH TECH COMPUTERING by installing stuff from a text file.

### What will it do

- Install [Homebrew](http://brew.sh)
- Install several rubies (see `ruby.yml`)
- Install nginx and dnsmasq to work along [nginx-app](https://github.com/reprazent/wak) to have `.dev` domains available
- Install command line apps I use
- Install apps I use (everything I didn't get through App Store is installed using `brew cask`)
- Set some sensible OSX defaults

And more, see the `playbook.yml` for more info.

### Steps

- Install Xcode
- clone this repo
- `sudo easy_install pip; sudo pip install ansible`
- `ansible-playbook playbook.yml --ask-sudo-pass` (it needs sudo for `nginx`)

Once this is done, installing new things is as easy as changing the `playbook.yml` and rerunning `ansible-playbook playbook.yml --ask-sudo-pass`.
