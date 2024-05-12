imgui_sources = '''
    imgui.cpp
    imgui_demo.cpp
    imgui_draw.cpp
    imgui_tables.cpp
    imgui_widgets.cpp
'''.split()

if get_option('gui') == 'tiles'
  imgui_sources += '''imgui_impl_sdl2.cpp imgui_impl_sdlrenderer2.cpp'''.split()
endif

imgui_incdir = include_directories('.')
imgui_lib = static_library('imgui', imgui_sources, dependencies: gui_dep)
imgui_dep = declare_dependency(link_with: imgui_lib, include_directories: imgui_incdir, dependencies: [])

if get_option('gui') == 'tiles'
  gui_dep += imgui_dep
endif

