sdl_sources += files('SDL_thread.c')

if host_system == 'windows'
  # Windows: native CV + SRWLock primitives, plus the generic suffix variants
  # (compiled as fallbacks when SDL_THREAD_GENERIC_COND_SUFFIX /
  # SDL_THREAD_GENERIC_RWLOCK_SUFFIX are set in SDL_build_config_windows.h).
  sdl_sources += files(
    'windows/SDL_syscond_cv.c',
    'windows/SDL_sysmutex.c',
    'windows/SDL_sysrwlock_srw.c',
    'windows/SDL_syssem.c',
    'windows/SDL_systhread.c',
    'windows/SDL_systls.c',
    'generic/SDL_syscond.c',
    'generic/SDL_sysrwlock.c',
  )
else
  # Linux + Emscripten: pthread
  sdl_sources += files(
    'pthread/SDL_syscond.c',
    'pthread/SDL_sysmutex.c',
    'pthread/SDL_sysrwlock.c',
    'pthread/SDL_syssem.c',
    'pthread/SDL_systhread.c',
    'pthread/SDL_systls.c',
  )
endif
