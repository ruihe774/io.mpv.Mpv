project(
  'lua',
  'c',
  version: '5.1.5',
  license: 'MIT',
  default_options: ['c_std=gnu99'],
  meson_version: '>=1.0.0'
)

cc = meson.get_compiler('c')

lua = library(
  'lua',
  [
    'src/lapi.c',
    'src/lcode.c',
    'src/ldebug.c',
    'src/ldo.c',
    'src/ldump.c',
    'src/lfunc.c',
    'src/lgc.c',
    'src/llex.c',
    'src/lmem.c',
    'src/lobject.c',
    'src/lopcodes.c',
    'src/lparser.c',
    'src/lstate.c',
    'src/lstring.c',
    'src/ltable.c',
    'src/ltm.c',
    'src/lundump.c',
    'src/lvm.c',
    'src/lzio.c',
    'src/lauxlib.c',
    'src/lbaselib.c',
    'src/ldblib.c',
    'src/liolib.c',
    'src/lmathlib.c',
    'src/loslib.c',
    'src/ltablib.c',
    'src/lstrlib.c',
    'src/loadlib.c',
    'src/linit.c'
  ],
  c_args: ['-DLUA_USE_POSIX'],
  dependencies: [cc.find_library('m')],
  gnu_symbol_visibility: 'hidden',
  include_directories: ['src'],
  install: true,
  soversion: '5.1'
)

lua_dep = declare_dependency(
  link_with: lua,
  include_directories: ['src']
)

meson.override_dependency('lua', lua_dep)
