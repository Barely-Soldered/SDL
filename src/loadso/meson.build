if host_system == 'windows'
  sdl_sources += files('windows/SDL_sysloadso.c')
elif host_system == 'linux'
  sdl_sources += files('dlopen/SDL_sysloadso.c')
elif host_system == 'emscripten'
  sdl_sources += files('dummy/SDL_sysloadso.c')
endif
