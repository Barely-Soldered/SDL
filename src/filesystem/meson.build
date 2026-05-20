sdl_sources += files('SDL_filesystem.c')

if host_system == 'windows'
  sdl_sources += files(
    'windows/SDL_sysfilesystem.c',
    'windows/SDL_sysfsops.c',
  )
elif host_system == 'linux'
  sdl_sources += files(
    'unix/SDL_sysfilesystem.c',
    'posix/SDL_sysfsops.c',
  )
elif host_system == 'emscripten'
  sdl_sources += files(
    'emscripten/SDL_sysfilesystem.c',
    'posix/SDL_sysfsops.c',
  )
endif
