sdl_sources += files(
  'SDL_dialog.c',
  'SDL_dialog_utils.c',
)

if host_system == 'windows'
  sdl_sources += files('windows/SDL_windowsdialog.c')
elif host_system == 'linux'
  sdl_sources += files(
    'unix/SDL_portaldialog.c',
    'unix/SDL_unixdialog.c',
    'unix/SDL_zenitydialog.c',
    'unix/SDL_zenitymessagebox.c',
  )
else
  sdl_sources += files('dummy/SDL_dummydialog.c')
endif
