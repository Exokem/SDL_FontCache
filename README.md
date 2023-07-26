# SDL_FontCache
A generic font caching C library with loading and rendering support for SDL.

# Installation
1. Clone the repository.
2. Download SDL2 (SDL2-devel-X.Y.Z-VC.zip) [https://github.com/libsdl-org/SDL/releases]
3. Download SDL2_ttf (SDL2_ttf-devel-X.Y.Z-VC.zip) [https://github.com/libsdl-org/SDL_ttf/releases]
4. Extract SDL2 and SDL2_ttf to the same directory, and that directory to your CMAKE_PREFIX_PATH environment variable

An example file structure for the SDL libraries: 

```
Libraries
  ├─ SDL2
  │    ├─ cmake
  │    ├─ include
  │    └─ lib
  └─ SDL2_ttf
       ├─ cmake
       ├─ include
       └─ lib
```


# Features

SDL_FontCache loads, caches, and renders TrueType fonts using SDL_ttf.  
It fully supports UTF-8 strings and includes some utility functions for manipulating them.

This fork is configured for exporting the library to native windows DLLs.

An example using SDL_Renderer:

```
FC_Font* font = FC_CreateFont();  
FC_LoadFont(font, renderer, "fonts/FreeSans.ttf", 20, FC_MakeColor(0,0,0,255), TTF_STYLE_NORMAL);  

...

FC_Draw(font, renderer, 0, 0, "This is %s.\n It works.", "example text"); 
 
...

FC_FreeFont(font);
```
