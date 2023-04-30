# What's this

A Heroku buildpack which installs Oracle client 21.1.

Inspired by https://elements.heroku.com/buildpacks/lalomores/oracle-client-buildpack.

# Description

Intended to be used in conjunction with other buildpacks for apps that require access to Oracle databases.

## Usage

1. Dependency buildpack

Add the libaio buildpack first in order to provide libaio1:

```
heroku buildpacks:add https://github.com/heroku/heroku-buildpack-apt.git --index 1
```

Then add a file named `Aptfile` in the root of your source code with this content:

```
libaio1
```


2. Add this buildpack

```
heroku buildpacks:add https://github.com/dpapaspyros/oracle-client-buildpack.git --index 2
```

Alternatively, use `.buildpacks` to add both buildpacks in order.