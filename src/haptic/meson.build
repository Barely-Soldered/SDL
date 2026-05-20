sdl_sources += files('SDL_haptic.c')

if host_system == 'windows'
  sdl_sources += files(
    'windows/SDL_dinputhaptic.c',
    'windows/SDL_windowshaptic.c',
    'hidapi/SDL_hidapihaptic.c',
    'hidapi/SDL_hidapihaptic_lg4ff.c',
  )
elif host_system == 'linux'
  sdl_sources += files(
    'linux/SDL_syshaptic.c',
    'hidapi/SDL_hidapihaptic.c',
    'hidapi/SDL_hidapihaptic_lg4ff.c',
  )
else
  sdl_sources += files('dummy/SDL_syshaptic.c')
endif
