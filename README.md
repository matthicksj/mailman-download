mailman-download
================

This script downloads all the archives for a set of mailing lists so
that you can maintain a local, searchable copy in a mail program like
Thunderbird.  The entire date range supplied will be combined into
a single archive file.

The configuration is driven from a simple YAML file that specifies your
mailman server as well as the lists and authentication (if needed) to
use.  

The config file defaults to ~/lists.yaml and can be overridden as
needed.

The working directory defaults to ~/mail-archives where all the archives 
downloaded are kept for the application to keep track of what was already
downoladed avoiding email duplication. If you need to redownload some archives
simply delete the files from this directory.

The script should be safely re-runnable and will download incremental
updates, only rebuilding the archive files if necessary.

First run
===========

Be sure you have ruby installed

    which ruby

Copy the lists.yaml file in your home dir

    cp lists.yaml ~/

Edit it accordingly to the mailing-lists you want to download

Run the download script with the "--verbose" parameter

    ./mailman-download --verbose

Thunderbird
===========

This script has only been tested on Thunderbird, inspired by the
following blog post -
http://johnpoelstra.com/importing-mailing-list-archives-to-thunderbird/

After running this script, you will need to restart Thunderbird
and the archives will show up under your local folders.

Enjoy!
