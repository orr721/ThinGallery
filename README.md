ThinGallery
===========

Copyright 2016 Gordon Williams, gw@pur3.co.uk (Licensed as MPLv2)

A single-file gallery webpage. This uses EXIF thumbnails, XMLHttpRequest Range headers, 
and your web server's own index pages to quickly display thumbnails for a directory without
having to fully load every image file, and without needing ANY server-side scripting.

Usage
-----

* Put `gallery.html` in the folder that contains your photos. 
* Don't rename it to `index.html` as the web server's own index.html is required in order to list the photos
* Open gallery.html with a web browser, and enjoy

Future Additions
----------------

These are just ideas - if you fancy adding them then pleae have a go and issue a Pull Request!

* Relative paths when folders clicked on
* Better EXIF decoding (the current way is nasty and fails sometimes)
* Read image rotation from EXIF
* Allow Delete + Rotate, and store the data in a cookie. Allow export as a shell script that would use ImageMagick to perform the operations.

