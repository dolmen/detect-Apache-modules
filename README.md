

Use case
========

You have an account at a shared *A** (eg. LAMP) hosting provider.
You want to know which Apache modules are available so you can use them in
a .htaccess.

If the host has `mod_php` you could simply use the `apache_get_modules`
function.

If not (no PHP, or PHP as CGI), use *`detect-Apache-modules`*.
detect-Apache-modules makes use of some core Apache configuration available
in .htaccess to report which modules are available.

Usage
=====

Edit .htaccess to replace:
  - 'http://my-host/apache-modules' with the target base URL
  - '/apache-modules' with the target URL path

Put those files in a directory on the target host:
  - .htaccess
  - list.json
  - list.xhtml
  - ok.txt
  - jquery*.min.js

Open list.html remotely. You'll get the result in your browser.


Updating the probed modules
===========================

The list of modules which are probed is static.

This list is in two files which must be in sync
  - .htaccess
  - list.json
If they are not in sync, some modules may be incorrectly reported as not
installed, or not reported at all.

To add more modules to the list you can manually modify the files or 
use setup.php to add modules from an existing host.

Using setup.php
---------------

Requirements:
  - a host which has PHP running with `mod_php`
  - `list.json` and `.htaccess` writeable by Apache

Load setup.php from a web browser remotely. The `list.json` will be read,
combined with the local list of installed Apache modules and both `list.json`
and `.htaccess` files will be updated.


Copyright and license
=====================

Copyright 2011 Olivier Mengué

License: Apache License, version 2.0

See LICENSE.txt or http://www.apache.org/licenses/LICENSE-2.0.html
