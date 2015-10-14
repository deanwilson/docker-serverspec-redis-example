Docker/Server Testing Example
=============================

This repo is a simple example of using serverspec to test the creation and
running state of a docker container.

## Run the tests ##

To run the tests

    $ cd docker-serverspec-redis-example

    $ bundle install
    $ bundle exec rspec spec/Dockerfile_spec.rb

    Dockerfile
      Dockerfile#config
        should expose the redis port
      File "/etc/centos-release"
        should be file
      Package "redis"
        should be installed
      Dockerfile#running
        round trip a key
          should be able to write and read a key
        Command "redis-cli info"
          stdout
            should match /redis_version:/

    Finished in 1.12 seconds (files took 0.31127 seconds to load)
    5 examples, 0 failures
