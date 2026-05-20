sdl_sources += files(
  'SDL_runapp.c',
)

if host_system == 'windows'
  sdl_sources += files(
    'windows/SDL_sysmain_runapp.c',
    'generic/SDL_sysmain_callbacks.c',
  )
elif host_system == 'emscripten'
  sdl_sources += files(
    'emscripten/SDL_sysmain_runapp.c',
    'emscripten/SDL_sysmain_callbacks.c',
  )
else
  sdl_sources += files('generic/SDL_sysmain_callbacks.c')
endif

sdl_sources += files('SDL_main_callbacks.c')
