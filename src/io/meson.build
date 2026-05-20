sdl_sources += files(
  'SDL_asyncio.c',
  'SDL_iostream.c',
  'generic/SDL_asyncio_generic.c',
)

if host_system == 'linux'
  sdl_sources += files('io_uring/SDL_asyncio_liburing.c')
elif host_system == 'windows'
  sdl_sources += files('windows/SDL_asyncio_windows_ioring.c')
endif
