package(default_visibility = ["//visibility:public"])
licenses(["notice"])

cc_library(
    name = "log4cplus-200-rc1",
    includes = ["include","threadpool"],
    hdrs = glob(["include/log4cplus/**/*.h", "include/log4cplus/**/*.hxx"]),
    copts = [
        "-DHAVE_CONFIG_H",
        "-DNDEBUG",
        "-DINSIDE_LOG4CPLUS",
        "-D_GNU_SOURCE=1",
        "-D_REENTRANT",
        "-g",
        "-O2",
        "-Wall",
        "-fdiagnostics-show-caret",
        "-ftrack-macro-expansion",
        "-Wextra",
        "-pedantic",
        "-Wstrict-aliasing",
        "-Wstrict-overflow",
        "-Woverloaded-virtual",
        "-Wold-style-cast",
        "-Wc++0x-compat",
        "-Wc++11-compat",
        "-Wundef",
        "-Wshadow",
        "-Wformat",
        "-Wsuggest-attribute=format",
        "-Wsuggest-attribute=noreturn",
        "-Wno-variadic-macros",
        "-fvisibility=hidden",
        "-pthread",
        "-Wno-deprecated-declarations",
        "-Wno-unused-parameter",
        "-Wno-shadow",
    ],
    linkopts = [
        "-pthread",
        "-lrt",
    ],
    linkstatic = 1,
    srcs = glob(["src/*.cxx",
                "threadpool/ThreadPool.h"],
        exclude=["src/msttsappender.cxx",
                "src/clfsappender.cxx",
                "src/cygwin-win32.cxx",
                "src/socket-win32.cxx"]),
    deps = [
    ],
)

cc_test(
    name = "test",
    copts = [
        "-g",
        "-O2",
        "-Wall",
        "-Wno-deprecated-declarations",
    ],
    linkopts = [
        "-lrt",
    ],
    srcs = [
        "tests/thread_test/main.cxx",
    ],
    deps = [
        ":log4cplus-120",
    ],
)
