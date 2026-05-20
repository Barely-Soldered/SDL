sdl_sources += files('SDL_url.c')

if host_system == 'windows'
  sdl_sources += files('windows/SDL_sysurl.c')
elif host_system == 'linux'
  sdl_sources += files('unix/SDL_sysurl.c')
elif host_system == 'emscripten'
  sdl_sources += files('emscripten/SDL_sysurl.c')
else
  sdl_sources += files('dummy/SDL_sysurl.c')
endif
