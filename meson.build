project('ShapeParam', 'cpp',
  version : '0.1',
  default_options : ['warning_level=3', 'cpp_std=c++14'])


cmake = import('cmake')

igl_proj = cmake.subproject('libigl', cmake_options: ['-DLIBIGL_WITH_OPENGL=ON','-DLIB_WITH_OPENGL_GLFW=ON', '-DLIBIGL_EXPORT_TARGETS=ON'])

igl_lib = igl_proj.dependency('igl_opengl_glfw')
glad_lib = igl_proj.dependency('glad')
message(igl_proj.target_list())

src_files = []

subdir('src')

executable('ShapeParam',
           src_files,
	   dependencies: [igl_lib, glad_lib],
           install : true)
