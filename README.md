repeats
=======

This is a jiffy little python script that takes a base path as its argument and prints the paths of identical files to stdout, separated by `:`.

How it works
------------

The script calculates the MD5 checksums of all the files of the same size underneath the base path I use as my argument. If these MD5s match, the path is printed.

How to use it
-------------
#### List identical pictures in my album.
    $ ./repeats ~/Dropbox/Chris/album/
    ~/Dropbox/Chris/album/_import/IMG_0034.JPG:~/Dropbox/Chris/album/my-trip/IMG_0034.JPG

#### Delete identical pictures in my album _import directory.
    $ ./repeats ~/Dropbox/Chris/album/ | cut -d : -f 1 | grep '\/_import\/' | xargs rm

#### How to install it
You probably just want to symlink it into a directory in your PATH.

    $ git clone <repo>
    $ ln -s /path/to/my/repos/repeats/repeats ~/bin/repeats
