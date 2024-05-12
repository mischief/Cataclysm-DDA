project('Cataclysm-DDA', 'cpp', 
    default_options: [
        'cpp_std=c++17',
        'werror=false',
        'warning_level=1',
    ],
    version: '0.I'
)

fs = import('fs')

zlib_dep = dependency('zlib')

gui_dep = []

if get_option('gui') == 'curses'
    ncurses_dep = dependency('ncursesw')
    gui_dep += ncurses_dep
    add_project_arguments('-DIMTUI', language: 'cpp')
endif
if get_option('gui') == 'tiles'
    if get_option('sound')
        sdl2_mixer_dep = dependency('SDL2_mixer')
        add_project_arguments('-DSDL_SOUND', language: 'cpp')
        gui_dep += sdl2_mixer_dep
    endif

    sdl2_dep = dependency('sdl2')
    sdl2_image_dep = dependency('SDL2_image')
    sdl2_ttf_dep = dependency('SDL2_ttf')
    gui_dep += [sdl2_dep, sdl2_image_dep, sdl2_ttf_dep]
    add_project_arguments('-DSDL_MAIN_HANDLED', language: 'cpp')
    add_project_arguments('-DTILES', language: 'cpp')
    add_project_arguments('-DIMGUI_DISABLE_OBSOLETE_KEYIO', language: 'cpp')

    if host_machine.system() == 'windows'
        add_project_arguments('-DUSE_WINMAIN', language: 'cpp')
    endif
endif

src_pch = meson.source_root() / 'pch' / 'main-pch.hpp'

cxx = meson.get_compiler('cpp')
### XXX: not yet
#add_global_arguments('-stdlib=libc++', language: 'cpp')
#add_global_link_arguments('-stdlib=libc++', language: 'cpp')

subdir('src')
subdir('tests')

