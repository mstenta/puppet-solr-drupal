# Solr Module for Drupal

This is a puppet module for setting up a multi-core solr instance, for use with [Drupal Apache Solr module](http://drupal.org/project/apachesolr) (version 6.x-3.x or 7.x-1.x).

It uses the solrconfig.xml, schema.xml, and protwords.txt files provided by the [Drupal Apache Solr module](http://drupal.org/project/apachesolr).

This is originally a fork of (http://github.com/vamsee/puppet-solr).

## Quick Start

Put this in your solr.pp file and run sudo puppet apply:

    class { solr:
      cores => [ 'development', 'staging', 'production' ]
    }

**NOTE**: Currently only Ubuntu is supported, contributions for other platforms are most welcome. 
The code is well commented, and should give you a clear idea about how this module 
configures solr. Please read those for more information.

