project('core_basic_window', 'c',
	version : '2.0.1-alpha',
	license: 'MIT'
)

raylib_proj = subproject('raylib')
raylib_dep = raylib_proj.get_variable('raylib_dep')

executable('core_basic_window', 'core_basic_window.c',
	dependencies: [raylib_dep]
)
