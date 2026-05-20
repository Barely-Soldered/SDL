sdl_sources += files('SDL_time.c')

if host_system == 'windows'
  sdl_sources += files('windows/SDL_systime.c')
else
  sdl_sources += files('unix/SDL_systime.c')
endif
