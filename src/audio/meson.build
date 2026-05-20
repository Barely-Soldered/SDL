sdl_sources += files(
  'SDL_audio.c',
  'SDL_audiocvt.c',
  'SDL_audiodev.c',
  'SDL_audioqueue.c',
  'SDL_audioresample.c',
  'SDL_audiotypecvt.c',
  'SDL_mixer.c',
  'SDL_wave.c',
  'dummy/SDL_dummyaudio.c',
)

if host_system == 'windows'
  sdl_sources += files('wasapi/SDL_wasapi.c')
elif host_system == 'linux'
  sdl_sources += files(
    'alsa/SDL_alsa_audio.c',
    'pulseaudio/SDL_pulseaudio.c',
    'pipewire/SDL_pipewire.c',
  )
elif host_system == 'emscripten'
  sdl_sources += files('emscripten/SDL_emscriptenaudio.c')
endif
