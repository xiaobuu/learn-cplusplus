# Generated by Buckaroo - https://buckaroo.pm
include_defs('//BUCKAROO_DEPS')

cxx_library(
  name = 'bot',
  header_namespace = 'bot',
  srcs = glob([
    'bot/src/**/*.cpp',
  ]),
  headers = subdir_glob([ # private include files
    ('bot/detail', '**/*.h'), # they are only accesible inside the library
    ('bot/detail', '**/*.hpp'),
  ]),
  exported_headers = subdir_glob([ # public include files
    ('bot/include', '**/*.h'), # those will be exported
    ('bot/include', '**/*.hpp'), # and accessible via <bot/header.h>
  ]),
  deps = BUCKAROO_DEPS,
  visibility = ['PUBLIC']
)

cxx_binary(
  name = 'main',
  srcs = ['bot/apps/main.cpp'],
  headers = subdir_glob([
    # external headers
    ("extern", "**/*"),
  ]),
  deps = [':bot'],
  visibility = ['PUBLIC'],
  linker_flags = [
    '-lpthread',
    '-lboost_thread',
    '-lboost_system',
    '-lssl',
    '-lcrypto'
  ],
  compiler_flags = [
    '-std=c++14',
    '-lboost_thread',
  ]
)

cxx_binary(
  name = 'asio',
  srcs = ['bot/apps/asio.cpp'],
  headers = subdir_glob([
    # external headers
    ("extern", "**/*"),
  ]),
  deps = [],
  visibility = ['PUBLIC'],
  linker_flags = [
    '-lpthread',
    '-lboost_thread',
    '-lboost_system',
  ],
  compiler_flags = [
    '-std=c++11',
    '-lboost_thread',
  ]
)

cxx_binary(
  name = 'hash',
  srcs = ['bot/apps/hash.cpp'],
  headers = subdir_glob([
    # external headers
    ("extern", "**/*"),
  ]),
  deps = [':bot'],
  visibility = ['PUBLIC'],
  linker_flags = [
    #'-lpthread',
    #'-lboost_thread',
    #'-lboost_system',
    #'-lssl',
    '-lcrypto'
  ],
  compiler_flags = [
    '-std=c++11',
    #'-lboost_thread',
  ]
)
