imtui_sources = '''
    imtui-impl-ncurses.cpp
    imtui-impl-text.cpp
'''.split()

imtui_incdir = include_directories('.')
imtui_lib = static_library('imtui', imtui_sources, include_directories: thirdparty_incdir, dependencies: [ncurses_dep, imgui_dep])
imtui_dep = declare_dependency(link_with: imtui_lib, include_directories: thirdparty_incdir, dependencies: imgui_dep)

gui_dep += imtui_dep

