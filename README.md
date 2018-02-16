selenium-invadelabs [![Build Status](https://travis-ci.org/invadelabs/selenium-invadelabs.svg?branch=master)](https://travis-ci.org/invadelabs/selenium-invadelabs)
===================
Selenium, Docker, and Tavis CI testing for Invade Labs.

## Spin up if testing on local
```
docker run -d -p 4444:4444 -v /dev/shm:/dev/shm selenium/standalone-chrome:3.8.1-chlorine
docker run -d -p 4445:4444 -v /dev/shm:/dev/shm selenium/standalone-firefox:3.8.1-chlorine
```

## Install Firefox 54 or earlier for Selenium IDE
Selenium IDE isn't supported on Firefox >= 55
https://ftp.mozilla.org/pub/firefox/releases/54.0/linux-x86_64/en-US/firefox-54.0.tar.bz2

Download Firefox 54, create a new profile, and disable automatic updates.
```
tar jxvf firefox-54.0.tar.gz
./firefox-bin --ProfileManager --new-instance
Options > Preferences > Select the Advanced panel > Select the Update tab.
Check Never check for updates
```

## Install selenium-ide extension
https://addons.mozilla.org/en-US/firefox/addon/selenium-ide/


## Use Selenium IDE in Firefox
`Developer > Selenium IDE > Record`

## Install ruby-2.4.1 and gems
```
rvm use 2.4.1
bundle install
```

## Test
Generate a screenshot from our tests with output files `chrome_#{time}.png` and `firefox_#{time}.png` and email them.
```
export SENDGRID_API_KEY="my awesome key"
ruby ./chrome.rb
ruby ./firefox.rb
```
