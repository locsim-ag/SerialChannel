src_files = files(
    'src\SerialChannel_win.cpp',
  )

SerialChannel = static_library('SerialChannel',
  src_files,
  include_directories: include_directories('.'),
  dependencies: [boost_dep],
  )

SerialChannel_dep = declare_dependency(
  link_with: SerialChannel,
  )
