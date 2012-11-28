Install Imagick
---------------
	brew search php53-imagick
	brew install php53-imagick

homebrew will tell you to tap some repos before you can install


Add extension to mamp php.ini
-----------------------------

	vim /Applications/MAMP\ PRO/MAMP\ PRO.app/Contents/Resources/<yourphpversion.ini>

add

	extension="/usr/local/Cellar/php53-imagick/3.1.0RC2/imagick.so"



Copy libfreetype to MAMP lib
----------------------------
	cp /usr/local/Cellar/freetype/2.4.10/lib/libfreetype.6.dylib /Applications/MAMP/Library/lib/


Fix library version incompatibilities
-------------------------------------
	vim /Applications/MAMP/Library/bin/envvars

Comment out the following lines:

	DYLD_LIBRARY_PATH="/Applications/MAMP/Library/lib:$DYLD_LIBRARY_PATH"
	export DYLD_LIBRARY_PATH


Restart MAMP and check phpinfo
------------------------------
You should see the following:

	imagick module	enabled
	imagick module version	3.1.0RC2
	imagick classes	Imagick, ImagickDraw, ImagickPixel, ImagickPixelIterator
	ImageMagick version	ImageMagick 6.7.7-6 2012-09-18 Q16 http://www.imagemagick.org
	ImageMagick copyright	Copyright (C) 1999-2012 ImageMagick Studio LLC
	ImageMagick release date	2012-09-18
	ImageMagick number of supported formats:	191


Note
-----
If you get an error while installing libxml2, verify that you have installed the latest version of Xcode command line tools (Xcode/Preferences/Downloads/Components)
