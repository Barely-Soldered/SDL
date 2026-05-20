project('SDL3', ['c', 'cpp'],
  version: '3.4.8',
  license: 'Zlib',
  meson_version: '>= 1.0.0',
  default_options: [
    'c_std=c99',
    'cpp_std=c++17',
    'warning_level=1',
    'default_library=static',
  ],
)

cc = meson.get_compiler('c')
host_system = host_machine.system()

# MASM is needed for MSVC's hand-written prolog shims (src/stdlib/SDL_mslibc_*).
# Adding the language conditionally avoids forcing a MASM toolchain on every
# build (GCC/Clang don't use .masm sources).
if host_system == 'windows' and cc.get_id() == 'msvc'
  add_languages('masm', native: false, required: true)
endif

# ---------------------------------------------------------------------------
# Include directories
#
# include/                 - public SDL3/*.h headers, consumer-facing
# include/build_config/    - per-platform SDL_build_config_*.h selected via
#                            dispatcher in SDL_build_config.h
# src/                     - internal headers (SDL_internal.h, per-subsystem
#                            _c.h headers) referenced via relative paths from
#                            sibling subsystems
# ---------------------------------------------------------------------------
sdl_public_inc = include_directories('include', is_system: true)
sdl_internal_inc = include_directories(
  'include',
  'include/build_config',
  'src',
)

# ---------------------------------------------------------------------------
# Per-platform dependencies + link flags
#
# We dlopen most optional libraries (X11, Wayland, ALSA, PA, PipeWire, ...) so
# the only hard link deps are the toolchain primitives plus Vulkan headers.
# ---------------------------------------------------------------------------
sdl_deps = []
sdl_link_args = []
sdl_c_args = []

if host_system == 'windows'
  sdl_deps += [
    cc.find_library('user32'),
    cc.find_library('gdi32'),
    cc.find_library('winmm'),
    cc.find_library('imm32'),
    cc.find_library('ole32'),
    cc.find_library('oleaut32'),
    cc.find_library('version'),
    cc.find_library('uuid'),
    cc.find_library('advapi32'),
    cc.find_library('setupapi'),
    cc.find_library('shell32'),
    cc.find_library('dinput8'),
  ]
elif host_system == 'linux'
  sdl_deps += [
    dependency('threads'),
    cc.find_library('dl'),
    cc.find_library('m', required: false),
    cc.find_library('rt', required: false),
  ]
elif host_system == 'emscripten'
  # Emscripten provides pthread / GL / etc. via toolchain flags at link time;
  # nothing to find here.
endif

# ---------------------------------------------------------------------------
# Wayland protocol generation (Linux only)
#
# Each XML in wayland-protocols/ becomes two files via wayland-scanner:
#   <name>-client-protocol.h    (private-code header)
#   <name>-protocol.c           (private-code source)
# The generated outputs are appended to the wayland video backend source list
# inside src/video/meson.build.
# ---------------------------------------------------------------------------
wayland_generated_sources = []
wayland_generated_headers = []
wayland_generated_inc = []
if host_system == 'linux'
  wayland_scanner = find_program('wayland-scanner', required: true)
  wayland_protocols = [
    'alpha-modifier-v1',
    'color-management-v1',
    'cursor-shape-v1',
    'fractional-scale-v1',
    'frog-color-management-v1',
    'idle-inhibit-unstable-v1',
    'input-timestamps-unstable-v1',
    'keyboard-shortcuts-inhibit-unstable-v1',
    'pointer-constraints-unstable-v1',
    'pointer-gestures-unstable-v1',
    'pointer-warp-v1',
    'primary-selection-unstable-v1',
    'relative-pointer-unstable-v1',
    'tablet-v2',
    'text-input-unstable-v3',
    'viewporter',
    'wayland',
    'xdg-activation-v1',
    'xdg-decoration-unstable-v1',
    'xdg-dialog-v1',
    'xdg-foreign-unstable-v2',
    'xdg-output-unstable-v1',
    'xdg-shell',
    'xdg-toplevel-icon-v1',
  ]
  foreach proto : wayland_protocols
    xml = files('wayland-protocols' / proto + '.xml')
    wayland_generated_headers += custom_target(proto + '-client-protocol.h',
      input: xml,
      output: proto + '-client-protocol.h',
      command: [wayland_scanner, 'private-code', '@INPUT@', '@OUTPUT@'],
    )
    wayland_generated_sources += custom_target(proto + '-protocol.c',
      input: xml,
      output: proto + '-protocol.c',
      command: [wayland_scanner, 'private-code', '@INPUT@', '@OUTPUT@'],
    )
  endforeach
endif

# ---------------------------------------------------------------------------
# Source aggregation
#
# Each src/<subsystem>/meson.build appends to sdl_sources. The aggregator at
# src/meson.build owns the subdir() call order.
# ---------------------------------------------------------------------------
sdl_sources = []
subdir('src')

# ---------------------------------------------------------------------------
# Static library + dependency declaration
# ---------------------------------------------------------------------------
sdl3_lib = static_library('SDL3',
  sdl_sources,
  include_directories: sdl_internal_inc,
  dependencies: sdl_deps,
  c_args: sdl_c_args,
)

sdl3_dep = declare_dependency(
  link_with: sdl3_lib,
  link_args: sdl_link_args,
  include_directories: sdl_public_inc,
  dependencies: sdl_deps,
)

meson.override_dependency('sdl3', sdl3_dep)
