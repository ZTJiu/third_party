package(default_visibility = ["//visibility:public"])
licenses(["notice"]) # MIT license

cc_library(
  name = "libev-422",
  includes= [
    ".",
  ],
  hdrs = [
    "ev.h",
    "ev++.h",
  ],
  textual_hdrs = [
    "ev_epoll.c",
    "ev_poll.c",
    "ev_select.c",
  ],
  copts = [
    "-O",
    "-Wno-unused-result",
    "-Wno-unused-value",
    "-Wno-comment",
    "-Wno-parentheses",
  ],
  srcs = glob(
    [
      "*.h",
      "ev.c",
      "event.c",
    ],
  ),
  deps = [
  ],
)

