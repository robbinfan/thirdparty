cc_library(
    name = 'gflags',
    incs = ['./build/include/gflags'],
    srcs = [
        'gflags.cc',
        'gflags_reporting.cc',
        'gflags_completions.cc',
    ],
    deps = [':gen_config', '#pthread'],
    warning = 'no'
)

gen_rule(
    name = 'gen_config',
    cmd = 'cmake -H./thirdparty/gflags-2.1.1 -B$CURRENT/build',
    outs = ['./include/gflags/config.h'],
)
