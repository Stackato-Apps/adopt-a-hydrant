# Adopt-a-Hydrant

[![Build Status](http://img.shields.io/travis/codeforamerica/adopt-a-hydrant.svg)][travis]
[![Dependency Status](http://img.shields.io/gemnasium/codeforamerica/adopt-a-hydrant.svg)][gemnasium]
[![Coverage Status](http://img.shields.io/coveralls/codeforamerica/adopt-a-hydrant.svg)][coveralls]

[travis]: http://travis-ci.org/codeforamerica/adopt-a-hydrant
[gemnasium]: https://gemnasium.com/codeforamerica/adopt-a-hydrant
[coveralls]: https://coveralls.io/r/codeforamerica/adopt-a-hydrant

Claim responsibility for shoveling out a fire hydrant after it snows.

## Screenshot
![Adopt-a-Hydrant](https://github.com/codeforamerica/adopt-a-hydrant/raw/master/screenshot.png "Adopt-a-Hydrant")

## Demo
You can see a running version of the application at
[http://adopt-a-hydrant.herokuapp.com/][demo].

[demo]: http://adopt-a-hydrant.herokuapp.com/

## Deploying to Stackato
1. Create config/production_secret.yml (production_secret_sample.yml may be used as reference)

2. Generate a new secret token:
    ```
    rake secret
    ```

3. Copy the token generated into the secret_key_base field 

4. From the command line run:
    ```
    stackato push -n
    stackato run bundle exec rake db:migrate
    stackato run bundle exec rake db:seed
    ```

## Installation
This application requires [Postgres](http://www.postgresql.org/) to be installed

    git clone git://github.com/codeforamerica/adopt-a-hydrant.git
    cd adopt-a-hydrant
    bundle install

    bundle exec rake db:create
    bundle exec rake db:schema:load

## Usage
    rails server

## Seed Data
    bundle exec rake db:seed

### Google Analytics
If you have a Google Analytics account you want to use to track visits to your
deployment of this app, just set your ID and your domain name as environment
variables in stackato.yml:

    env:
      GOOGLE_ANALYTICS_ID: your_id
      GOOGLE_ANALYTICS_DOMAIN: your_domain_name

An example ID is `UA-12345678-9`, and an example domain is `adoptahydrant.org`.

## Contributing
In the spirit of [free software][free-sw], **everyone** is encouraged to help
improve this project.

[free-sw]: http://www.fsf.org/licensing/essays/free-sw.html

Here are some ways *you* can contribute:

* by using alpha, beta, and prerelease versions
* by reporting bugs
* by suggesting new features
* by [translating to a new language][locales]
* by writing or editing documentation
* by writing specifications
* by writing code (**no patch is too small**: fix typos, add comments, clean up
  inconsistent whitespace)
* by refactoring code
* by closing [issues][]
* by reviewing patches
* [financially][]

[locales]: https://github.com/codeforamerica/adopt-a-hydrant/tree/master/config/locales
[issues]: https://github.com/codeforamerica/adopt-a-hydrant/issues
[financially]: https://secure.codeforamerica.org/page/contribute

## Submitting an Issue
We use the [GitHub issue tracker][issues] to track bugs and features. Before
submitting a bug report or feature request, check to make sure it hasn't
already been submitted. When submitting a bug report, please include a [Gist][]
that includes a stack trace and any details that may be necessary to reproduce
the bug, including your gem version, Ruby version, and operating system.
Ideally, a bug report should include a pull request with failing specs.

[gist]: https://gist.github.com/

## Submitting a Pull Request
1. [Fork the repository.][fork]
2. [Create a topic branch.][branch]
3. Add specs for your unimplemented feature or bug fix.
4. Run `bundle exec rake test`. If your specs pass, return to step 3.
5. Implement your feature or bug fix.
6. Run `bundle exec rake test`. If your specs fail, return to step 5.
7. Run `open coverage/index.html`. If your changes are not completely covered
   by your tests, return to step 3.
8. Add, commit, and push your changes.
9. [Submit a pull request.][pr]

[fork]: http://help.github.com/fork-a-repo/
[branch]: http://learn.github.com/p/branching.html
[pr]: http://help.github.com/send-pull-requests/

## Supported Ruby Version
This library aims to support and is [tested against][travis] Ruby version 2.1.0.

If something doesn't work on this version, it should be considered a bug.

This library may inadvertently work (or seem to work) on other Ruby
implementations, however support will only be provided for the version above.

If you would like this library to support another Ruby version, you may
volunteer to be a maintainer. Being a maintainer entails making sure all tests
run and pass on that implementation. When something breaks on your
implementation, you will be personally responsible for providing patches in a
timely fashion. If critical issues for a particular implementation exist at the
time of a major release, support for that Ruby version may be dropped.

## Copyright
Copyright (c) 2014 Code for America. See [LICENSE][] for details.

[license]: https://github.com/codeforamerica/adopt-a-hydrant/blob/master/LICENSE.md

[![Code for America Tracker](http://stats.codeforamerica.org/codeforamerica/adopt-a-hydrant.png)][tracker]

[tracker]: http://stats.codeforamerica.org/projects/adopt-a-hydrant
