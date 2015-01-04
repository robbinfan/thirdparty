cc_library(
    name = 'snappy',
    srcs = [
        'snappy.cc',
        'snappy-c.cc',
        'snappy-sinksource.cc',
        'snappy-stubs-internal.cc'
    ],
    defs = ['HAVE_CONFIG_H'],
    deps = [':gen_config'],
    warning = 'no',
)

gen_rule(
    name = 'gen_config',
    cmd = 'cd thirdparty/snappy-1.1.2;./configure;cd -',
    outs = ['./config.h'],
)

cc_binary(
    name = 'snappy_unittest',
    srcs = [
        'snappy_unittest.cc',
        'snappy-test.cc',
    ],
    defs = ['HAVE_CONFIG_H'],
    deps = [':snappy', '#z'],
    warning = 'no',
)

