# Aggregator: each subsystem appends to the parent's sdl_sources via subdir().
#
# Order is not load-bearing (no inter-subsystem dependency at the meson level
# beyond the final static_library link), but kept alphabetical for sanity.

# Top-level src/ files (SDL.c, SDL_assert.c, etc.)
sdl_sources += files(
  'SDL.c',
  'SDL_assert.c',
  'SDL_error.c',
  'SDL_guid.c',
  'SDL_hashtable.c',
  'SDL_hints.c',
  'SDL_list.c',
  'SDL_log.c',
  'SDL_properties.c',
  'SDL_utils.c',
)

subdir('atomic')
subdir('audio')
subdir('core')
subdir('cpuinfo')
subdir('dialog')
subdir('events')
subdir('filesystem')
subdir('gpu')
subdir('haptic')
subdir('hidapi')
subdir('io')
subdir('joystick')
subdir('libm')
subdir('loadso')
subdir('locale')
subdir('main')
subdir('misc')
subdir('power')
subdir('process')
subdir('render')
subdir('sensor')
subdir('stdlib')
subdir('storage')
subdir('thread')
subdir('time')
subdir('timer')
subdir('video')
