package(default_visibility = ["//visibility:public"])
licenses(["notice"])

cc_library(
    name = "gflags-220",
    includes = ["include"],
    hdrs = glob(["src/gflags/*.h", "include/gflags/*.h"]),
    copts = [
        "-Wall",
        "-Wwrite-strings",
        "-Woverloaded-virtual",
        "-Wno-sign-compare",
        "-Wno-unused-local-typedefs",
        "-DNDEBUG",
        "-pthread",
    ],
    linkopts = [
        "-pthread",
    ],
    linkstatic = 1,
    #hdrs_check = "loose",
    srcs = glob([
        "src/*.h",
        "src/*.cc",
        ], exclude = [
            "src/windows_port.cc",
            "src/windows_port.h"
        ]),
    deps = [],
)
