sdl_sources += files('SDL_process.c')

if host_system == 'windows'
  sdl_sources += files('windows/SDL_windowsprocess.c')
elif host_system == 'linux'
  sdl_sources += files('posix/SDL_posixprocess.c')
else
  sdl_sources += files('dummy/SDL_dummyprocess.c')
endif
