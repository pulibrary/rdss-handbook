# Not a Rails Template
We have noted that any template that is kept in code needs to be maintained, but are generally not.  Therefore instead of maintaining a template we are going to utilize another method of pointing to existing code repos for our current understanding of best practices.

**As you utilize this documentation please update it with the latest information**

## Generate a basic Rails Application
You will want to generate your new application using `rails new`  For ORCID@Princeton we utilized [this tutorial for integrating vite with rails](https://davidteren.medium.com/ruby-on-rails-7-high-performance-frontend-with-esbuild-rollup-vite-7712dea1917e). The tutorial suggest utilizing tailwind as your javascript framework, but after trying it we decided against it and just went [with bootstrap](https://github.com/pulibrary/orcid_princeton/commit/7493a6878404075d36fb3d8fc96c9c475dca08ec).

## Add in rspec
We utilize rspec instead of minitest so remove minitest and add rspec.  Here is an [example of this on ORCID@princeton](https://github.com/pulibrary/orcid_princeton/commit/720fab085e61ec77489934fc9865672f70b43ebf)

## Add in Lando
We utilize lando (which is a layer above docker) for running dependencies like the database and solr.  Here is an example of a lando [config file for just a database](https://github.com/pulibrary/orcid_princeton/blob/main/.lando.yml) and [one that has solr](https://github.com/pulibrary/pdc_discovery/blob/main/.lando.yml)

We utilize a [rake task for starting the servers](https://github.com/pulibrary/orcid_princeton/commit/50e74125a52ad0a7a7219d1acc1ec391f41c2ad6#diff-c6fe42b5f9614cf05591f282523db8002858f18e90349760f50ed3b0303a2c68) and a [script to set the lando information](https://github.com/pulibrary/orcid_princeton/commit/50e74125a52ad0a7a7219d1acc1ec391f41c2ad6#diff-2d2dd957f4d74355374600c9e2738f66c024f609c0855180d162ba65590a0934) in the Rails environment

## Add in Simplecov
We utilize simplecov to check that our code remains covered as we develop it.  Here is a [rake task](
https://github.com/pulibrary/orcid_princeton/commit/50e74125a52ad0a7a7219d1acc1ec391f41c2ad6#diff-c3a6181c08ba1edc2c44b32cb94ae52930e0d67c1c936999ba439339ea17cfec) to check our coverage.

## Add in Rubocop
We utilize rubocop and bixby (from the samvera community) to make sure our code looks consistant.  Add in the [bixby gem](https://github.com/samvera/bixby) and create an [initial rubocop install](https://github.com/rubocop/rubocop#installation).  Here is an [example rubocop configuration file](https://github.com/pulibrary/orcid_princeton/commit/50e74125a52ad0a7a7219d1acc1ec391f41c2ad6#diff-4f894049af3375c2bd4e608f546f8d4a0eed95464efcdea850993200db9fef5c) from OCID@Pricneton

## Add in eslint
We utilize eslint to make sure our javascript looks consistent. Here is an example [eslint configuration file](https://github.com/pulibrary/orcid_princeton/commit/50e74125a52ad0a7a7219d1acc1ec391f41c2ad6#diff-3894e4104cda190617684d0dc5d55e39e49c63cc6955edf4a446b91ae086bbd2) from OCRID@Princeton  

We generally start with the [airbnb base and a few other packages](https://github.com/pulibrary/orcid_princeton/commit/50e74125a52ad0a7a7219d1acc1ec391f41c2ad6#diff-7ae45ad102eab3b6d7e7896acd08c427a9b25b346470d7bc6507b6481575d519R15-R21) installed with yarn.

## Add in Circle CI
We utilize circle ci for continuos integration.  [Here is a tutorial](https://circleci.com/blog/setting-up-continuous-integration-with-github/) for implementing continuos integration. And here is the [config file](https://github.com/pulibrary/orcid_princeton/blob/50e74125a52ad0a7a7219d1acc1ec391f41c2ad6/.circleci/config.yml) from OCID@Princeton.  Note the coverage is initially set to zero on line 112!

## Add in Capistrano 
We utilize capistrano to deploy to the production and staging servers.  Here is [an example commit for adding](https://github.com/pulibrary/orcid_princeton/commit/1faa1a753da9dcf93aec988ffe198456bf9e9139) in capistrano to ORCID@princeton which was created following the [install instructions here](https://github.com/capistrano/rails#installation)

## Add in Vite

If you followed the instructions for a new rails application from the vite tutorial you should already have vite install.

[Make sure you remove sprockets](https://github.com/pulibrary/orcid_princeton/commit/50e74125a52ad0a7a7219d1acc1ec391f41c2ad6#diff-d09ea66f8227784ff4393d88a19836f321c915ae10031d16c93d67e6283ab55fL8-L9) so that vite is handling all your assets.



