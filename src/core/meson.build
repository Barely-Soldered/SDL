sdl_sources += files('SDL_core_unsupported.c')

if host_system == 'linux'
  sdl_sources += files(
    'linux/SDL_dbus.c',
    'linux/SDL_evdev.c',
    'linux/SDL_evdev_capabilities.c',
    'linux/SDL_evdev_kbd.c',
    'linux/SDL_fcitx.c',
    'linux/SDL_ibus.c',
    'linux/SDL_ime.c',
    'linux/SDL_progressbar.c',
    'linux/SDL_system_theme.c',
    'linux/SDL_threadprio.c',
    'linux/SDL_udev.c',
  )
  sdl_sources += files(
    'unix/SDL_appid.c',
    'unix/SDL_fribidi.c',
    'unix/SDL_gtk.c',
    'unix/SDL_libthai.c',
    'unix/SDL_poll.c',
  )
elif host_system == 'windows'
  sdl_sources += files(
    'windows/SDL_gameinput.cpp',
    'windows/SDL_hid.c',
    'windows/SDL_immdevice.c',
    'windows/SDL_windows.c',
    'windows/SDL_xinput.c',
  )
endif
