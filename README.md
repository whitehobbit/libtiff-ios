libtiff-ios
===========

Based on original script found at http://pastebin.com/Pgiy3rYJ
and the idea from [Tesseract-OCR-iOS Makefile] (https://github.com/gali8/Tesseract-OCR-iOS/pull/210)

Compile libTIFF, libPNG and JPEG libraries for use on iOS

Creates "fat" binary libraries compatible with arm64, arm64e and x86_64/Simulator

    make            #builds all libraries

You may also build only the library you wish by specifiying the following make targets:

    make libtiff
    make libpng
    make libjpg

By default every "fat" library will contain all architectures specified above. So it can be linked with apps either for devices or simulator. If you don't need all architectures above (for example, for AppStore submittion), just specify the necessary architectures in the `ARCHS` environement variable as follows:

    export ARCHS=arm64, arm64e, x86_64

It's much easier now to update to a any (new or old) versions of library: just change a corresponding version numbers in the beginning of the make file:

    PNG_NAME        = libpng-1.6.34
    JPEG_SRC_NAME   = jpegsrc.v9c# filename at the server
    JPEG_DIR_NAME   = jpeg-9c# folder name after the JPEG_SRC_NAME archive has been unpacked
    TIFF_NAME       = tiff-4.1.0


Location for the XCode version to use is identified using

    xcode-select -p
    
If you have multiple versions installed, you can switch to a different installation using

    xcode-select -s /full_path_to_xcode/
