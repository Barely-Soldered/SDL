sdl_sources += files('SDL_timer.c')

if host_system == 'windows'
  sdl_sources += files('windows/SDL_systimer.c')
else
  sdl_sources += files('unix/SDL_systimer.c')
endif
