# jenkins-ansible-role
This ansible role is used to install jenkins and any plugins you might want.

By default it installs the following packages that jenkins will need.
```
git
curl
build-essentials
gradle
```
These will typically be needed to handle all tasks to manage jenkins and run containerized builds

And the following plugins
```
git
gradle
```
as they are needed to handle gradle based jenkins configuration (configuraiton as jenkins jobs)

Lastly it also installs docker inside the container, which we will use talk to a mounted ```docker.sock``` from the host machine. This allows the jenkins container to handle builds using docker without running docker in docker.

Since this is intended to run in a conatiner in the foreground, we do not enable the jenkins service to automatically start.  We do however start the jenkins server during build to allow for plugin installations.
