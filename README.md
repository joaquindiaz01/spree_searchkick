Spree + Searchkick
===============

Add [Elasticsearch](http://elastic.co) goodies to Spree, powered by [searchkick](http://searchkick.org)

Features
--------

* Full search (keyword, in_taxon)
* Taxons Filters (facets)
* Search Autocomplete ([Typeahead](https://twitter.github.io/typeahead.js/))
* Added `/best` route, where best selling products are boosted in first page


Installation
------------

Add spree_searchkick to your Gemfile:

```ruby
gem 'spree_searchkick'
```

Bundle your dependencies and run the installation generator:

```shell
bundle
bundle exec rails g spree_searchkick:install
```

[Install elasticsearch](https://www.elastic.co/downloads/elasticsearch)

Documentation
-------------

By default, only the `Spree::Product` class is indexed and to control what data is indexed, override `Spree::Product#search_data` method. Call `Spree::Product.reindex` after changing this method.

To enable or disable taxons filters, go to taxonomy form and change `filterable` boolean.

Testing
-------

First bundle your dependencies, then run `rake`. `rake` will default to building the dummy app if it does not exist, then it will run specs. The dummy app can be regenerated by using `rake test_app`.

```shell
bundle
bundle exec rake
```

When testing your applications integration with this extension you may use it's factories.
Simply add this require statement to your spec_helper:

```ruby
require 'spree_searchkick/factories'
```

Copyright (c) 2015 Gonzalo Moreno, released under the New BSD License
