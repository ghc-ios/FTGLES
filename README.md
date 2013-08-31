A Haskell binding for the portable TrueType to OpenGL font rendering library FTGLES,
which is an iOS port of FTGL. This package is a slight modification by Stephen
Blackheath of J. R. Heard's Haskell binding package, FTGL.
This package provides OpenGL with polygonal, and texture mapped fonts using
Freetype2 and any truetype font.

First, install this Cabal package. The C code doesn't need to exist at this point.

Then build the C/C++ code for FTGLES, like this. Note that you must modify the two
install.sh scripts to compile against whatever iOS SDK version you are using.

    git clone git@github.com:cdave1/ftgles.git
    git clone git@github.com:cdave1/freetype2-ios.git
    cd freetype2-ios/
    bash install.sh
    cd ../ftgles
    ln -s ../freetype2-ios freetype2
    cd Xcode
    bash install.sh
 
Now add these two files to your Xcode project:
 
    freetype2-ios/libFreetype2.a
    FTGLES/Xcode/libFTGLES.a
 
Also these libraries are required to be added in Xcode (because FTGLES is written
in C++):
 
    libc++.dylib
    libstdc++.dylib
