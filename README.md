ThinGallery
===========

https://github.com/gfwilliams/ThinGallery

Copyright 2016 Gordon Williams, gw@pur3.co.uk (Licensed as MPLv2)

A single-file gallery webpage. This uses EXIF thumbnails, XMLHttpRequest Range headers, 
and your web server's own index pages to quickly display thumbnails for a directory without
having to fully load every image file, and without needing ANY server-side scripting.

[See it in action!](http://www.pur3.co.uk/gallery)
----------------------------------

![Original Index Page](screenshots/index.png)
![Gallery list](screenshots/gallery1.png)
![Gallery image](screenshots/gallery2.png)

Why?
----

* You may have access to a web server, but no ability to upload/execute scripts on it
* You may not want to execute scripts on your server for security reasons
* **You might have a NAS Box** - this may not support common server-side 
languages like PHP, and even if it does, it may be too slow to resize your images.

Setup
-----

* Put `gallery.html` in the folder that contains your photos. 
* Don't rename it to `index.html` as the web server's own index page is required in order to list the photos
* Open gallery.html with a web browser, and enjoy.

Usage
-----

* Click on an image to open it
* The thumbnail will be shown enlarged first (with an hourglass over it). When the full-size image is loaded it'll replace the thumbnail.
* Use the left and right arrows (on screen or keyboard) to move between photos
* Click the arrow in the bottom right to load the image in its own tab
* Click the image, background, or scroll to close the opened image

How it works
------------

When there's no `index.*` page, the web server creates its own HTML listing of files, and
the gallery loads this and scans it in order to find out what images are available.

For each JPEG image, it requests *just the first 30,000 bytes*, which should contain the
image's thumbnail if it had one. If it's there, it is used - otherwise the entire image
is loaded (once all the other thumbnails have been scanned).

This means that in a directory of photos from a digital camera, instead of loading each
~5MB image file (and using up all your bandwidth and RAM), the gallery is only loading 
one 250th of the amount of data, making it much faster to browse your files.

Future Additions
----------------

These are just ideas - if you fancy adding them then please have a go and issue a Pull Request!

* Find some Unicode that actually works nicely on all platforms
* Relative paths when folders clicked on
* Read image rotation from EXIF
* Allow Delete + Rotate, and store the data in a cookie. Allow export as a shell script that would use ImageMagick to perform the operations.

