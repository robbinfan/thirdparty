gen_rule(
    name = "gen_config",
    cmd="cd thirdparty/gmock-1.7.0;./configure;cd -",
    outs=['./build-aux/config.h']
)

cc_library(
    name = 'gmock',
    srcs = [
        'src/gmock-cardinalities.cc',
        'src/gmock.cc',
        'src/gmock-internal-utils.cc',
        'src/gmock-matchers.cc',
        'src/gmock-spec-builders.cc'
    ],
    incs = ['include', 'build-aux'],
    defs = ['HAVE_CONFIG_H', 'GTEST_HAS_PTHREAD=1'],
    deps = '//thirdparty/gtest:gtest'
)

cc_library(
    name = 'gmock_main',
    srcs = [
        'src/gmock_main.cc',
    ],
    incs = ['include', 'build-aux'],
    defs = ['HAVE_CONFIG_H', 'GTEST_HAS_PTHREAD=1'],
    deps = ':gmock'
)
