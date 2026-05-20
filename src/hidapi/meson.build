sdl_sources += files('SDL_hidapi.c')

if host_system == 'windows'
  sdl_sources += files(
    'windows/hid.c',
    'windows/hidapi_descriptor_reconstruct.c',
  )
elif host_system == 'linux'
  sdl_sources += files('linux/hid.c')
endif
