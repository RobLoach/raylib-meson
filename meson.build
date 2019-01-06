project('raylib', 'c',
	version : '2.0.1-alpha',
	license: 'Zlib'
)

add_project_arguments('-DPLATFORM_' + get_option('raylib_platform'),
	language: 'c'
)

glfw_proj = subproject('glfw')
glfw_dep = glfw_proj.get_variable('glfw_dep')
glfw_dependencies = glfw_proj.get_variable('dependencies')

raylib_sources = [
	'raylib/src/audio.c',
	'raylib/src/audio.h',
	'raylib/src/camera.h',
	'raylib/src/config.h',
	'raylib/src/core.c',
	'raylib/src/easings.h',
	'raylib/src/gestures.h',
	'raylib/src/models.c',
	'raylib/src/physac.h',
	'raylib/src/raylib.h',
	'raylib/src/raymath.h',
	'raylib/src/rglfw.c',
	'raylib/src/rlgl.h',
	'raylib/src/shapes.c',
	'raylib/src/text.c',
	'raylib/src/textures.c',
	'raylib/src/utils.c',
	'raylib/src/utils.h',
	'raylib/src/external/ANGLE/EGL/egl.h',
	'raylib/src/external/ANGLE/EGL/eglext.h',
	'raylib/src/external/ANGLE/EGL/eglplatform.h',
	'raylib/src/external/ANGLE/GLES2/gl2.h',
	'raylib/src/external/ANGLE/GLES2/gl2ext.h',
	'raylib/src/external/ANGLE/GLES2/gl2platform.h',
	'raylib/src/external/ANGLE/GLES3/gl3.h',
	'raylib/src/external/ANGLE/GLES3/gl3ext.h',
	'raylib/src/external/ANGLE/GLES3/gl3platform.h',
	'raylib/src/external/ANGLE/KHR/khrplatform.h',
	'raylib/src/external/ANGLE/angle_windowsstore.h',
	'raylib/src/external/cgltf.h',
	'raylib/src/external/cgltf.h',
	'raylib/src/external/dirent.h',
	'raylib/src/external/dr_flac.h',
	'raylib/src/external/dr_mp3.h',
	'raylib/src/external/dr_wav.h',
	'raylib/src/external/glad.h',
	'raylib/src/external/jar_mod.h',
	'raylib/src/external/jar_xm.h',
	'raylib/src/external/mini_al.c',
	'raylib/src/external/mini_al.h',
	'raylib/src/external/par_shapes.h',
	'raylib/src/external/rgif.h',
	'raylib/src/external/stb_image.h',
	'raylib/src/external/stb_image_resize.h',
	'raylib/src/external/stb_image_write.h',
	'raylib/src/external/stb_perlin.h',
	'raylib/src/external/stb_rect_pack.h',
	'raylib/src/external/stb_truetype.h',
	'raylib/src/external/stb_vorbis.h'
]

raylib_dependencies = [glfw_dep, glfw_dependencies]

raylib_inc = include_directories('raylib/src')
raylib_lib = static_library('raylib', raylib_sources,
	dependencies: raylib_dependencies,
	include_directories: raylib_inc
)

raylib_dep = declare_dependency(
	include_directories: raylib_inc,
	link_with: raylib_lib
)

if get_option('raylib_build_examples')
	examples_deps = [raylib_dep]
	executable('core_basic_window', 'raylib/examples/core/core_basic_window.c', dependencies: examples_deps)
endif