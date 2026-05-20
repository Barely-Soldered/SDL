sdl_sources += files(
  'SDL_gamepad.c',
  'SDL_joystick.c',
  'SDL_steam_virtual_gamepad.c',
  'controller_type.c',
  'dummy/SDL_sysjoystick.c',
  'virtual/SDL_virtualjoystick.c',
)

# HIDAPI joystick backends (Switch / DualSense / Xbox controllers / Steam Deck
# / 8BitDo / Flydigi / etc.) — compiled on every desktop platform; the
# emscripten/dummy paths skip it. Steam Controller header-only files at
# hidapi/steam/ ship in-tree but have no .c files to enumerate.
if host_system == 'windows' or host_system == 'linux'
  sdl_sources += files(
    'hidapi/SDL_hidapi_8bitdo.c',
    'hidapi/SDL_hidapi_combined.c',
    'hidapi/SDL_hidapi_flydigi.c',
    'hidapi/SDL_hidapi_gamecube.c',
    'hidapi/SDL_hidapi_gip.c',
    'hidapi/SDL_hidapi_lg4ff.c',
    'hidapi/SDL_hidapi_luna.c',
    'hidapi/SDL_hidapi_ps3.c',
    'hidapi/SDL_hidapi_ps4.c',
    'hidapi/SDL_hidapi_ps5.c',
    'hidapi/SDL_hidapi_rumble.c',
    'hidapi/SDL_hidapi_shield.c',
    'hidapi/SDL_hidapi_sinput.c',
    'hidapi/SDL_hidapi_stadia.c',
    'hidapi/SDL_hidapi_steam.c',
    'hidapi/SDL_hidapi_steam_hori.c',
    'hidapi/SDL_hidapi_steam_triton.c',
    'hidapi/SDL_hidapi_steamdeck.c',
    'hidapi/SDL_hidapi_switch.c',
    'hidapi/SDL_hidapi_switch2.c',
    'hidapi/SDL_hidapi_wii.c',
    'hidapi/SDL_hidapi_xbox360.c',
    'hidapi/SDL_hidapi_xbox360w.c',
    'hidapi/SDL_hidapi_xboxone.c',
    'hidapi/SDL_hidapi_zuiki.c',
    'hidapi/SDL_hidapijoystick.c',
    'hidapi/SDL_report_descriptor.c',
  )
endif

if host_system == 'windows'
  sdl_sources += files(
    'windows/SDL_dinputjoystick.c',
    'windows/SDL_rawinputjoystick.c',
    'windows/SDL_windows_gaming_input.c',
    'windows/SDL_windowsjoystick.c',
    'windows/SDL_xinputjoystick.c',
  )
elif host_system == 'linux'
  sdl_sources += files('linux/SDL_sysjoystick.c')
elif host_system == 'emscripten'
  sdl_sources += files('emscripten/SDL_sysjoystick.c')
endif
