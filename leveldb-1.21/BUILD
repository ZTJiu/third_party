package(default_visibility = ["//visibility:public"])
licenses(["notice"]) # MIT license

cc_library(
  name = "leveldb",
  includes = [
    "include",
    ".",
  ],
  hdrs = [
    "include/leveldb/cache.h",
    "include/leveldb/c.h",
    "include/leveldb/comparator.h",
    "include/leveldb/db.h",
    "include/leveldb/dumpfile.h",
    "include/leveldb/env.h",
    "include/leveldb/export.h",
    "include/leveldb/filter_policy.h",
    "include/leveldb/iterator.h",
    "include/leveldb/options.h",
    "include/leveldb/slice.h",
    "include/leveldb/status.h",
    "include/leveldb/table_builder.h",
    "include/leveldb/table.h",
    "include/leveldb/write_batch.h",
  ],
  defines = ["LEVELDB_PLATFORM_POSIX=1", "LEVELDB_IS_BIG_ENDIAN=0"],
  copts = [
  "-DROCKSDB_PLATFORM_POSIX",
  "-DROCKSDB_LIB_IO_POSIX",
  "-DOS_LINUX",
  "-fno-builtin-memcmp",
  "-DROCKSDB_FALLOCATE_PRESENT",
  "-DZLIB",
  "-DSNAPPY",
  "-DBZIP2",
  "-DROCKSDB_MALLOC_USABLE_SIZE",
  "-DROCKSDB_PTHREAD_ADAPTIVE_MUTEX",
  "-DROCKSDB_BACKTRACE",
  "-DROCKSDB_RANGESYNC_PRESENT",
  "-DROCKSDB_SCHED_GETCPU_PRESENT",
  "-march=native",
  "-DHAVE_SSE42",
  "-DROCKSDB_SUPPORT_THREAD_LOCAL",
  "-DIOS_CROSS_COMPILE",
  "-LEVELDB_PLATFORM_POSIX=1",
  ],
  srcs = [
    #"${LEVELDB_PORT_CONFIG_DIR}/port_config.h"
    "port/port_config.h",
    "port/port_example.h",
    "port/port.h",
    "port/port_stdcxx.h",
    "port/thread_annotations.h",

    "db/builder.cc",
    "db/builder.h",
    "db/c.cc",
    "db/db_impl.cc",
    "db/db_impl.h",
    "db/db_iter.cc",
    "db/db_iter.h",
    "db/dbformat.cc",
    "db/dbformat.h",
    "db/dumpfile.cc",
    "db/filename.cc",
    "db/filename.h",
    "db/log_format.h",
    "db/log_reader.cc",
    "db/log_reader.h",
    "db/log_writer.cc",
    "db/log_writer.h",
    "db/memtable.cc",
    "db/memtable.h",
    "db/repair.cc",
    "db/skiplist.h",
    "db/snapshot.h",
    "db/table_cache.cc",
    "db/table_cache.h",
    "db/version_edit.cc",
    "db/version_edit.h",
    "db/version_set.cc",
    "db/version_set.h",
    "db/write_batch_internal.h",
    "db/write_batch.cc",
    "table/block_builder.cc",
    "table/block_builder.h",
    "table/block.cc",
    "table/block.h",
    "table/filter_block.cc",
    "table/filter_block.h",
    "table/format.cc",
    "table/format.h",
    "table/iterator_wrapper.h",
    "table/iterator.cc",
    "table/merger.cc",
    "table/merger.h",
    "table/table_builder.cc",
    "table/table.cc",
    "table/two_level_iterator.cc",
    "table/two_level_iterator.h",
    "util/arena.cc",
    "util/arena.h",
    "util/bloom.cc",
    "util/cache.cc",
    "util/coding.cc",
    "util/coding.h",
    "util/comparator.cc",
    "util/crc32c.cc",
    "util/crc32c.h",
    "util/env.cc",
    "util/filter_policy.cc",
    "util/hash.cc",
    "util/hash.h",
    "util/logging.cc",
    "util/logging.h",
    "util/mutexlock.h",
    "util/no_destructor.h",
    "util/options.cc",
    "util/random.h",
    "util/status.cc",

    "util/env_posix.cc",
    "util/posix_logger.h",
    "util/env_posix_test_helper.h",

    # public
    #"${LEVELDB_PUBLIC_INCLUDE_DIR}/c.h"
    #"${LEVELDB_PUBLIC_INCLUDE_DIR}/cache.h"
    #"${LEVELDB_PUBLIC_INCLUDE_DIR}/comparator.h"
    #"${LEVELDB_PUBLIC_INCLUDE_DIR}/db.h"
    #"${LEVELDB_PUBLIC_INCLUDE_DIR}/dumpfile.h"
    #"${LEVELDB_PUBLIC_INCLUDE_DIR}/env.h"
    #"${LEVELDB_PUBLIC_INCLUDE_DIR}/export.h"
    #"${LEVELDB_PUBLIC_INCLUDE_DIR}/filter_policy.h"
    #"${LEVELDB_PUBLIC_INCLUDE_DIR}/iterator.h"
    #"${LEVELDB_PUBLIC_INCLUDE_DIR}/options.h"
    #"${LEVELDB_PUBLIC_INCLUDE_DIR}/slice.h"
    #"${LEVELDB_PUBLIC_INCLUDE_DIR}/status.h"
    #"${LEVELDB_PUBLIC_INCLUDE_DIR}/table_builder.h"
    #"${LEVELDB_PUBLIC_INCLUDE_DIR}/table.h"
    #"${LEVELDB_PUBLIC_INCLUDE_DIR}/write_batch.h"

  ],
  deps = [
    #"//infra-cpp-thirdparty/snappy-113",
    #"//infra-cpp-thirdparty/bzip2-106:bz2",
    #"//infra-cpp-thirdparty/gtest-170",
  ],
)

cc_binary(
  name = "db_bench",
  includes = [
    "include",
    ".",
  ],
  copts=[
    "-O",
    "-I./",
  ],
  linkopts=[
    "-lm",
    "-lpthread"
  ],
  linkstatic = True,
  srcs=[
    "db/db_bench.cc",
    "util/histogram.cc",
    "util/histogram.h",
    "util/testutil.cc",
    "util/testutil.h",
    "util/testharness.cc",
    "util/testharness.h",
    
    "helpers/memenv/memenv.h",
    "helpers/memenv/memenv.cc",

  ]+ glob([
  ],
  exclude = [
  ]),
  deps = [
    "//leveldb",
  ],
) # cc_binary:db_bench
