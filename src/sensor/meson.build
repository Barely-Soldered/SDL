sdl_sources += files('SDL_sensor.c')

if host_system == 'windows'
  sdl_sources += files('windows/SDL_windowssensor.c')
elif host_system == 'emscripten'
  sdl_sources += files('emscripten/SDL_emscriptensensor.c')
else
  sdl_sources += files('dummy/SDL_dummysensor.c')
endif
