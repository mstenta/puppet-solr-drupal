# Solr Module for Drupal

(This is a fork of [vamsee/puppet-solr](http://github.com/vamsee/puppet-solr),
which adds Drupal-specific configuration from the
[Drupal Apachesolr module](http://drupal.org/project/apachesolr).)

This is a puppet module for setting up a multi-core solr instance.

## Quick Start

Put this in your site.pp file and run sudo puppet apply:

    include solr

If you need multiple cores out of the box, you can run this:

    class { solr:
      cores => [ 'development', 'staging', 'production' ]
    }

It's _**highly**_ recommended that you use a mirror like so:

    class { 'solr':
      mirror        => 'http://apache.bytenet.in/lucene/solr',
      version       => '4.10.4',
      cores         => ['development', 'staging', 'production'],
    }

**NOTE**: Currently only Ubuntu is supported, contributions for other platforms are most welcome.
The code is well commented, and should give you a clear idea about how this module configures solr.

## Running the tests

The module is developed through Vagrant (http://www.vagrantup.com) for easy testability. You can also
use this to quickly test the module for yourself. Just cd into the directory and run:

    vagrant up

The jetty server maps to port 8983 by default, and vagrant maps this to port 8983 on host system also.
So you should be able to see the solr server running at http://localhost:8983/solr. This module also has
a good test suite, you can run the specs by simply typing:

    rake

If you want to run the system specs (slower, uses vagrant with serverspec) you can do the following:

    rake spec:system

If you want to run them all together, use this:

    rake spec:all

## TODO

 * Support other platforms

##License

MIT. Please see the LICENSE file for more information.

## Contact

Contributions, especially making this multiplatform are most welcome.

## Support

Please log tickets and issues in the issues page (https://github.com/vamsee/puppet-solr/issues)
