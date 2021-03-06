# kitchen-salt
[![Gem Version](https://badge.fury.io/rb/kitchen-salt.svg)](http://badge.fury.io/rb/kitchen-salt)
[![Gem Downloads](http://ruby-gem-downloads-badge.herokuapp.com/kitchen-salt?type=total&color=brightgreen)](https://rubygems.org/gems/kitchen-salt)
[![Build Status](https://travis-ci.org/saltstack/kitchen-salt.png)](https://travis-ci.org/saltstack/kitchen-salt)
[![Build Status](https://drone.gtmanfred.com/api/badges/saltstack/kitchen-salt/status.svg)](https://drone.gtmanfred.com/saltstack/kitchen-salt)

A Test Kitchen Provisioner for Salt

The provider works by generating a salt-minion config, creating pillars based on attributes in .kitchen.yml & calling salt-call.

This provider has been tested against the Ubuntu boxes running in vagrant/virtualbox & vagrant-lxc boxes on Ubuntu.

## Installation & Setup
You'll need the test-kitchen & kitchen-salt gem's installed in your system, along with kitchen-vagrant or some other suitable driver for test-kitchen.  Please see the [INTRODUCTION](INTRODUCTION.md).

## Provisioner Options
More details on all the configuration optins are in [provisioner_options.md](provisioner_options.md)

## Requirements
You'll need a driver box that is supported by both the SaltStack [bootstrap](https://github.com/saltstack/salt-bootstrap) system & the Chef Omnibus installer (the Chef Omnibus installer is only needed to provide busser with a useable ruby environment, you can tell busser to use an alternative ruby if your box has suitable ruby support built in).

## Continuous Integration & Testing
PR's and other changes should validated using Travis-CI and the test-kitchen branch of [beaver-formula](https://github.com/simonmcc/beaver-formula/blob/test-kitchen/.kitchen.yml), this uses the kitchen-ec2 driver, the version of kitchen-salt under review & the latest release of test-kitchen.

* http://oj.io/ci/aws-credentials-and-travis-ci/

TODO: Guide on running the tests locally with test-kitchen, vagrant & virtualbox.

TODO: Guide on running the tests locally with test-kitchen & kitchen-ec2.


## Releasing

    # hack. work. test.
    git add stuff
    git commit -v
    gem bump --release --tag
