# Lokiman-Emscripten
Lokiman modified for Emscripten

![](https://i.imgur.com/QZN0Ujj.png)

## To compile with Emscripten
Recommend using docker container for Emscripten: 
https://hub.docker.com/r/robertaboukhalil/emsdk

```docker pull robertaboukhalil/emsdk:1.39.1```

                docker run \
                    -dt \
                    -p 12345:80 \
                    --name wasm \
                    --volume "$(pwd)":/src \
                    robertaboukhalil/emsdk:1.39.1
 
    
 build with
 
 ```wrap
 emcc -Oz cmdline_options.cpp constants.cpp figur.cpp funny_animation.cpp game.cpp gamecontroller.cpp ghost_figur.cpp
 highscore.cpp labyrinth.cpp level.cpp menu.cpp menu_about.cpp menu_item.cpp menu_main.cpp menu_options.cpp pacman.cpp
 pacman_figur.cpp pille.cpp platform.cpp rail.cpp screen.cpp sounds.cpp -o lokiman.html --preload-file
 data/@/usr/local/share/pacman --use-preload-plugins -s USE_SDL=2 -s USE_SDL_IMAGE=2 -s USE_SDL_TTF=2 
 -s USE_SDL_MIXER=2 -s EXIT_RUNTIME=1 -s DISABLE_DEPRECATED_FIND_EVENT_TARGET_BEHAVIOR=1 -s ASYNCIFY -s
 ALLOW_MEMORY_GROWTH=1
 ```
 
 copy
 
        lokiman.html lokiman.js lokiman.wasm lokiman.data
 
 to your webserver dir
 
 ## License ##
Lokiman-Emscritpen is licensed under the terms of the GNU General Public License version 2 (or any later version).
