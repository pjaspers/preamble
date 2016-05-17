`preamble |priːˈamb(ə)l, ˈpriː-| - a preliminary or preparatory statement`

Our current playbook to set up our CI server.

### What will it do

- Install [Homebrew](http://brew.sh)
- Install several rubies (see `ruby.yml`)
- Install Jenkins
- Add some command line niceties.

And more, see the `playbook.yml` for more info.

### Steps

- Install Xcode
- `git clone https://github.com/10to1/preamble.git`
- `sudo easy_install pip; sudo pip install ansible`
- `cd preamble`
- `ansible-playbook playbook.yml --ask-sudo-pass` (it needs sudo for `nginx`)

Once this is done, installing new things is as easy as changing the `playbook.yml` and rerunning `ansible-playbook playbook.yml --ask-sudo-pass`.

I've also tried to add some tags, so you can target specific parts of it (`ansible-playbook --tags=tag1,tag2`) or skip specific parts (`ansbible-playbook --skip-tags=tag1,tag2`).

Available tags:

- ios (Installs everything related to iOS)
- mail (Installs mutt and friends)
- nginx (Install nginx and dnsmasq, requires root)
- ruby (Install rubies)
- phantomjs (Install phantomjs)
- osx (Installs os x applications, and also `capslock` and `defaults`)
- capslock (Remaps capslock to control)
- defaults (Sets Finder defaults)
