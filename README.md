# spedepekka.github.io

Sources for https://jarnotuovinen.com

[Hakukoneoptimointi Oulu](http://www.kranu.fi/hakukoneoptimointi/oulu)

## How to run this locally

This should work on Ubuntu 22.04 WSL

Install stuff

```
apt install gnupg2
gpg2 --keyserver keyserver.ubuntu.com --recv-keys 409B6B1796C275462A1703113804BB82D39DC0E3 7D2BAF1CF37B13E2069D6956105BD0E739499BDB
# from https://rvm.io/
curl -sSL https://get.rvm.io | bash -s stable
source /etc/profile.d/rvm.sh
# update list of known rubies
rvm get head
rvm install 3.4.1
bundle install
```

Run stuff

```
bundle exec jekyll serve
```

Go to

http://localhost:4000

