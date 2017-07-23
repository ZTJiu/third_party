package(default_visibility = ["//visibility:public"])
licenses(["notice"])

cc_library(
	name = "gflags-221",
	includes = ["include"],
	hdrs = glob(["include/gflags/*.h"]),
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
	srcs = glob([
		"src/config.h",
		"src/mutex.h",
		"src/util.h",
		"src/gflags.cc",
		"src/gflags_reporting.cc",
		"src/gflags_completions.cc",
	]),
	deps = [],
)
