# Delete All
 
This module is used to bulk delete content and/or users from a site.
This is mainly a developer tool, which can come in handy in several cases, 
listed below.

The usual way to do this is to go to Administer -> Content then select all the
nodes and delete them. This works if you have a handful of nodes only. If you
have hundreds or thousands of nodes, then it is not a practical solution.

Another option is to directly delete the nodes from the node table in
the database. This does not work properly, since there are also comments,
and many tables for add on modules that need to be cleaned.

Some sample use cases:

 - This is a test site that the client was using for a period of time, and they
must clean it up before starting with real data.
 - You are testing something that creates a lot of nodes (e.g. aggregator), and
want to do it over and over again.
 - You created a site in the past and want to replicate it again,
but with new content.

Note that for content, comments and all additions to content that contributed
modules may have added. For users, any additional module data
will also be deleted.

## Installation

- Install this module using the official 
  [Backdrop CMS instructions](https://backdropcms.org/guide/modules)

## Usage

In order to use this module, install it it and enable it as with any other
module. You will then see two new entries, one under Administer -> Content,
and the other under Administer -> Users. A confirmation message will be
displayed before the actual deletion happens.

When deleting nodes, you can select to delete all nodes, or just delete
nodes by type.

There are also two methods for deleting nodes. The "normal" method uses
node_delete, and is the preferred way of doing things. But if your site has
hundreds or thousands of nodes, node_delete can take quite long. The "quick"
method is for these cases when there are thousands of nodes. It deletes
everything using SQL by joining the tables. Since it deletes thousands of
nodes at a time in a single sql statement and bypasses lots of php and the
module's hook_delete, it's much quicker. But it's not as safe a way of
deleting as using the "normal" method.

There is some Drush integration as well (see the Wiki).


## Documentation

Additional documentation is located in the [Wiki](https://github.com/backdrop-contrib/delete_all/wiki)

## Issues

Bugs and Feature requests should be reported in the [Issue Queue](https://github.com/backdrop-contrib/delete_all/issues)

## Current Maintainers

- [Laryn Kragt Bakker](https://github.com/laryn) - [CEDC.org](https://cedc.org)

## Credits

- Ported to Backdrop CMS by [Laryn Kragt Bakker](https://github.com/laryn) - [CEDC.org](https://cedc.org).
- Drupal Maintainers: 
  [Dipak Yadav](https://www.drupal.org/u/dipakmdhrm), 
  [Hammad Ghani](https://www.drupal.org/u/hammad-ghani), 
  [Khalid Baheyeldin](https://www.drupal.org/u/kbahey), 
  [Brian Gilbert](https://www.drupal.org/u/realityloop), 
  [Kevin O'Brien](https://www.drupal.org/u/coderintherye), 
  [Doug Green](https://www.drupal.org/u/douggreen)

## License

This project is GPL v2 software. See the LICENSE.txt file in this directory for
complete text.
