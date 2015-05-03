# Docker Ember CLI

A docker image that packages the latest version of Ember CLI, IOJS, and Bower. It also includes the version of PhantomJS packaged through NPM to provide testing.

## Dockerfile

[`akeem/selenium-node-phantomjs` Dockerfile](https://github.com/AkeemMcLennon/docker-ember-cli/blob/master/Dockerfile)

## How to use this image

This image uses the working directory `/usr/src/app` as its volume. To initialize a new ember app for example, you would run

```
$ docker run -v "$PWD":/usr/src/app -it --rm akeem/ember ember init
```

By default, this image doesn't specify a user apart from root and is not intended to be used a daemon in production.  However, if you would like you run bower without running as a separate user, you can also run 

```
$ docker run -v "$PWD":/usr/src/app -it akeem/ember bower install --alow-root 
```

Keep in mind that this effectively runs all commands as root.
