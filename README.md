========
Build/Run Doomsday Engine For Windows 7
========

##Requirements
* 32bit qt-win-opensource-4.8.5-vs2010
* source doomsday engine stable 1.13 [LINK](https://github.com/skyjake/Doomsday-Engine/tree/stable-1.13)
* binaries doomsday engine [LINK](http://dengine.net/windows)
* WADs of Doom, Doom2, Hexen, Heretic (You need atleast one. You can buy the game's to get the WADs).
* 

##Requirements Explained

  We will be building with qt. The very nice people on the forums informed me of the correct version to use, and it indeed works great for me. If you use a newer version than this, I can't gurantee it will work. Also, it's super important that you are using 32bit. 64bit qt will give you cryptic errors.
  
  You'll need the source because that's what we're trying to build. Get stable 1.13 so things will be sure to work.
  
  Get and install the binaries/exe for the doomsday engine so that you can make running a snap. Basically, with this we get the full and proper directory structure that the program will need. We'll also get the .dlls. Note that we'll be building in RELEASE and not DEBUG. I haven't gotten DEBUG builds to run. So since we're building RELEASE, we can use the non-debug .dlls from the installation.
  
  Finally, the WADs contain the actual game data and assets. It's vital. The WADs are basically the damn games. Buy the games to get the WADs or w/e, just get them.
  
  
##Build Steps

1. Know that there are official instructions on the project wiki [LINK](http://dengine.net/dew/index.php?title=Compilation)
