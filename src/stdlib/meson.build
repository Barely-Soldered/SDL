sdl_sources += files(
  'SDL_crc16.c',
  'SDL_crc32.c',
  'SDL_getenv.c',
  'SDL_iconv.c',
  'SDL_malloc.c',
  'SDL_memcpy.c',
  'SDL_memmove.c',
  'SDL_memset.c',
  'SDL_murmur3.c',
  'SDL_qsort.c',
  'SDL_random.c',
  'SDL_stdlib.c',
  'SDL_string.c',
  'SDL_strtokr.c',
)

# MSVC compiler-intrinsics shim. Pure C on MSVC; the .masm assembly variants
# satisfy ARM64 / x86_64 prolog needs that the C version can't express. MinGW
# and other compilers don't need this shim.
if host_system == 'windows' and cc.get_id() == 'msvc'
  sdl_sources += files('SDL_mslibc.c')
  if host_machine.cpu_family() == 'x86_64'
    sdl_sources += files('SDL_mslibc_x64.masm')
  elif host_machine.cpu_family() == 'aarch64'
    sdl_sources += files('SDL_mslibc_arm64.masm')
  endif
endif
