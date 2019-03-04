# CAS playground

Repository to play around with Apereo CAS configurations

## Getting started
* [Cas 6.0.x overlay tuto](https://apereo.github.io/2018/11/16/cas60-gettingstarted-overlay/)
* [Cas overlay template gradle](https://github.com/apereo/cas-overlay-template)

* Download the overlay template & copy to a different folder to apply and track changes
```
https://github.com/apereo/cas-overlay-template.git
cd cas-overlay-template
git checkout origin/6.0 -b 6.0
cd ..
mkdir cas-overlay
rsync -r cas-overlay-template/ cas-overlay/ --exclude .git
```