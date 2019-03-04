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
* Test the build (put thekeystore present in /cas-overlay/etc/cas at /etc/cas/ or generate a new one)
```
cd cas-overlay
./build.sh package
./build.sh run
```
* Check that the service is running: https://localhost:8443/cas
* Check with the dummy credentials that you can log-in:
    * username: casuser
    * password: Mellon
* Launch LDAP test server [Base image](https://github.com/osixia/docker-openldap)
```
docker-compose -f ldap.yaml up
```
* Connect to the container and check that it is running
```
docker container exec -it ldap bash
ldapsearch -x -H ldap://localhost -b dc=example,dc=org -D "cn=admin,dc=example,dc=org" -w admin
```
or installing ldap-utils from the host
```
sudo apt install ldap-utils
ldapsearch -x -H ldap://localhost -b dc=example,dc=org -D "cn=admin,dc=example,dc=org" -w admin
```