sdl_sources += files('SDL_gpu.c')

if host_system == 'windows'
  sdl_sources += files(
    'd3d12/SDL_gpu_d3d12.c',
    'vulkan/SDL_gpu_vulkan.c',
  )
elif host_system == 'linux'
  sdl_sources += files('vulkan/SDL_gpu_vulkan.c')
endif
# Emscripten: no GPU backend (no Vulkan / D3D12 in browser)
