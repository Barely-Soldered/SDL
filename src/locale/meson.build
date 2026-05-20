sdl_sources += files('SDL_locale.c')

if host_system == 'windows'
  sdl_sources += files('windows/SDL_syslocale.c')
elif host_system == 'linux'
  sdl_sources += files('unix/SDL_syslocale.c')
elif host_system == 'emscripten'
  sdl_sources += files('emscripten/SDL_syslocale.c')
else
  sdl_sources += files('dummy/SDL_syslocale.c')
endif
