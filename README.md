Heroku buildpack: CasperJS
=======================

This is a [Heroku buildpack](http://devcenter.heroku.com/articles/buildpacks) of [CasperJS](http://casperjs.org) / [PhantomJS](http://phantomjs.org/).

Usage
-----

Example usage:

    $ heroku create --stack cedar --buildpack https://github.com/leesei/heroku-buildpack-casperjs.git

    $ git push heroku master

Alternately, you can cascade with other buildpacks:

    $ heroku create --stack cedar --buildpack https://github.com/ddollar/heroku-buildpack-multi.git

    $ echo https://github.com/leesei/heroku-buildpack-casperjs.git > .buildpacks

    # echo [other buildpack] >> .buildpacks
    # `git add` your files

    $ git push heroku master

You can also login to the herokuapp and execute `phantomjs` and `casperjs`:

    $ heroku run bash
    Running `bash` attached to terminal... up, run.2587
    Add phantomjs/casperjs paths ...
    ~ $ casperjs





