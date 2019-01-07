# raylib-meson

[raylib](https://github.com/raysan5/raylib) build for [Meson](https://mesonbuild.com) projects.

## Usage

1. Create a [meson.build](examples/core_basic_window/meson.build) file
    ``` python
    project('myproject', 'c',
      version : '1.0.0',
      license: 'MIT'
    )

    raylib_proj = subproject('raylib')
    raylib_dep = raylib_proj.get_variable('raylib_dep')

    executable('myproject', 'myproject.c',
      dependencies: [raylib_dep]
    )
    ```
    
2. Create the [subprojects .wrap files](examples/core_basic_window/subprojects)
    - [`subprojects/glfw.wrap`](examples/core_basic_window/subprojects/glfw.wrap)
    - [`subprojects/raylib.wrap`](examples/core_basic_window/subprojects/raylib.wrap)

3. Build the project
    ``` bash
    meson build
    cd build
    ninja
    ```

See [the `examples` folder](examples) for some examples of this in place. Also see [raylib-meson-sample](https://github.com/RobLoach/raylib-meson-sample) for a dedicated repository.

## Development

``` bash
meson build
cd build
ninja
```
