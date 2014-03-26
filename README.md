========
Build/Run Doomsday Engine For Windows 7
========

##Requirements
* Visual Studio 2012
* 32bit qt-win-opensource-4.8.5-vs2010
* source doomsday engine stable 1.13 [LINK](https://github.com/skyjake/Doomsday-Engine/tree/stable-1.13)
* binaries doomsday engine [LINK](http://dengine.net/windows)
* SDL_mixer-1.2.11
* SDL-devel-1.2.14-VC8
* WADs of Doom, Doom2, Hexen, Heretic (You need atleast one. You can buy the game's to get the WADs).

##Requirements Explained

  VS2012 is what I used to build the SDL_Mixer source.

  We will be building with qt. The very nice people on the forums informed me of the correct version to use, and it indeed works great for me. If you use a newer version than this, I can't gurantee it will work. Also, it's super important that you are using 32bit. 64bit qt will give you cryptic errors.
  
  You'll need the source because that's what we're trying to build. Get stable 1.13 so things will be sure to work.
  
  Get and install the binaries/exe for the doomsday engine so that you can make running a snap. Basically, with this we get the full and proper directory structure that the program will need. We'll also get the .dlls. Note that we'll be building in RELEASE and not DEBUG. I haven't gotten DEBUG builds to run. So since we're building RELEASE, we can use the non-debug .dlls from the installation. Once again, I'm not saying a DEBUG compile won't work, I'm saying it hasn't worked for me yet.
  
  SDL_Mixer is something I had to build myself from source. Google up the version I note above, then you'll build it as described below.
  
  Finally, the WADs contain the actual game data and assets. It's vital. The WADs are basically the damn games. Buy the games to get the WADs or w/e, just get them.
  
  
##Build Steps

1. Know that there are official instructions on the project wiki [LINK](http://dengine.net/dew/index.php?title=Compilation)
2. Install QT.
3. Install Doomsday Engine.
4. Grab the source and store it somewhere good. Ex: "D:/dont_move/my_doom/code".
5. Unzip the SDL_Mixer and build it. You'll go to the "VisualC" folder and open the .sln.
6. Once the project is open in VS2012, you'll eventually notice that the project is borked and none of the files actually reference the files in the folders.
  * You will need to manually remove each "can't find" file from the projects and re-add them manually with a drag-drop.
7. The RELEASE build should now work. The output should be in the "VisualC/Release" folder.
8. Doomsday will expect each resource to be in some folder that itself has an "include" and "lib" folder, containing the include files (.h) and libs and dlls respectively.
  * So, for example, I created a folder "D:/dont_move/my_doom/code/requirements".
  * In this folder, I have a folder "SDL_MIXER", with "SDL_MIXER/include" and "SDL_MIXER/lib".
  * You don't have to do this exactly, but this does work for me.
9. Enter the source code you stored and go to (your path may be a bit different): "Doomsday-Engine-stable-1.13\Doomsday-Engine-stable-1.13\doomsday"
10. Copy "config_user-example.pri" and paste it as "config_user.pri"
11. Open "config_user.pri", notice that you'll need to supply the paths to certain resources on your machine.
  * These are my personal paths, they may or may not apply to your machine, but they offer good examples.
  * My direct_x: DIRECTX_DIR = "C:/Program Files (x86)/Microsoft DirectX SDK (June 2010)"
  * My sdl: SDL_DIR = "V:/dont_move/doom/code/requirements/SDL"
  * My sdl_mixer: SDL_MIXER_DIR = "V:/dont_move/doom/code/requirements/SDL_MIXER"
12. Add the following to the bottom of the "config_user.pri" file. This will disable some ancient/crusty resources we don't (I don't) want to use.
```
# Don't use OpenAL. Don't use EAX. They are old and non-existent lol.
CONFIG += deng_noopenal
CONFIG += deng_nodirectsound
```
13. In this "doomsday" folder, open the "doomsday.pro".
