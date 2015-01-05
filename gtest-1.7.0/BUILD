gen_rule(
    name = "gen_config",
    cmd="cd thirdparty/gtest-1.7.0;./configure;cd -",
    outs=['./build-aux/config.h']
)

cc_library(
    name = "gtest",
    srcs = [
        "src/gtest.cc",
        "src/gtest-death-test.cc",
        "src/gtest-filepath.cc",
        "src/gtest-printers.cc",
        "src/gtest-port.cc",
        "src/gtest-test-part.cc",
        "src/gtest-typed-test.cc",
    ],
    incs = ['.', './include'],
    defs = ['HAVE_CONFIG_H', 'GTEST_HAS_PTHREAD=1'],
    deps = [':gen_config', '#pthread'],
    warning = 'no'
)

cc_library(
    name = "gtest_main",
    srcs = [
        "src/gtest_main.cc",
    ],
    incs = ['.', './include'],
    defs = ['HAVE_CONFIG_H', 'GTEST_HAS_PTHREAD=1'],
    deps = [
        ":gtest",
        "//thirdparty/gflags:gflags"
    ],
    warning = 'no'
)
