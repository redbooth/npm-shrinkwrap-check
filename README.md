npm-shrinkwrap-check
====================

Checks that `package.json` and `npm-shrinkwrap.json` files are always in sync so you
don't commit out-of-sync dependencies in your code.

installation
============

Install it globally running

`$ npm install -g npm-shrinkwrap-check`

usage
=====

In a folder that contains a `package.json` run the following command:

`$ npm-shrinkwrap-check`

This will perform the following checks:

* Both `package.json` and `npm-shrinkwrap.json` exist.
* There are no dependencies in `package.json` that are **not** contained in `npm-shrinkwrap.json`

options
=======

```
Options:
  -3, --v3       Perform check taking npm3 flat structure into account.
  -d, --dev      Check devDependencies.
  -h, --help     Show this help message.
  -v, --verbose  Run in verbose mode
  -V, --version  Outputs version
```

add as git hook
===============

It is a good practice that you add `npm-shrinkwrap-check` as a [git hook](http://git-scm.com/docs/githooks).

To add a `pre-push` hook create a `.git/hooks/pre-push` in your repo with the following:

```sh
#!/bin/sh

npm-shrinkwrap-check
```

This will prevent you from pushing out-of-sync `package.json` and `npm-shrinkwrap.json` files to your repo.

