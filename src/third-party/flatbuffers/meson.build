flatbuffer_sources = '''
    idl_parser.cpp
    util.cpp
'''.split()

flatbuffers_lib = static_library('flatbuffers', flatbuffer_sources, include_directories: [thirdparty_incdir, src_incdir])
flatbuffers_dep = declare_dependency(link_with: flatbuffers_lib, include_directories: thirdparty_incdir)

