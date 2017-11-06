# WOFF

WOFF is a compressed format for putting fonts on web pages. While
browsers can support True Type font files (.ttf suffix), WOFF files
are smaller and are compatible with all modern browsers (e.g. Internet
Explorer has had WOFF support since IE9 from 2011, Firefox has supported
WOFF files since 2009, etc.).

## This repo

This is a mirror of http://people.mozilla.org/~jkew/woff/ so that
the open-source reference code remains available and is not put
behind a paywall.

To compile and install, make sure you have the zlib development libraries
installed (e.g. in CentOS6 `yum -y install zlib-devel` as root), then

    git clone https://github.com/samboy/WOFF
    cd WOFF
    make

Then, as root:

    cp sfnt2woff /usr/local/bin

Once this is done, to make a webfont, enter the directory with the .ttf
file, then run sfnt2woff

    sfnt2woff Chortle2014f.ttf

This creates a Chortle2014f.woff webfont file. Replace
“Chortle2014f.ttf” with the name of the actual webfont to convert.

http://people.mozilla.org/~jkew/woff/ has Windows and MacOS binaries
for people who do not wish to install a compiler.

## Zopfli compression

Zopfli compression can make WOFF files with a better compression
ratio:

https://github.com/bramstein/sfnt2woff-zopfli

## WOFF2

Here is the reference code for making WOFF2 files: 

https://github.com/google/woff2 

Note that this code will _not_ install in CentOS6, but compiles and
installs just fine in CentOS7:

    git clone --recursive https://github.com/google/woff2.git
    cd woff2
    make clean all

woff2 font generation is similar:

    woff2_compress Chortle2014f.ttf

## EOT

Keep in mind that EOT is an obsolete format; any browser which supports
EOT but _does not_ support WOFF (Read: Internet Explorer 6-8) is a browser 
which is unsupported.

That in mind, the best EOT converter for Windows can be downloaded at
http://eotfast.com ; there are a couple of cross platform EOT converters
including the one at https://www.w3.org/Tools/eot-utils/

