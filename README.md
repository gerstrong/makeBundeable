# makeBundeable
Small script which modifies your executable and all dependant dylibs in order to create a MacOS portable bundle

This script is used for cross building Commander Genius for MacOS. 

Similar tools are macdylibbundler which ich written in C++ or the Qt Tool Macdeployqt

https://github.com/auriamg/macdylibbundler

## How to use it

The to be modified dylibs are usually taken from MacPorts. Since those use well defined search path and need to be modified, because you don't want users be forced installing mac ports in order to use your software, these dylibs are very good candidates.

    mkdir CGenius.app
    mkdir -p CGenius.app/Contents
    mkdir -p CGenius.app/Contents/libs
    mkdir -p CGenius.app/Contents/MacOS
    mkdir -p CGenius.app/Contents/Resources
   

Now copy some of the files you want to have in your the App directory, most importantly your executable. You don't need to copy the dependant dylibs though. The script takes of it.

Now you need to execute

    bash makebundleable.sh CGenius.app/Contents/MacOS/CGeniusExe

and convert your directory into a bundle (DMG).
