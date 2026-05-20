sdl_sources += files(
  'SDL_render.c',
  'SDL_render_unsupported.c',
  'SDL_yuv_sw.c',
  # Software renderer: SDL_internal.h treats SDL_VIDEO_RENDER_SW as load-bearing
  # default infrastructure (fallback for CPU-side SDL_Surface targets), so this
  # ships on every platform regardless of which hardware backends are active.
  'software/SDL_blendfillrect.c',
  'software/SDL_blendline.c',
  'software/SDL_blendpoint.c',
  'software/SDL_drawline.c',
  'software/SDL_drawpoint.c',
  'software/SDL_render_sw.c',
  'software/SDL_triangle.c',
)

if host_system == 'windows'
  sdl_sources += files(
    'direct3d11/SDL_render_d3d11.c',
    'direct3d11/SDL_shaders_d3d11.c',
    'direct3d12/SDL_render_d3d12.c',
    'direct3d12/SDL_shaders_d3d12.c',
    'opengl/SDL_render_gl.c',
    'opengl/SDL_shaders_gl.c',
    'opengles2/SDL_render_gles2.c',
    'opengles2/SDL_shaders_gles2.c',
    'vulkan/SDL_render_vulkan.c',
    'vulkan/SDL_shaders_vulkan.c',
    'gpu/SDL_pipeline_gpu.c',
    'gpu/SDL_render_gpu.c',
    'gpu/SDL_shaders_gpu.c',
  )
elif host_system == 'linux'
  sdl_sources += files(
    'opengl/SDL_render_gl.c',
    'opengl/SDL_shaders_gl.c',
    'opengles2/SDL_render_gles2.c',
    'opengles2/SDL_shaders_gles2.c',
    'vulkan/SDL_render_vulkan.c',
    'vulkan/SDL_shaders_vulkan.c',
    'gpu/SDL_pipeline_gpu.c',
    'gpu/SDL_render_gpu.c',
    'gpu/SDL_shaders_gpu.c',
  )
elif host_system == 'emscripten'
  sdl_sources += files(
    'opengles2/SDL_render_gles2.c',
    'opengles2/SDL_shaders_gles2.c',
  )
endif
