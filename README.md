Mr. Sifter
==========

Mister Sifter is a tool to help sort a home directory.  Each file or directory
is added to a category.  The tool can then be used to feed the list of
important files into a backup program, or set up those files to be
synchronized, or any number of other similar uses.

Later on, the tool can be used to notify the user if more files have appeared
that are not yet categorized.

The categorization is stored in a file with the following syntax:

```
[backup]
.config
.ssh
.vimrc
Documents

[sync]
Desktop

[unimportant]
.local/share/Trash
```

The program works recursively.  If all entries in a directory are handled, that
directory does not need to be categorized.  For example, if you have two
subdirectories of `Documents`, `Documents/important` and
`Documents/unimportant`, you only need to categorize the two subdirectories.
If a new directory appears named `Documents/journal`, it will be flagged as not
yet categorized.

TODO
----

* Let users take file size into consideration, e.g. anything in `Documents`
  that is smaller than 10MB should be added to `backup` automatically, but
  larger files need to be added manually.
