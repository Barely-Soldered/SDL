sdl_sources += files('SDL_power.c')

if host_system == 'windows'
  sdl_sources += files('windows/SDL_syspower.c')
elif host_system == 'linux'
  sdl_sources += files('linux/SDL_syspower.c')
elif host_system == 'emscripten'
  sdl_sources += files('emscripten/SDL_syspower.c')
endif
