# Heroku buildpack: CasperJS

This is a [Heroku buildpack](http://devcenter.heroku.com/articles/buildpacks) of [CasperJS](http://casperjs.org) / [PhantomJS](http://phantomjs.org/).

**Note**: this buildpack only installs the `phantomjs` and `casperjs` binaries.

## Usage

Example usage:

```bash
$ heroku create --stack cedar --buildpack https://github.com/leesei/heroku-buildpack-casperjs.git

$ git push heroku master
```

You can now login to the herokuapp and execute `phantomjs` and `casperjs`:

```bash
$ heroku run bash
Running `bash` attached to terminal... up, run.2587
Add phantomjs/casperjs paths ...

$ phantomjs --version
1.9.2

$ casperjs --version
1.1.0-DEV
```

---

Alternately, you can cascade with other buildpacks with [buildpack-multi](https://github.com/ddollar/heroku-buildpack-multi). 
`buildpack-casperjs` plays well with cascading since this buildpack uses `profile.d/casperjs.sh` to add to PATH.

```bash
$ heroku create --stack cedar --buildpack https://github.com/ddollar/heroku-buildpack-multi.git

$ echo https://github.com/leesei/heroku-buildpack-casperjs.git > .buildpacks

# echo [other buildpack] >> .buildpacks
# `git add` your files

$ git push heroku master
```

Example: [leesei/heroku-casper-node](https://github.com/leesei/heroku-casper-node)

You can replace Node with other language of your choice.
