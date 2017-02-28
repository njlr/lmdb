cxx_library(
  name = 'lmdb',
  header_namespace = 'lmdb',
  exported_headers = subdir_glob([
    ('libraries/liblmdb', 'lmdb.h'),
    ('libraries/liblmdb', 'midl.h'),
  ]),
  srcs = [
    'libraries/liblmdb/mdb.c',
    'libraries/liblmdb/midl.c',
  ],
  visibility = [
    'PUBLIC',
  ],
)

cxx_binary(
  name = 'mdb_copy',
  srcs = [
    'libraries/liblmdb/mdb_copy.c',
  ],
  deps = [
    ':lmdb',
  ],
)

cxx_binary(
  name = 'mdb_dump',
  srcs = [
    'libraries/liblmdb/mdb_dump.c',
  ],
  deps = [
    ':lmdb',
  ],
)

cxx_binary(
  name = 'mdb_load',
  srcs = [
    'libraries/liblmdb/mdb_load.c',
  ],
  deps = [
    ':lmdb',
  ],
)

cxx_binary(
  name = 'mdb_stat',
  srcs = [
    'libraries/liblmdb/mdb_stat.c',
  ],
  deps = [
    ':lmdb',
  ],
)

genrule(
  name = 'sample-mdb.c',
  out = 'sample-mdb.c',
  srcs = [
    'libraries/liblmdb/sample-mdb.txt',
  ],
  cmd = 'cp $SRCS $OUT'
)

cxx_binary(
  name = 'sample-mdb',
  headers = {
    'lmdb.h': 'libraries/liblmdb/lmdb.h',
  },
  srcs = [
    ':sample-mdb.c',
  ],
  deps = [
    ':lmdb',
  ],
)
